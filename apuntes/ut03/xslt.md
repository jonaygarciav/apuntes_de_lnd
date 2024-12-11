# XSLT (Extensible Stylesheet Language Transformations)

* Introducción
* Elementos Principales de XSLT
* Transformar XML en HTML
* Transformar XML en JSON

## Introducción

__XSLT__ (_Extensible Stylesheet Language Transformations_) es un lenguaje basado en XML diseñado para transformar documentos XML en otros formatos, como HTML, texto plano o incluso otro XML. XSLT permite estructurar, filtrar, y estilizar datos de documentos XML de forma programática.

XSLT utiliza XPath para seleccionar partes específicas del documento XML y definir cómo deben transformarse o mostrarse.

| Versión     | Año de Lanzamiento | Descripción Breve                                                                                |
|-------------|--------------------|--------------------------------------------------------------------------------------------------|
| XSLT 1.0    | 1999               | Versión inicial, centrada en la transformación de XML a otros formatos como HTML y texto plano.  |
| XSLT 2.0    | 2007               | Introducción de soporte para XPath 2.0, manejo avanzado de datos, y procesamiento de XML Schema. |
| XSLT 3.0    | 2017               | Soporte para XPath 3.1, JSON, y procesamiento basado en funciones y programación modular.        |

__XSLT 1.0 (1999)__

* Primera versión del estándar.
* Introducción de plantillas `<xsl:template>`, bucles `<xsl:for-each>`, y transformaciones básicas.
* Uso exclusivo de XPath 1.0 para consultas y selección de nodos.
* Limitado a transformaciones de XML a HTML, texto plano, o XML estructurado.

__XSLT 2.0 (2007)__

* Soporte para XPath 2.0 con tipos de datos basados en XML Schema.
* Nuevas funciones como manejo de cadenas y operaciones matemáticas avanzadas.
* Introducción de secuencias y tipos estáticos para validación.
* Mejor integración con XQuery.

__XSLT 3.0 (2017)__:

* Soporte para XPath 3.1, incluyendo funciones avanzadas para JSON.
* Introducción de nuevas características como:
* Modo funcional (funciones como ciudadanos de primera clase).
* Procesamiento basado en plantillas dinámicas y pipelines.
* Mejora en la modularidad y reutilización del código.

## Arquitectura Básica de XSLT

Un archivo XSLT tiene las siguientes características principales:

1. Es un documento XML con la etiqueta raíz `<xsl:stylesheet>` o `<xsl:transform>`.
2. Incluye plantillas `<xsl:template>` que definen cómo procesar cada parte del XML.
3. Usa XPath para seleccionar y manipular nodos.

Estructura básica:

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
  <xsl:output method="html" indent="yes"/>
  
  <!-- Plantilla raíz -->
  <xsl:template match="/">
    <!-- Contenido transformado -->
  </xsl:template>
</xsl:stylesheet>
```

## Elementos Principales de XSLT

`<xsl:template>`

Define cómo procesar un conjunto de nodos. La plantilla puede coincidir con:

* La raíz (/).
* Un nodo específico (/library).
* Todos los nodos de un tipo (//item).

Ejemplo:

```xml
<xsl:template match="/">
  <html>
    <body>
      <h1>Library Items</h1>
    </body>
  </html>
</xsl:template>
```

`<xsl:value-of>`

Extrae el valor de un nodo seleccionado con una expresión XPath.

Ejemplo:

```xml
<xsl:value-of select="library/item/title"/>
```

`<xsl:for-each>`

Permite iterar sobre un conjunto de nodos seleccionados con XPath.

Ejemplo:

```xml
<xsl:for-each select="library/item">
  <p><xsl:value-of select="title"/></p>
</xsl:for-each>
```

`<xsl:if>`

Condición que muestra contenido solo si una expresión XPath es verdadera.

Ejemplo:

```xml
<xsl:if test="price > 20">
  <p>Expensive item</p>
</xsl:if>
```

`<xsl:choose>`

Estructura condicional similar a if-else.

Ejemplo:

```xml
<xsl:choose>
  <xsl:when test="price > 20">
    <p>Expensive</p>
  </xsl:when>
  <xsl:otherwise>
    <p>Affordable</p>
  </xsl:otherwise>
</xsl:choose>
```

`<xsl:apply-templates>`

Procesa un conjunto de nodos utilizando plantillas definidas en el documento XSLT.

Ejemplo:

```xml
<xsl:apply-templates select="library/item"/>
```

## Transformar XML en HTML

Dado el siguiente XML:

```xml
<library>
  <item id="1">
    <title>1984</title>
    <author>George Orwell</author>
    <price>15.99</price>
  </item>
  <item id="2">
    <title>To Kill a Mockingbird</title>
    <author>Harper Lee</author>
    <price>10.99</price>
  </item>
</library>
```

Transformación XSLT:

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
  <xsl:output method="html" indent="yes"/>
  
  <!-- Plantilla raíz -->
  <xsl:template match="/">
    <html>
      <head>
        <title>Library</title>
      </head>
      <body>
        <h1>Library Catalog</h1>
        <table border="1">
          <tr>
            <th>Title</th>
            <th>Author</th>
            <th>Price</th>
          </tr>
          <xsl:for-each select="library/item">
            <tr>
              <td><xsl:value-of select="title"/></td>
              <td><xsl:value-of select="author"/></td>
              <td><xsl:value-of select="price"/></td>
            </tr>
          </xsl:for-each>
        </table>
      </body>
    </html>
  </xsl:template>
</xsl:stylesheet>
```

Resultado HTML:

```html
<html>
  <head>
    <title>Library</title>
  </head>
  <body>
    <h1>Library Catalog</h1>
    <table border="1">
      <tr>
        <th>Title</th>
        <th>Author</th>
        <th>Price</th>
      </tr>
      <tr>
        <td>1984</td>
        <td>George Orwell</td>
        <td>15.99</td>
      </tr>
      <tr>
        <td>To Kill a Mockingbird</td>
        <td>Harper Lee</td>
        <td>10.99</td>
      </tr>
    </table>
  </body>
</html>
```

## Transformar XML en JSON

Ejemplo de XML:

```xml
<library>
  <book id="1">
    <title>1984</title>
    <author>George Orwell</author>
    <price>15.99</price>
  </book>
  <book id="2">
    <title>Brave New World</title>
    <author>Aldous Huxley</author>
    <price>12.49</price>
  </book>
</library>
```

Transformación XSLT:

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:xs="http://www.w3.org/2001/XMLSchema"
                exclude-result-prefixes="xs"
                version="3.0">

  <xsl:output method="json" indent="yes"/>

  <xsl:template match="/">
    <xsl:map>
      <xsl:map-entry key="library">
        <xsl:array>
          <xsl:for-each select="library/book">
            <xsl:map>
              <xsl:map-entry key="id" select="@id"/>
              <xsl:map-entry key="title" select="title"/>
              <xsl:map-entry key="author" select="author"/>
              <xsl:map-entry key="price" select="price"/>
            </xsl:map>
          </xsl:for-each>
        </xsl:array>
      </xsl:map-entry>
    </xsl:map>
  </xsl:template>

</xsl:stylesheet>
```

Resultado JSON:

```json
{
  "library": [
    {
      "id": "1",
      "title": "1984",
      "author": "George Orwell",
      "price": "15.99"
    },
    {
      "id": "2",
      "title": "Brave New World",
      "author": "Aldous Huxley",
      "price": "12.49"
    }
  ]
}
```