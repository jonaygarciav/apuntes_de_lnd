# Validación de Documentos XML con DTD

* Introducción
* Tipos de DTD
    * DTD interno
    * DTD externo
* Definición de elementos dentro de un DTD
* Elementos dentro de un DTD
* Atributos dentro de un DTD
    * Parámetros de Valor Predeterminado
* Uso de Wildcards (*, +, ?)

## Introducción

Un documento XML es válido cuando sigue las reglas definidas en un __DTD__ o un esquema __XSD__. Es decir, además de estar bien formado, el contenido debe cumplir con una estructura previamente definida que determine qué elementos y atributos son permitidos y en qué orden deben aparecer.

Un __DTD__ (_Document Type Definition_) es un conjunto de reglas que define la estructura y las relaciones entre los elementos, atributos y entidades dentro de un documento XML. Un DTD puede estar interno (dentro del propio documento XML) o externo (definido en un archivo aparte). Su principal objetivo es validar que los documentos XML cumplen con un formato o estructura específica.

Existen dos tipos de DTD: `interno` y `externo`.

## Tipos de DTD

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

## Elementos dentro de un DTD

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

## Atributos dentro de un DTD

En un DTD, los atributos se definen con la declaración <!ATTLIST>, que tiene la siguiente sintaxis:

```
<!ATTLIST nombre_elemento nombre_atributo tipo_atributo valor_predeterminado>
```

* __nombre_elemento__: el elemento XML al que pertenece el atributo.
* __nombre_atributo__: el nombre del atributo.
* __tipo_atributo__: el tipo de datos del atributo. Puede ser:
    * _CDATA_: caracteres de texto.
    * _ID_: un identificador único en el documento, asignado a un elemento. Cada valor de ID debe ser único en todo el documento XML.
    * _IDREF_: permite que un atributo se refiera a un ID de otro elemento en el mismo documento XML, estableciendo así una referencia entre ellos. IDREF se usa cuando solo se necesita una referencia a un único ID.
    * _IDREFS_: similar a IDREF, pero permite referencias múltiples a varios ID separados por espacios.
    * _Enumeraciones_: permite definir un atributo que tiene un conjunto de valores posibles. Esto es útil cuando queremos limitar el valor de un atributo a opciones específicas, como una lista de opciones (por ejemplo, colores, estados o categorías).
* __valor_predeterminado__: indica si el atributo es obligatorio, tiene un valor predeterminado, o es opcional.

### Parámetros de Valor Predeterminado

`#REQUIRED` es un parámetro que especifica que el atributo es obligatorio en el documento XML. Si un atributo está marcado como `#REQUIRED` y no está presente en un elemento, el documento XML no cumplirá con el DTD.

Ejemplo:

```
<!ELEMENT empleado (nombre, cargo)>
<!ATTLIST empleado id ID #REQUIRED>
```

