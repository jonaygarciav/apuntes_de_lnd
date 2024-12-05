Xpath

# Introducción

__XPath__ es un lenguaje para navegar por documentos XML y seleccionar nodos en un árbol estructurado. Se utiliza comúnmente en combinación con XSLT, herramientas de pruebas (como Selenium) y para análisis de datos en aplicaciones basadas en XML y HTML.

Un documento XML se organiza como un árbol jerárquico, donde cada nodo puede ser:

* Un elemento `<tag>`.
* Un atributo `attribute="value".
* Texto contenido dentro de un elemento.
* Comentarios u otros tipos de nodos.
* Estructura del árbol en XPath

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
