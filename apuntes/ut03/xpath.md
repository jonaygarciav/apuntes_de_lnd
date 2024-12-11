# XPath

* Introducción
* Elementos Básicos en XPath
    * Barra simple `\`
    * Barra doble `\\`
    * Arroba `@`
    * Asterisco `*`
    * Punto simple `.`
    * Punto doble `..`
    * Corchetes `[]`
    * Operador OR `|`
* Funciones en XPath
* Consultas XPath Comunes
    * Seleccionar nodos por su etiqueta
    * Filtrar nodos
    * Navegar por relaciones jerárquicas

# Introducción

__XPath__ es un lenguaje para navegar por documentos XML y seleccionar nodos en un árbol estructurado. Se utiliza comúnmente en combinación con XSLT, herramientas de pruebas (como Selenium) y para análisis de datos en aplicaciones basadas en XML y HTML.

Un documento XML se organiza como un árbol jerárquico, donde cada nodo puede ser:

* Un elemento `<tag>`.
* Un atributo `attribute="value"`.
* Texto contenido dentro de un elemento `<nombre>Steve</nombre>`.
* Comentarios u otros tipos de nodos `<!--- Students grades are uploaded by months --->`.
* Estructura del árbol en XPath

| Versión     | Nombre                  | Año de Lanzamiento | Descripción Breve                                |
|-------------|-------------------------|--------------------|-------------------------------------------------|
| XPath 1.0   | XPath 1.0               | 1999               | Versión inicial, usada en XSLT y XQuery.        |
| XPath 2.0   | XPath 2.0               | 2007               | Introducción de tipos de datos y funciones avanzadas. |
| XPath 3.0   | XPath 3.0               | 2014               | Soporte para funciones definidas por el usuario y expresiones dinámicas. |
| XPath 3.1   | XPath 3.1               | 2017               | Soporte para JSON y nuevos operadores de secuencias. |

__XPath 1.0 (1999)__

* Primera versión del estándar.
* Introducción de conceptos básicos como nodos, rutas absolutas (/), relativas (//), y filtros ([]).
* Soporte para tipos de nodos: elementos, atributos, texto, espacio de nombres, comentarios.
* Operadores numéricos básicos (+, -, *, div).
* Funciones de cadenas (contains(), substring(), string-length()).
* Funciones básicas de nodos (name(), count(), position()).

__XPath 2.0 (2007)__

* Introducción de un sistema de tipos basado en XML Schema.
* Nuevas funciones:
    * `distinct-values()`: Devuelve valores únicos.
    * `avg()` y `min()`: Cálculo de agregados.
    * Funciones avanzadas de cadenas como `matches()` y `replace()`.
* Operadores sobre secuencias (=, !=, <, >, intersect, except).
* Mayor integración con XQuery y XSLT 2.0.

__XPath 3.0 (2014)__

* Soporte para funciones definidas por el usuario.
* Nuevas expresiones dinámicas:
    * `if-then-else`.
    * Mapas y arrays como estructuras de datos.
* Expresiones en línea (lambda o funciones anónimas).
* Soporte para nodos nulos o vacíos con ().

__XPath 3.1 (2017)__

* Soporte para JSON:
    * Conversión entre JSON y XML.
    * Funciones como json-doc() y operadores para acceder a objetos JSON.
* Nuevos operadores para secuencias:
    * `!`: Aplicar una expresión a cada elemento.
    * `=>`: Operador de tubería (pipeline) para encadenar funciones.
    * Mejoras en el soporte para mapas y arrays.

Cuándo utilizar las diferentes versiones de XPath:

* __XPath 1.0__: ideal para transformaciones básicas y sistemas legados.
* __XPath 2.0 y 3.0__: usado en transformaciones avanzadas con XSLT 2.0/3.0 y en consultas complejas de XML.
* __XPath 3.1__: más adecuado para manejar datos modernos como JSON y realizar operaciones complejas en secuencias.

## Elementos Básicos en XPath

### Barra simple `/`

La barra simple `/` se utiliza para seleccionar nodos desde la raíz del documento. Cada paso adicional desciende un nivel en el árbol.

Ejemplo XML:

```xml
<library>
  <book>
    <title>1984</title>
    <author>George Orwell</author>
  </book>
  <book>
    <title>Brave New World</title>
    <author>Aldous Huxley</author>
  </book>
