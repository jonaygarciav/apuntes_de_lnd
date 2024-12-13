# XQuery

* Introducción
* Sintaxis Básica en XQuery
* Comandos y Funciones en XQuery
    * FOR
    * LET
    * WHERE
    * ORDER BY
    * RETURN
    * DOC()
* Ejercicio Resuelto

## Introducción

__XQuery__ (abreviatura de _XML Query Language_) es un lenguaje diseñado para consultar, transformar y manipular datos estructurados en formato XML. Es especialmente útil para trabajar con bases de datos XML, documentos grandes, y para realizar conversiones entre diferentes formatos como XML a JSON, HTML, o texto.

| **Nombre**          | **Versión** | **Año de Lanzamiento** | **Mejoras Introducidas**                                                                                                                |
|----------------------|-------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| **XQuery 1.0**       | 1.0         | 2007                    | Versión inicial del estándar, introdujo soporte básico para consultas y transformaciones de documentos XML.                              |
| **XQuery Update 1.0**| 1.0         | 2011                    | Añadió la capacidad de realizar actualizaciones a datos XML (modificar, insertar, borrar nodos).                                          |
| **XQuery 3.0**       | 3.0         | 2014                    | Introdujo expresiones funcionales, manejo mejorado de errores, nuevas funciones, y mejor integración con XPath 3.0.                      |
| **XQuery 3.1**       | 3.1         | 2017                    | Añadió soporte para JSON nativo, estructuras de datos complejas como mapas y arrays, y nuevas funciones para manejar datos no XML.        |
| **XQuery 4.0** (Draft)| 4.0        | En desarrollo           | (Propuesta) Extensiones funcionales, mejoras de rendimiento, nuevas funciones para trabajar con secuencias, datos dinámicos, y XPath 4.0. |

__XQuery 1.0 (2007)__:
* Primera versión oficial.
* Basado en XPath 2.0.
* Introdujo expresiones básicas como `for`, `let`, `where`, `order by`, y `return`.
* Diseñado principalmente para consultas sobre documentos XML.

__XQuery Update 1.0 (2011)__:
* Introdujo la capacidad de realizar operaciones de modificación en documentos XML:
* Insertar nodos: insert node.
* Eliminar nodos: delete node.
* Modificar valores: replace value of node.

__XQuery 3.0 (2014)__:
* Soporte para expresiones funcionales y recursión.
* Nuevas funciones como `fold-left()` y `fold-right()` para iteraciones avanzadas.
* Mejor manejo de errores.
* Introducción de las claves try y catch.

__XQuery 3.1 (2017)__:
* Soporte para manipulación de JSON y estructuras como mapas y arrays.
* Nuevas funciones como `json-to-xml()`, `xml-to-json()`, `array:append()`, `map:put()`.
* Compatibilidad mejorada con XPath 3.1.

## Sintaxis Básica en XQuery

Un programa XQuery típico sigue esta estructura:

```
for $variable in <fuente_de_datos>
let $otraVariable := <expresión>
where <condición>
order by <expresión>
return <resultado>
```

* `for`: itera sobre un conjunto de datos.
* `let`: asigna valores o cálculos a una variable.
* `where`: aplica filtros a los datos.
* `order by`: ordena los datos.
* `return`: Devuelve el resultado.

Además, XQuery utiliza la función `doc()` para cargar un documento XML.

## Comandos y Funciones en XQuery

### FOR

El comando `for` permite recorrer secuencias o listas de nodos.

Sintaxis:

```
for $variable in <fuente_de_datos>
return <expresión>
```

Ejemplo: dado el siguiente archivo XML (libros.xml):

```xml
<biblioteca>
  <libro>
    <titulo>1984</titulo>
    <autor>George Orwell</autor>
    <precio>19.99</precio>
  </libro>
  <libro>
    <titulo>Brave New World</titulo>
    <autor>Aldous Huxley</autor>
    <precio>14.99</precio>
  </libro>
</biblioteca>
```

Consulta: devuelve el titulo de cada uno de libros

```
for $libro in doc("libros.xml")/biblioteca/libro
return $libro/titulo
```

Resultado:

```
<titulo>1984</titulo>
<titulo>Brave New World</titulo>
```

### LET

El comando `let` se utiliza para asignar valores intermedios o cálculos a variables.

Sintaxis:

```
let $variable := <valor>
return <expresión>
```

Ejemplo: calcular un precio con descuento del 10%:

```
for $libro in doc("libros.xml")/biblioteca/libro
let $descuento := $libro/precio * 0.9
return <libro>
  <titulo>{$libro/titulo}</titulo>
  <precioDescuento>{$descuento}</precioDescuento>
</libro>
```

Resultado: calcula un descuento del 10% sobre su precio original y devuelve un nuevo XML con el título del libro y el precio descontado.

