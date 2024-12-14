# XQuery (Ejercicios)

__Ejercicio 1__. Archivo `biblioteca.xml`:

```xml
<biblioteca>
  <libro id="1" genero="Ficción">
    <titulo>1984</titulo>
    <autor pais="Reino Unido">George Orwell</autor>
    <precio moneda="USD">19.99</precio>
  </libro>
  <libro id="2" genero="Ciencia Ficción">
    <titulo>Brave New World</titulo>
    <autor pais="Reino Unido">Aldous Huxley</autor>
    <precio moneda="USD">14.99</precio>
  </libro>
  <libro id="3" genero="Distopía">
    <titulo>Fahrenheit 451</titulo>
    <autor pais="EE.UU.">Ray Bradbury</autor>
    <precio moneda="USD">12.50</precio>
  </libro>
  <libro id="4" genero="Ficción">
    <titulo>To Kill a Mockingbird</titulo>
    <autor pais="EE.UU.">Harper Lee</autor>
    <precio moneda="USD">18.99</precio>
  </libro>
  <libro id="5" genero="Ficción">
    <titulo>The Great Gatsby</titulo>
    <autor pais="EE.UU.">F. Scott Fitzgerald</autor>
    <precio moneda="USD">10.99</precio>
  </libro>
</biblioteca>
```

_Pregunta 1_. Devuelve todos los títulos de los libros.

_Pregunta 2_. Devuelve los títulos de libros cuyo precio es mayor a 15.

_Pregunta 3_. Lista los autores y sus países de origen.

_Pregunta 4_. Calcula el precio promedio de los libros.

_Pregunta 5_. Devuelve los títulos ordenados alfabéticamente.

_Pregunta 6_. Devuelve los títulos y precios de los libros en formato XML.

_Pregunta 7_. Encuentra libros del género "Ficción".

_Pregunta 8_. Devuelve los libros cuyo autor sea de "EE.UU.".

_Pregunta 9_. Lista los libros y su precio total (precio + 5 USD de impuesto).

_Pregunta 10_. Devuelve el libro más caro en el catálogo.

__Ejercicio 2__. Archivo `tienda.xml`:

```xml
<tienda>
  <producto id="1" categoria="Computadoras">
    <nombre>Portátil</nombre>
    <marca>HP</marca>
    <precio moneda="USD">800</precio>
  </producto>
  <producto id="2" categoria="Accesorios">
    <nombre>Monitor</nombre>
    <marca>Dell</marca>
    <precio moneda="USD">200</precio>
  </producto>
  <producto id="3" categoria="Accesorios">
    <nombre>Ratón</nombre>
    <marca>Logitech</marca>
    <precio moneda="USD">25</precio>
  </producto>
  <producto id="4" categoria="Computadoras">
    <nombre>Escritorio</nombre>
    <marca>Lenovo</marca>
    <precio moneda="USD">600</precio>
  </producto>
  <producto id="5" categoria="Impresoras">
    <nombre>Impresora</nombre>
    <marca>Canon</marca>
    <precio moneda="USD">150</precio>
  </producto>
</tienda>
```

_Pregunta 1_. Devuelve los nombres de todos los productos.

_Pregunta 2_. Devuelve los productos de la categoría "Accesorios".

_Pregunta 3_. Calcula el precio total de todos los productos.

_Pregunta 4_. Encuentra productos con un precio mayor a 500 USD.

_Pregunta 5_. Devuelve los productos y sus precios con un descuento del 10%.

_Pregunta 6_. Lista los productos ordenados por precio de menor a mayor.

_Pregunta 7_. Devuelve los productos de la marca "HP".

_Pregunta 8_. Devuelve los nombres y categorías de los productos como elementos `<item>`.

_Pregunta 9_. Encuentra el producto más barato.

_Pregunta 10_. Calcula el precio promedio de los productos en la categoría "Computadoras".

_Ejercicio 3_. Archivo `musica.xml`:

```xml
<catalogo>
  <album id="1" genero="Rock">
    <titulo>The Dark Side of the Moon</titulo>
    <artista>Pink Floyd</artista>
    <anio>1973</anio>
    <precio>20.00</precio>
  </album>
  <album id="2" genero="Pop">
    <titulo>Thriller</titulo>
    <artista>Michael Jackson</artista>
    <anio>1982</anio>
    <precio>18.00</precio>
  </album>
  <album id="3" genero="Rock">
    <titulo>Abbey Road</titulo>
    <artista>The Beatles</artista>
    <anio>1969</anio>
    <precio>25.00</precio>
  </album>
  <album id="4" genero="Jazz">
    <titulo>Kind of Blue</titulo>
    <artista>Miles Davis</artista>
    <anio>1959</anio>
    <precio>15.00</precio>
  </album>
</catalogo>
```

