# Introducción a XML

* Introducción
* Documentos XML
* Estructura jerárquica de un documento XML
* Modelo de datos de un documento XML: Tipos de nodos
* Corrección sintáctica: documentos XML bien formados


## Introducción

__XML__ (_eXtensible Markup Language_) es un lenguaje de marcado utilizado para definir estructuras de datos. Su principal ventaja es que es legible tanto por humanos como por máquinas y se puede utilizar para transportar datos entre sistemas de manera sencilla. XML permite definir etiquetas personalizadas, proporcionando una forma flexible de estructurar y almacenar datos. A diferencia de HTML, que está diseñado para presentar información en un navegador web, XML es un lenguaje de propósito general que no tiene un conjunto de etiquetas predefinidas.

## Documentos XML

Un documento XML es un archivo de texto que contiene datos estructurados en una jerarquía de elementos. Estos documentos comienzan con una declaración XML que define la versión del lenguaje XML que se está utilizando y la codificación de caracteres.

Ejemplo básico de un documento XML:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<libro>
    <titulo>Aprendiendo XML</titulo>
    <autor>Juan Pérez</autor>
    <precio moneda="USD">30.50</precio>
</libro>
```

Este documento describe un libro con un título, un autor y un precio. Es un ejemplo de cómo XML almacena datos jerárquicamente en elementos.

## Estructura jerárquica de un documento XML

Un documento XML sigue una estructura jerárquica similar a un árbol. Tiene un nodo raíz que contiene todos los demás elementos. Los elementos hijos son nodos que pueden contener otros nodos hijos o atributos.

Ejemplo:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<empresa>
    <empleado>
        <nombre>Carlos</nombre>
        <departamento>Ingeniería</departamento>
    </empleado>
    <empleado>
        <nombre>Ana</nombre>
        <departamento>Recursos Humanos</departamento>
    </empleado>
</empresa>
```

En este caso, `<empresa>` es el nodo raíz que contiene varios elementos `<empleado>`, cada uno con sus propios hijos: `<nombre>` y `<departamento>`.

## Modelo de datos de un documento XML: Tipos de nodos

En XML, los datos están representados como una estructura de nodos que puede incluir varios tipos, cada uno con su función:

__Nodo de elemento__: estos son los nodos principales que representan una etiqueta XML y contienen otros nodos anidados:

```xml
<editorial>
    <nombre>Editorial Tech</nombre>
    <año>2022</año>
    <ubicacion>Pensilvania, EE.UU.</ubicacion>
</editorial>
```

__Nodo de texto__: contiene el texto dentro de un elemento XML.

```xml
<autor>Pedro Gómez</autor>
```

__Nodo de atributo__: son nodos que contienen atributos con información adicional que está asociada al elemento.

```xml
<precio moneda="EUR">25.50</precio>
```

__Nodo de comentario__: son notas o descripciones que no afectan el contenido, útiles para anotaciones.

```xml
<!-- Este es un documento XML sobre libros -->
```

__Nodo de declaración de procesamiento__: instrucciones que le dicen a la aplicación cómo manejar los datos.

```xml
<?xml-stylesheet type="text/xsl" href="libros.xsl"?>
```

__Nodo de documento__: el nodo raíz de todo el documento XML, que encapsula todos los demás nodos.

```xml
<libro>
    <titulo>Guía de XML</titulo>
    <autor>Pedro Gómez</autor>
    ...
</libro>
```

A continuación, un ejemplo completo:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!-- Este es un documento XML sobre libros -->
<libro>
    <titulo>Guía de XML</titulo>
    <autor>Pedro Gómez</autor>
    <precio moneda="USD">45.00</precio>
    <!-- El libro está en dólares -->
    <editorial>
        <nombre>Editorial Tech</nombre>
        <año>2022</año>
        <ubicacion>Pensilvania, EE.UU.</ubicacion>
    </editorial>
</libro>
```

## Corrección sintáctica: documentos XML bien formados

Para que un documento XML esté bien formado, debe cumplir con las siguientes reglas:

1. Tener un único elemento raíz que encapsule todos los demás elementos.
2. Todas las etiquetas de apertura deben tener su correspondiente etiqueta de cierre.
3. Las etiquetas deben estar correctamente anidadas.
4. Los atributos deben estar entre comillas.
5. XML es sensible a las mayúsculas y minúsculas.

Ejemplo de un documento XML bien formado:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persona>
    <nombre>María</nombre>
    <edad>28</edad>
    <correo electrónico="maria@example.com"/>
</persona>
```

La cabecera XML no es estrictamente obligatoria para que un documento sea considerado bien formado, pero es altamente recomendable incluirla. La cabecera es esta línea que suele estar al principio de los documentos XML. Si incluimos la cabecera en un documento XML, tener en cuenta que el único atributo obligatorio en la cabecera es el atributo _version_.

El único atributo obligatorio en la cabecera de un documento XML es `<version>`. Este atributo especifica la versión del estándar XML que está utilizando el documento.

```xml
<?xml version="1.0"?>
```

A continuación, se muestran los tres atributos que se pueden añadir a la cabecera XML:

* `<version>` (obligatorio): Indica la versión de XML utilizada en el documento. La versión más común es `1.0`, aunque también existe la versión `1.1`.
* `<encoding>` (opcional pero recomendado): define la codificación de caracteres que se utiliza en el documento (como `UTF-8` o `ISO-8859-1`). Aunque no es obligatorio, es muy recomendable incluirlo, sobre todo si el documento contiene caracteres fuera del conjunto ASCII estándar.
* `<standalone>` (opcional): indica si el documento depende de un DTD externo o no. Puede tener los valores `yes` o `no`. Si no se especifica, el valor por defecto es no.

Ejemplo de cabecera XML con los tres atributos:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
```

> __Nota__: en resumen, el único atributo obligatorio es version, pero encoding es muy recomendable para evitar problemas de interpretación de caracteres.