En este ejemplo:
* El elemento empleado debe tener un atributo id único (de tipo ID).
* id es obligatorio (#REQUIRED), por lo que todos los elementos <empleado> en el XML deben incluirlo.

`#IMPLIED` es un parámetro que indica que el atributo es opcional. Si el atributo no está presente en un elemento, el documento seguirá siendo válido, aplicándose que el valor es nulo o sin contenido.

Ejemplo:

```
<!ELEMENT empleado (nombre, cargo)>
<!ATTLIST empleado telefono CDATA #IMPLIED>
```

En este ejemplo:
* El elemento empleado puede tener un atributo telefono de tipo CDATA (texto).
* telefono es opcional (#IMPLIED), por lo que no es obligatorio incluirlo en el elemento <empleado>.

Se puede asignar un `valor predeterminado` al atributo en el DTD. Si el atributo no está presente en el documento XML, el parser le asignará este valor predeterminado.

Ejemplo:

```xml
<!ELEMENT empleado (nombre, cargo)>
<!ATTLIST empleado departamento CDATA "General">
```

En este ejemplo:
* El elemento empleado tiene un atributo departamento de tipo CDATA.
* Si el atributo departamento no está presente en el elemento <empleado>, el parser asignará el valor "General" como  valor predeterminado.

Ejemplo completo de DTD con `#REQUIRED` y `#IMPLIED`:

```xml
<!ELEMENT empleado (nombre, cargo)>
<!ELEMENT nombre (#PCDATA)>
<!ELEMENT cargo (#PCDATA)>
<!ATTLIST empleado
  id ID #REQUIRED
  telefono CDATA #IMPLIED
  departamento CDATA "General">
```

Explicación del ejemplo:
* `<empleado>`: define un elemento empleado que contiene los elementos nombre y cargo.
* `id (#REQUIRED)`: este atributo es obligatorio para el elemento empleado. Cada empleado debe tener un id único.
* `telefono (#IMPLIED)`: es opcional, por lo que puede o no estar presente en cada elemento empleado.
* `departamento (valor predeterminado: "General")`: este atributo es opcional. Si no se especifica un valor en el XML, automáticamemte el parser le asignará el valor "General".

Ejemplo del XML que cumple con el DTD: 

```xml
<empleados>
  <empleado id="E001" telefono="555-1234">
    <nombre>Ana López</nombre>
    <cargo>Gerente</cargo>
  </empleado>
  <empleado id="E002">
    <nombre>Juan Pérez</nombre>
    <cargo>Asistente</cargo>
    <!-- El atributo "departamento" usará su valor predeterminado "General" -->
  </empleado>
</empleado>
```

En este XML:
* El primer empleado tiene un _id_ y _telefono_ definidos.
* El segundo empleado tiene solamente el _id_. El atributo _departamento_ tomará el valor predeterminado "General".

Ejemplo de `ID` y `IDREF`:

Imaginemos un ejemplo de un documento XML que modela una biblioteca, donde los libros están relacionados con autores a través de identificadores.

```xml
<!ELEMENT biblioteca (libro+, autor+)>

<!ELEMENT libro (titulo)>
<!ATTLIST libro
  id ID #REQUIRED
  autorID IDREF #REQUIRED>

<!ELEMENT titulo (#PCDATA)>

<!ELEMENT autor (nombre)>
<!ATTLIST autor
  id ID #REQUIRED>

<!ELEMENT nombre (#PCDATA)>
```

* __libro__: define un elemento libro con un atributo id de tipo ID que debe ser único. También tiene un atributo autorID de tipo IDREF, que referencia el ID de un autor.
* __autor__: define un elemento autor con un atributo id de tipo ID, que debe ser único y que puede ser referenciado por autorID en libro.

XML válido para el DTD anterior:

```xml
<biblioteca>
  <libro id="B001" autorID="A001">
    <titulo>La Odisea</titulo>
  </libro>
  <libro id="B002" autorID="A002">
    <titulo>Don Quijote</titulo>
  </libro>
  <autor id="A001">
    <nombre>Homero</nombre>
  </autor>
  <autor id="A002">
    <nombre>Miguel de Cervantes</nombre>
  </autor>
</biblioteca>
```

En este XML:
* El libro con id="B001" referencia al autor con id="A001", estableciendo que Homero es el autor de La Odisea.
* El libro con id="B002" referencia al autor con id="A002", estableciendo que Miguel de Cervantes es el autor de Don Quijote.

Ejemplo de `IDREFS`:

Si un libro tiene varios autores, podemos usar IDREFS para permitir que el atributo autorID contenga múltiples ID separados por espacios.

```xml
<!ATTLIST libro
  id ID #REQUIRED
  autorID IDREFS #REQUIRED>
```

XML Válido para el DTD anterior:

```xml
<biblioteca>
  <libro id="B001" autorID="A001 A002">
    <titulo>Libro Co-escrito</titulo>
  </libro>
  <autor id="A001">
    <nombre>Autor Uno</nombre>
  </autor>
  <autor id="A002">
    <nombre>Autor Dos</nombre>
  </autor>
</biblioteca>
```

Aquí, el libro con id="B001" está referenciando dos autores, A001 y A002, permitiendo múltiples referencias con el atributo de tipo IDREFS.

Ejemplo de una `enumeración`:

```xml
<!ATTLIST producto categoria (libro | musica | video) "libro">
```

Explicación:
* `<!ATTLIST producto`: esto define una lista de atributos para el elemento producto. Los atributos proporcionan información adicional sobre el elemento en XML.
* `categoria`: es el nombre del atributo que se está definiendo. En este caso, el atributo categoria está asociado con el elemento `<producto>`.
* `(libro | musica | video)`: esta parte define los valores permitidos para el atributo categoria. El atributo categoria solo puede tomar uno de estos tres valores: libro, musica o video. Esto es lo que se llama una enumeración en DTD.
* `"libro"`: este es el valor por defecto del atributo categoria. Si no se especifica un valor para el atributo en el documento XML, el valor predeterminado será "libro".


## Uso de Wildcards (*, +, ?)

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
