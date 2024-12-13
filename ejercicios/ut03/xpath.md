# XPath (Ejercicios)

__Ejercicio 1__. Tienda de Libros

```xml
<bookstore>
  <book id="101">
    <title>Clean Code</title>
    <author>Robert C. Martin</author>
    <genre>Programming</genre>
    <price currency="USD">32.99</price>
    <stock>20</stock>
  </book>
  <book id="102">
    <title>The Pragmatic Programmer</title>
    <author>Andrew Hunt</author>
    <genre>Programming</genre>
    <price currency="USD">40.50</price>
    <stock>15</stock>
  </book>
  <book id="103">
    <title>1984</title>
    <author>George Orwell</author>
    <genre>Fiction</genre>
    <price currency="USD">12.99</price>
    <stock>50</stock>
  </book>
  <book id="104">
    <title>The Art of War</title>
    <author>Sun Tzu</author>
    <genre>Philosophy</genre>
    <price currency="USD">9.99</price>
    <stock>30</stock>
  </book>
  <book id="105">
    <title>Thinking, Fast and Slow</title>
    <author>Daniel Kahneman</author>
    <genre>Psychology</genre>
    <price currency="USD">20.00</price>
    <stock>10</stock>
  </book>
</bookstore>
```

_Pregunta 1_. Selecciona todos los títulos de los libros.

_Pregunta 2_. Selecciona los autores de los libros en el género "Programming".

_Pregunta 3_. Selecciona el precio del libro "The Art of War".

_Pregunta 4_. Cuenta cuántos libros tienen más de 20 en stock.

_Pregunta 5_. Selecciona todos los géneros únicos disponibles en la tienda.

_Pregunta 6_. Selecciona el autor cuyo libro cuesta más.

_Pregunta 7_. Selecciona el título del libro más barato.

_Pregunta 8_. Selecciona todos los libros cuyo precio esté entre 10 y 30.

_Pregunta 9_. Selecciona todos los libros que tengan menos de 20 unidades en stock.

_Pregunta 10_. Selecciona el atributo id de todos los libros.

__Ejercicio 2__. Tienda de electrónica.

```xml
<electronics>
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
  <item id="203">
    <name>Tablet</name>
    <brand>BrandX</brand>
    <price currency="USD">399.99</price>
    <stock>25</stock>
  </item>
  <item id="204">
    <name>Headphones</name>
    <brand>BrandZ</brand>
    <price currency="USD">199.99</price>
    <stock>100</stock>
  </item>
</electronics>
```

__Pregunta 1__. Selecciona todos los nombres de productos.

__Pregunta 2__. Selecciona los productos de la marca "BrandX".

__Pregunta 3__. Selecciona el producto más barato.

__Pregunta 4__. Selecciona el producto más caro.

__Pregunta 5__. Selecciona los nombres y precios de productos con más de 30 unidades en stock.

__Pregunta 6__. Selecciona el atributo currency de todos los precios.

__Pregunta 7__. Cuenta cuántos productos hay en stock con menos de 20 unidades.

__Pregunta 8__. Selecciona los nombres de todos los productos cuyo precio sea mayor a 500.

__Pregunta 9__. Selecciona los nombres de productos con el atributo id mayor a 202.

__Pregunta 10__. Selecciona todos los nodos completos de productos con "BrandZ".


__Ejercicio 3__. Biblioteca digital.

```xml
<library>
  <book id="301">
    <title>The Catcher in the Rye</title>
    <author>J.D. Salinger</author>
    <genre>Fiction</genre>
    <available>true</available>
  </book>
  <book id="302">
    <title>To Kill a Mockingbird</title>
    <author>Harper Lee</author>
    <genre>Fiction</genre>
    <available>false</available>
  </book>
  <book id="303">
    <title>The Great Gatsby</title>
    <author>F. Scott Fitzgerald</author>
    <genre>Fiction</genre>
    <available>true</available>
  </book>
  <book id="304">
    <title>1984</title>
    <author>George Orwell</author>
    <genre>Dystopian</genre>
    <available>true</available>
  </book>
  <book id="305">
    <title>Moby Dick</title>
    <author>Herman Melville</author>
    <genre>Adventure</genre>
    <available>false</available>
  </book>
</library>
```

__Pregunta 1__. Selecciona todos los títulos de los libros.