</library>
```

Seleccionar el nodo raíz:

```
/library
```

Resultado:

```xml
<library>
  ...
</library>
```

Seleccionar todos los nodos <book> hijos de <library>:

```
/library/book
```

Resultado:

```xml
<book>
  ...
</book>
<book>
  ...
</book>
```

### Barra doble `//`

La doble barra `//` selecciona nodos desde cualquier lugar del documento, sin importar su nivel en el árbol.

Seleccionar todos los nodos <book> en el documento:

```
//book
```

Resultado:

```xml
<book>
  ...
</book>
<book>
  ...
</book>
```

Seleccionar todos los nodos <title> en el documento:

```
//title
```

Resultado:

```xml
<title>1984</title>
<title>Brave New World</title>
```

Seleccionar todos los nodos <author> en cualquier parte del documento:

```
//author
```

Resultado:

```xml
<author>George Orwell</author>
<author>Aldous Huxley</author>
```

### Arroba `@`

El símbolo `@` se utiliza para seleccionar atributos de un nodo.

```xml
<library>
  <book id="1">
    <title>1984</title>
  </book>
  <book id="2">
    <title>Brave New World</title>
  </book>
</library>
```

Seleccionar todos los atributos id de los nodos <book>:

```
/library/book/@id
```

Resultado:

```
1
2
```

Seleccionar los nodos <book> cuyo atributo id es igual a "1":

```
/library/book[@id="1"]
```

Resultado:

```xml
<book id="1">
  <title>1984</title>
</book>
```

### Asterisco `*`

El asterisco `*` selecciona todos los nodos en un nivel específico.


Seleccionar todos los nodos hijos de <library>:

```
/library/*
```

Resultado:

```xml
<book id="1">
  ...
</book>
<book id="2">
  ...
</book>
```

Seleccionar todos los nodos en el documento:

```
//*
```

Resultado: Todos los nodos del documento.

### Punto simple `.`

El punto simple `.` se utiliza para seleccionar el nodo actual.

Seleccionar el nodo actual (si es <book>):

```
.
```

### Punto doble `..`

El doble punto `..` se utiliza para seleccionar el nodo padre del nodo actual.

Seleccionar el nodo <library> desde un nodo <book>:

```
/library/book/..
```

Resultado:

```xml
<library>
  ...
</library>
```

### Los corchetes `[]`

Los corchetes `[]` se usan para aplicar condiciones o filtros.

Seleccionar el primer nodo <book>:

```
/library/book[1]
```

Resultado:

```xml
<book id="1">
  ...
</book>
```

Seleccionar los nodos <book> cuyo atributo id es mayor a 1:

```
/library/book[@id > 1]
```

Resultado:

```xml
<book id="2">
  ...
</book>
```

Seleccionar nodos <book> donde <title> contenga la palabra "1984":

```
/library/book[title="1984"]
```

Resultado:

```xml
<book id="1">
  <title>1984</title>
</book>
```

### Operador OR `|`

El operador OR `|` se utiliza para combinar múltiples consultas XPath.

Seleccionar todos los nodos <title> y <author>:

```
//title | //author
```

Resultado:

```xml
<title>1984</title>
<title>Brave New World</title>
<author>George Orwell</author>
<author>Aldous Huxley</author>
```

## Funciones en XPath

* `text()`: selecciona el contenido textual de un nodo.
* `last()`: selecciona el último nodo de un conjunto.
* `count()`: devuelve el número total de nodos en un conjunto.
* `avg()`: devuelve el promedio de los valores en un conjunto de nodos.
* `sum()`: devuelve la suma de todos los valores en un conjunto de nodos.
* `min()`: devuelve el valor mínimo de un conjunto de nodos o números.
* `max()`: devuelve el valor máximo de un conjunto de nodos o números.
* `concat()`: concatena dos o más cadenas.
* `distinct-values()`: devuelve valores únicos de un conjunto de nodos o expresiones

## Consultas XPath Comunes

Ejemplo XML completo:

```xml
<store>
  <categories>
    <category id="1" name="Books">
      <item id="101">
        <name>The Great Gatsby</name>
        <author>F. Scott Fitzgerald</author>
        <price currency="USD">10.99</price>
        <stock>35</stock>
      </item>
      <item id="102">
        <name>1984</name>
        <author>George Orwell</author>
        <price currency="USD">8.99</price>
        <stock>12</stock>
      </item>
    </category>
    <category id="2" name="Electronics">
      <item id="201">
        <name>Smartphone</name>
        <brand>BrandX</brand>
        <price currency="USD">699.99</price>
        <stock>50</stock>
      </item>
      <item id="202">
        <name>Laptop</name>
        <brand>BrandY</brand>
        <price currency="USD">999.99</price>
        <stock>10</stock>
      </item>
    </category>
  </categories>
</store>
```

### Seleccionar nodos por su etiqueta

Seleccionar el nodo raíz `<store>`:

```
/store
```

Resultado:

```xml
<store>
...
</store>
```

Seleccionar todos los elementos `<category>`:

```
/store/categories/category
```

Resultado:

```xml
<category id="1" name="Books">
  ...
</category>
<category id="2" name="Electronics">
  ...
</category>
```

Seleccionar todos los elementos `<item>` en todas las categorías:

```
/store/categories/category/item
```

Resultado:

```xml
<item id="101">
  ...
</item>
<item id="102">
  ...
</item>
<item id="201">
  ...
</item>
<item id="202">
  ...
</item>
```

### Filtrar nodos

Seleccionar elementos `<item>` con un atributo `id="101"`:

```
//item[@id="101"]
```

Resultado:

```xml
<item id="101">
  <name>The Great Gatsby</name>
  <author>F. Scott Fitzgerald</author>
  <price currency="USD">10.99</price>
  <stock>35</stock>
</item>
```

Seleccionar todos los elementos `<category>` cuyo atributo _name_ tiene el valor "Electronics":

```
//category[@name="Electronics"]
```

Resultado:

```xml
<category id="2" name="Electronics">
  ...
</category>
```

Seleccionar todos los elementos `<item>` cuyo precio es mayor a _10.00_ (en texto):

```
//item[price > 10.00]
```

Resultado:

```xml
<item id="201">
  ...
</item>
<item id="202">
  ...
</item>
```

### Uso de funciones avanzadas

Seleccionar texto del primer elemento `<name>` dentro de `Books`:

```
/store/categories/category[@name="Books"]/item[1]/name/text()
```

Resultado:

```
The Great Gatsby
```

Seleccionar el atributo `currency` de todos los precios:

```
//price/@currency
```

Resultado:

```
USD
USD
USD
USD
```

Contar cuántos nodos `<item>` hay en total:

```
count(//item)
```

Resultado:

```
4
```

Seleccionar todos los elementos cuyo stock sea menor a 20:

```
//item[stock < 20]
```

Resultado:

```xml
<item id="102">
  <name>1984</name>
  <author>George Orwell</author>
  <price currency="USD">8.99</price>
  <stock>12</stock>
</item>
<item id="202">
  <name>Laptop</name>
  <brand>BrandY</brand>
  <price currency="USD">999.99</price>
  <stock>10</stock>
</item>
```

### Navegar por relaciones jerárquicas

Seleccionar todos los elementos `<item>` que son hijos de `<category>`:

```
/store/categories/category/item
```

Resultado:

```xml
<item id="101">
  <name>The Great Gatsby</name>
  <author>F. Scott Fitzgerald</author>
  <price currency="USD">10.99</price>
  <stock>35</stock>
</item>
<item id="102">
  <name>1984</name>
  <author>George Orwell</author>
  <price currency="USD">8.99</price>
  <stock>12</stock>
</item>
<item id="201">
  <name>Smartphone</name>
  <brand>BrandX</brand>
  <price currency="USD">699.99</price>
  <stock>50</stock>
</item>
<item id="202">
  <name>Laptop</name>
  <brand>BrandY</brand>
  <price currency="USD">999.99</price>
  <stock>10</stock>
</item>
```

Seleccionar el nodo padre del elemento que contenga una etiqueta `<name>` cuyo valor sea `1984`:

```
//item[name="1984"]/..
```

Resultado:

```xml
<category id="1" name="Books">
  ...
</category>
```