```
<libro>
  <titulo>1984</titulo>
  <precioDescuento>17.991</precioDescuento>
</libro>
<libro>
  <titulo>Brave New World</titulo>
  <precioDescuento>13.491</precioDescuento>
</libro>
```

### WHERE

El comando `where` aplica filtros o condiciones a los datos.

Sintaxis:

```
for $variable in <fuente_de_datos>
where <condición>
return <expresión>
```

Ejemplo: encontrar libros cuyo precio sea mayor a 15:

```
for $libro in doc("libros.xml")/biblioteca/libro
where $libro/precio > 15
return $libro/titulo
```

Resultado:

```
<titulo>1984</titulo>
```

### ORDER BY

El comando `order by` ordena los datos en función de una expresión.

Sintaxis:

```
for $variable in <fuente_de_datos>
order by <expresión> ascending|descending
return <expresión>
```

Ejemplo: ordenar libros por precio de menor a mayor:

```
for $libro in doc("libros.xml")/biblioteca/libro
order by $libro/precio ascending
return $libro/titulo
```

Resultado:

```
<titulo>Brave New World</titulo>
<titulo>1984</titulo>
```

### RETURN

El comando `return` define el resultado que se devolverá al usuario.

Sintaxis:

```
for $variable in <fuente_de_datos>
return <resultado>
```

Ejemplo: devolver los títulos y precios de los libros en formato XML:

```
for $libro in doc("libros.xml")/biblioteca/libro
return <libro>
  <titulo>{$libro/titulo}</titulo>
  <precio>{$libro/precio}</precio>
</libro>
```

Resultado:

```
<libro>
  <titulo>1984</titulo>
  <precio>19.99</precio>
</libro>
<libro>
  <titulo>Brave New World</titulo>
  <precio>14.99</precio>
</libro>
```

### DOC

La función `doc()` se utiliza para cargar un archivo XML.

Sintaxis:

```
doc("nombre_del_archivo.xml")
```

Ejemplo: cargar un archivo XML llamado libros.xml y devolver el nodo raíz:

```
doc("libros.xml")
```

Resultado:

```
<biblioteca>
  <libro>
    <titulo>1984</titulo>
    <autor>George Orwell</autor>
    <precio>19.99</precio>
  </libro>
  <libro>
    <titulo>Brave New World</titulo>
    <autor>Aldous Huxley</autor>
    <precio>14.99</precio>
  </libro>
</biblioteca>
```

## Ejercicio Resuelto

Dado el archivo catalogo.xml:

```xml
<catalogo>
  <producto id="1" categoria="Electrónica">
    <nombre>Portátil</nombre>
    <precio>800</precio>
  </producto>
  <producto id="2" categoria="Electrónica">
    <nombre>Monitor</nombre>
    <precio>200</precio>
  </producto>
  <producto id="3" categoria="Accesorios">
    <nombre>Ratón</nombre>
    <precio>25</precio>
  </producto>
</catalogo>
```

Ejercicio 1: devuelve los nombres de los productos.

Consulta:

```
for $producto in doc("catalogo.xml")/catalogo/producto
return $producto/nombre
```

Resultado:

```
<nombre>Portátil</nombre>
<nombre>Monitor</nombre>
<nombre>Ratón</nombre>
```

Ejercicio 2: filtra productos con precio mayor a 100.

Consulta:

```
for $producto in doc("catalogo.xml")/catalogo/producto
where $producto/precio > 100
return $producto/nombre
```

Resultado:

```
<nombre>Portátil</nombre>
<nombre>Monitor</nombre>
```

Ejercicio 3: ordena los productos por precio de menor a mayor.

Consulta:

```
for $producto in doc("catalogo.xml")/catalogo/producto
order by $producto/precio ascending
return $producto/nombre
```

Resultado:

```
<nombre>Ratón</nombre>
<nombre>Monitor</nombre>
<nombre>Portátil</nombre>
```

Ejercicio 4: calcula el precio total de todos los productos.
Consulta:

```
sum(doc("catalogo.xml")/catalogo/producto/precio)
```

Resultado:

```
1025
```

Ejercicio 5: devuelve los nombres y categorías de los productos.

Consulta:

```
for $producto in doc("catalogo.xml")/catalogo/producto
return <item>
  <nombre>{$producto/nombre}</nombre>
  <categoria>{$producto/@categoria}</categoria>
</item>
```

Resultado:

```
<item>
  <nombre>Portátil</nombre>
  <categoria>Electrónica</categoria>
</item>
<item>
  <nombre>Monitor</nombre>
  <categoria>Electrónica</categoria>
</item>
<item>
  <nombre>Ratón</nombre>
  <categoria>Accesorios</categoria>
</item>
```
