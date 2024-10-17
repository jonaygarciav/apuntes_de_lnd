# Validación de Documentos XML con DTD

## Introducción

Un documento XML es válido cuando sigue las reglas definidas en un DTD o un esquema XSD. Es decir, además de estar bien formado, el contenido debe cumplir con una estructura previamente definida que determine qué elementos y atributos son permitidos y en qué orden deben aparecer.

Un __DTD__ (_Document Type Definition_) es un conjunto de reglas que define la estructura y las relaciones entre los elementos, atributos y entidades dentro de un documento XML. Un DTD puede estar interno (dentro del propio documento XML) o externo (definido en un archivo aparte). Su principal objetivo es validar que los documentos XML cumplen con un formato o estructura específica.

Existen dos tipos de DTD: `interno` y `externo`.

### DTD interno

Se incluye dentro del propio documento XML, entre las etiquetas `<!DOCTYPE ... >`.

Ejemplo:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE libro [
    <!ELEMENT libro (titulo, autor, precio)>
    <!ELEMENT titulo (#PCDATA)>
    <!ELEMENT autor (#PCDATA)>
    <!ELEMENT precio (#PCDATA)>
]>
<libro>
    <titulo>XML Avanzado</titulo>
    <autor>Pedro Gómez</autor>
    <precio>30.00</precio>
</libro>
```

### DTD Externo

Se define en un archivo externo y se referencia en el documento XML mediante la declaración `<!DOCTYPE ... SYSTEM "libro.dtd">`.

Ejemplo de referencia a un DTD externo:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE libro SYSTEM "libro.dtd">
<libro>
    <titulo>XML Avanzado</titulo>
    <autor>Pedro Gómez</autor>
    <precio>30.00</precio>
</libro>
```

### Definición de elementos dentro de un DTD__

Contenido del archivo _libro.dtd_:

```xml
<!ELEMENT libro (titulo, autor, precio)>
<!ELEMENT titulo (#PCDATA)>
<!ELEMENT autor (#PCDATA)>
<!ELEMENT precio (#PCDATA)>
```

En DTD, los elementos se definen usando la declaración `<!ELEMENT>`:

Elementos con datos de texto (PCDATA): Si un elemento contiene solo texto, se usa `#PCDATA` (_Parsed Character Data_).

```xml
<!ELEMENT titulo (#PCDATA)>
```

Elementos que contienen otros elementos: Si un elemento contiene otros elementos, estos deben listarse dentro de paréntesis.

```xml
<!ELEMENT libro (titulo, autor, precio)>
```

### Atributos en DTD

Los atributos se definen con la declaración `<!ATTLIST>`. Puedes asignarles tipos y valores predeterminados.

```xml
<!ATTLIST precio moneda CDATA #IMPLIED>
```

Esto indica que el elemento `<precio>` puede tener un atributo _moneda_ de tipo CDATA (Character Data), pero no es obligatorio (#IMPLIED).

Tipos de atributos:

* __CDATA__: Caracteres de texto.
* __ID__: Un identificador único dentro del documento.
* __IDREF__: Hace referencia a un ID en otro lugar del documento.
* __Enumeraciones__: Una lista de valores posibles.

Ejemplo d euna enumeración:

```xml
<!ATTLIST producto categoria (libro | musica | video) "libro">
```

Explicación:
* `<!ATTLIST producto`: esto define una lista de atributos para el elemento producto. Los atributos proporcionan información adicional sobre el elemento en XML.
* `categoria`: es el nombre del atributo que se está definiendo. En este caso, el atributo categoria está asociado con el elemento `<producto>`.
* `(libro | musica | video)`: esta parte define los valores permitidos para el atributo categoria. El atributo categoria solo puede tomar uno de estos tres valores: libro, musica o video. Esto es lo que se llama una enumeración en DTD.
* `"libro"`: este es el valor por defecto del atributo categoria. Si no se especifica un valor para el atributo en el documento XML, el valor predeterminado será "libro".

__Uso de Wildcards (*, +, ?)__

Los wildcards o metacaracteres permiten definir cuántas veces puede aparecer un elemento en la estructura de DTD:

__Asterisco (*)__: indica que el elemento puede aparecer cero o más veces.

```xml
<!ELEMENT lista_libros (libro*)>
```

Esto significa que el elemento `<libro>` puede aparecer ninguna o múltiples veces dentro del elemento `<lista_libros>`.

__Más (+)__: indica que el elemento debe aparecer al menos una vez o más.

```xml
<!ELEMENT lista_libros (libro+)>
```

Aquí, al menos un `<libro>` debe estar presente en el elemento `<lista_libros>`.

__Interrogación (?)__: indica que el elemento es opcional y puede aparecer cero o una vez.

```xml
<!ELEMENT autor (biografia?)>
```

Esto significa que el elemento `<biografia>` es opcional y puede estar presente o no dentro de `<autor>`.

Ejemplo de documento DTD que contiene wildcards:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE biblioteca [
    <!ELEMENT biblioteca (libro+)>
    <!ELEMENT libro (titulo, autor?, precio)>
    <!ELEMENT titulo (#PCDATA)>
    <!ELEMENT autor (#PCDATA)>
    <!ELEMENT precio (#PCDATA)>
    <!ATTLIST precio moneda CDATA #IMPLIED>
]>
<biblioteca>
    <libro>
        <titulo>XML Básico</titulo>
        <autor>Juan Pérez</autor>
        <precio moneda="USD">25.00</precio>
    </libro>
    <libro>
        <titulo>Guía Avanzada de XML</titulo>
        <precio moneda="EUR">30.00</precio>
    </libro>
</biblioteca>
```

En este ejemplo:

* El elemento `<biblioteca>` debe contener al menos un elemento `<libro>`.
* Un `<libro>` debe tener un `<titulo>`, puede tener o no un `<autor>`, y debe tener un `<precio>`.
