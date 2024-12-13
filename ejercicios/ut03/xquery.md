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

__Pregunta 1__. Devuelve todos los títulos de los libros.

__Pregunta 2__. Devuelve los títulos de libros cuyo precio es mayor a 15.

__Pregunta 3__. Lista los autores y sus países de origen.

__Pregunta 4__. Calcula el precio promedio de los libros.

__Pregunta 5__. Devuelve los títulos ordenados alfabéticamente.

__Pregunta 6__. Devuelve los títulos y precios de los libros en formato XML.

__Pregunta 7__. Encuentra libros del género "Ficción".

__Pregunta 8__. Devuelve los libros cuyo autor sea de "EE.UU.".

__Pregunta 9__. Lista los libros y su precio total (precio + 5 USD de impuesto).

__Pregunta 10__. Devuelve el libro más caro en el catálogo.

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

__Pregunta 1__. Devuelve los nombres de todos los productos.

__Pregunta 2__. Devuelve los productos de la categoría "Accesorios".

__Pregunta 3__. Calcula el precio total de todos los productos.

__Pregunta 4__. Encuentra productos con un precio mayor a 500 USD.

__Pregunta 5__. Devuelve los productos y sus precios con un descuento del 10%.

__Pregunta 6__. Lista los productos ordenados por precio de menor a mayor.

__Pregunta 7__. Devuelve los productos de la marca "HP".

__Pregunta 8__. Devuelve los nombres y categorías de los productos como elementos `<item>`.

__Pregunta 9__. Encuentra el producto más barato.

__Pregunta 10__. Calcula el precio promedio de los productos en la categoría "Computadoras".

__Ejercicio 3__. Archivo `musica.xml`:

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

__Pregunta 1__. Devuelve todos los títulos de los álbumes.

__Pregunta 2__. Devuelve los álbumes cuyo precio es mayor a 18.

__Pregunta 3__. Lista los títulos y géneros de todos los álbumes.

__Pregunta 4__. Calcula el precio promedio de los álbumes (usa `let`).

__Pregunta 5__. Encuentra los álbumes de género "Rock".

__Pregunta 6__. Ordena los álbumes por año de lanzamiento.

__Pregunta 7__. Devuelve el álbum más caro.

__Pregunta 8__. Devuelve los títulos y los precios con un descuento del 20%.

__Pregunta 9__. Devuelve los álbumes lanzados antes de 1975.

__Pregunta 10__. Calcula el precio total de todos los álbumes.

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

__Pregunta 1__. Devuelve los nombres de los estudiantes.

__Pregunta 2__. Filtra los estudiantes con una nota mayor a 8.

__Pregunta 3__. Devuelve los nombres y las carreras de los estudiantes.

__Pregunta 4__. Calcula la nota promedio de los estudiantes (usa let).

__Pregunta 5__. Devuelve los estudiantes de la carrera "Ingeniería".

__Pregunta 6__. Ordena a los estudiantes por edad.

__Pregunta 7__. Devuelve el estudiante más joven.

__Pregunta 8__. Devuelve los nombres y las notas incrementadas en 0.5.

__Pregunta 9__. Devuelve los estudiantes cuya nota es mayor a 8 y pertenecen a Ingeniería.

__Pregunta 10__. Cuenta cuántos estudiantes hay en total.

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

__Ejercicio 1__. Devuelve los nombres de los clientes.

__Ejercicio 2__. Devuelve los productos con precio total (cantidad × precio).

__Ejercicio 3__. Filtra los pedidos cuyo precio total sea mayor a 100.

__Ejercicio 4__. Calcula el precio promedio de todos los pedidos.

__Ejercicio 5__. Devuelve el pedido más caro.

__Ejercicio 6__. Ordena los pedidos por cliente alfabéticamente.

__Ejercicio 7__. Calcula el precio total de todos los pedidos.

__Ejercicio 8__. Devuelve los nombres de los clientes que compraron más de 3 unidades.

__Ejercicio 9__. Devuelve los productos y sus precios con un descuento del 15% (usa `let`).

__Ejercicio 10__. Cuenta el número total de pedidos.