__Pregunta 2__. Selecciona todos los libros disponibles (con available="true").

__Pregunta 3__. Selecciona el autor del libro "1984".

__Pregunta 4__. Selecciona todos los géneros de libros únicos.

__Pregunta 5__. Cuenta cuántos libros están disponibles.

__Pregunta 6__. Selecciona los títulos de los libros que no están disponibles.

__Pregunta 7__. Selecciona los autores cuyos libros están disponibles.

__Pregunta 8__. Selecciona el ID del libro "The Great Gatsby".

__Pregunta 9__. Selecciona todos los libros del género "Fiction".

__Pregunta 10__. Selecciona los títulos de los libros cuyo autor es "Herman Melville".

__Ejercicio 4__. Catálogo de Música

```xml
<musicCatalog>
  <album id="101">
    <title>Thriller</title>
    <artist>Michael Jackson</artist>
    <genre>Pop</genre>
    <price currency="USD">15.99</price>
    <stock>50</stock>
  </album>
  <album id="102">
    <title>The Dark Side of the Moon</title>
    <artist>Pink Floyd</artist>
    <genre>Rock</genre>
    <price currency="USD">20.99</price>
    <stock>30</stock>
  </album>
  <album id="103">
    <title>Back in Black</title>
    <artist>AC/DC</artist>
    <genre>Rock</genre>
    <price currency="USD">18.50</price>
    <stock>25</stock>
  </album>
  <album id="104">
    <title>21</title>
    <artist>Adele</artist>
    <genre>Pop</genre>
    <price currency="USD">12.99</price>
    <stock>100</stock>
  </album>
  <album id="105">
    <title>Abbey Road</title>
    <artist>The Beatles</artist>
    <genre>Rock</genre>
    <price currency="USD">19.99</price>
    <stock>10</stock>
  </album>
</musicCatalog>
```

__Pregunta 1__. Selecciona todos los títulos de los álbumes.

__Pregunta 2__. Selecciona los títulos de los álbumes del género "Rock".

__Pregunta 3__. Selecciona el precio del álbum "21".

__Pregunta 4__. Cuenta cuántos álbumes tienen más de 20 en stock.

__Pregunta 5__. Selecciona los nombres de los artistas cuyos álbumes cuestan más de 18 USD.

__Pregunta 6__. Selecciona el álbum más caro.

__Pregunta 7__. Selecciona el género del álbum "Thriller".

__Pregunta 8__. Selecciona el ID de todos los álbumes de la artista "Adele".

__Pregunta 9__. Selecciona los álbumes con menos de 30 en stock.

__Pregunta 10__. Selecciona todos los géneros únicos disponibles.

__Ejercicio 5__. Inventario de Productos

```xml
<inventory>
  <product id="P001">
    <name>Chair</name>
    <category>Furniture</category>
    <price currency="USD">49.99</price>
    <stock>200</stock>
  </product>
  <product id="P002">
    <name>Table</name>
    <category>Furniture</category>
    <price currency="USD">129.99</price>
    <stock>50</stock>
  </product>
  <product id="P003">
    <name>Lamp</name>
    <category>Lighting</category>
    <price currency="USD">19.99</price>
    <stock>100</stock>
  </product>
  <product id="P004">
    <name>Desk</name>
    <category>Furniture</category>
    <price currency="USD">249.99</price>
    <stock>20</stock>
  </product>
  <product id="P005">
    <name>Ceiling Light</name>
    <category>Lighting</category>
    <price currency="USD">79.99</price>
    <stock>30</stock>
  </product>
</inventory>
```

__Pregunta 1__. Selecciona los nombres de todos los productos.

__Pregunta 2__. Selecciona todos los productos de la categoría "Furniture".

__Pregunta 3__. Selecciona el precio del producto "Lamp".

__Pregunta 4__. Cuenta cuántos productos tienen más de 50 en stock.

__Pregunta 5__. Selecciona el producto más caro.

__Pregunta 6__. Selecciona los nombres de los productos con menos de 30 en stock.

__Pregunta 7__. Selecciona todos los precios en USD.

__Pregunta 8__. Selecciona el ID de todos los productos de la categoría "Lighting".

__Pregunta 9__. Selecciona el precio del producto más barato.

__Pregunta 10__. Selecciona los nombres y precios de todos los productos ordenados por precio.