_Pregunta 1_. Devuelve todos los títulos de los álbumes.

_Pregunta 2_. Devuelve los álbumes cuyo precio es mayor a 18.

_Pregunta 3_. Lista los títulos y géneros de todos los álbumes.

_Pregunta 4_. Calcula el precio promedio de los álbumes (usa `let`).

_Pregunta 5_. Encuentra los álbumes de género "Rock".

_Pregunta 6_. Ordena los álbumes por año de lanzamiento.

_Pregunta 7_. Devuelve el álbum más caro.

_Pregunta 8_. Devuelve los títulos y los precios con un descuento del 20%.

_Pregunta 9_. Devuelve los álbumes lanzados antes de 1975.

_Pregunta 10_. Calcula el precio total de todos los álbumes.

__Ejercicio 4__. Archivo `estudiantes.xml`:

```xml
<estudiantes>
  <estudiante id="1" carrera="Ingeniería">
    <nombre>Juan</nombre>
    <edad>20</edad>
    <nota>8.5</nota>
  </estudiante>
  <estudiante id="2" carrera="Derecho">
    <nombre>María</nombre>
    <edad>22</edad>
    <nota>9.0</nota>
  </estudiante>
  <estudiante id="3" carrera="Medicina">
    <nombre>Pedro</nombre>
    <edad>19</edad>
    <nota>7.5</nota>
  </estudiante>
  <estudiante id="4" carrera="Ingeniería">
    <nombre>Ana</nombre>
    <edad>21</edad>
    <nota>8.8</nota>
  </estudiante>
</estudiantes>
```

_Pregunta 1_. Devuelve los nombres de los estudiantes.

_Pregunta 2_. Filtra los estudiantes con una nota mayor a 8.

_Pregunta 3_. Devuelve los nombres y las carreras de los estudiantes.

_Pregunta 4_. Calcula la nota promedio de los estudiantes (usa let).

_Pregunta 5_. Devuelve los estudiantes de la carrera "Ingeniería".

_Pregunta 6_. Ordena a los estudiantes por edad.

_Pregunta 7_. Devuelve el estudiante más joven.

_Pregunta 8_. Devuelve los nombres y las notas incrementadas en 0.5.

_Pregunta 9_. Devuelve los estudiantes cuya nota es mayor a 8 y pertenecen a Ingeniería.

_Pregunta 10_. Cuenta cuántos estudiantes hay en total.

__Ejercicio 5__. Archivo `pedidos.xml`:

```xml
<pedidos>
  <pedido id="1" cliente="Juan">
    <producto>Televisor</producto>
    <cantidad>1</cantidad>
    <precio>400</precio>
  </pedido>
  <pedido id="2" cliente="María">
    <producto>Teléfono</producto>
    <cantidad>2</cantidad>
    <precio>200</precio>
  </pedido>
  <pedido id="3" cliente="Pedro">
    <producto>Ratón</producto>
    <cantidad>5</cantidad>
    <precio>25</precio>
  </pedido>
  <pedido id="4" cliente="Ana">
    <producto>Teclado</producto>
    <cantidad>3</cantidad>
    <precio>30</precio>
  </pedido>
</pedidos>
```

_Ejercicio 1_. Devuelve los nombres de los clientes.

_Ejercicio 2_. Devuelve los productos con precio total (cantidad × precio).

_Ejercicio 3_. Filtra los pedidos cuyo precio total sea mayor a 100.

_Ejercicio 4_. Calcula el precio promedio de todos los pedidos.

_Ejercicio 5_. Devuelve el pedido más caro.

_Ejercicio 6_. Ordena los pedidos por cliente alfabéticamente.

_Ejercicio 7_. Calcula el precio total de todos los pedidos.

_Ejercicio 8_. Devuelve los nombres de los clientes que compraron más de 3 unidades.

_Ejercicio 9_. Devuelve los productos y sus precios con un descuento del 15% (usa `let`).

_Ejercicio 10_. Cuenta el número total de pedidos.
