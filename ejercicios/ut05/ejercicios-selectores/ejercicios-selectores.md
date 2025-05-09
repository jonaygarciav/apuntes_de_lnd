# Ejercicios Selectores

## Ejercicio 1

Añadir los selectores a las reglas CSS para aplicar los estilos deseados y crear una página web que tenga el mismo aspecto que la siguiente imagen:

![][01]

Cada regla CSS incluye un comentario en el que se explica los elementos a los que debe aplicarse.

Código base:

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>Ejercicio de selectores</title>
<style>
/* Todos los elementos de la pagina */
{
  font-size: 16px;
  font-family: Arial, Helvetica, sans-serif;
}

/* Todos los parrafos de la pagina */
{
  color: #555;
}

/* Todos los párrafos contenidos en #primero */
{
  color: #369;
}

/* Todos los enlaces la pagina */
{
  color: #C30;
}

/* Los elementos <em> contenidos en #primero */
{
  color: #0000BB;
  background-color: #FFFFCC;
}

/* Todos los elementos <em> con la clase "especial" en toda la pagina */
{
  color: #FFFF00;
  background: #000000;
}

/* Todos los elementos <span> contenidos en la clase "normal" */
{
  font-weight: bold;
}
</style>
</head>

<body>

<div id="primero">
<p>
<a href="http://publicacionesaltaria.com/es/tienda/112-html-css-curso-practico.html">HTML &amp; CSS: Curso práctico avanzado</a>
</p>

<p>
Aunque los inicios de <a href="https://es.wikipedia.org/wiki/Internet">Internet</a> se remontan a los años sesenta, no ha sido hasta los años noventa cuando, gracias a la Web, se ha extendido su uso por todo el mundo. En pocos años, la Web ha evolucionado enormemente: se ha pasado de páginas sencillas, con pocas imágenes y contenidos estáticos que eran visitadas por unos pocos usuarios a <em>páginas complejas, con contenidos dinámicos que provienen de bases de datos y que son visitadas por miles de usuarios al mismo tiempo</em>.
</p>
</div>

<div id="segundo" class="normal">
<p>
Todas las páginas están internamente construidas con la misma tecnología, con el <em class="especial">Lenguaje de marcas de hipertexto</em> (<span>Hypertext Markup Language</span>, <a href="https://es.wikipedia.org/wiki/HTML">HTML</a>) y con las <em class="especial">Hojas de estilo en cascada</em> (<span>Cascading Style Sheets</span>, <a href="https://es.wikipedia.org/wiki/CSS">CSS</a>).
</p>

<p>
Este libro es <em>adecuado para cualquiera que tenga interés en aprender a desarrollar sus propias páginas web</em>. No son necesarios conocimientos previos para aprender con este libro, lo único que es necesario es saber utilizar un ordenador y saber navegar por la Web.
</p>
</div>

</body>
</html>
```

## Ejercicio 2

Escribir un fichero externo CSS para lograr una página web que tenga el mismo aspecto que la siguiente imagen:

![][02]

[01]: ./ejercicio01.png "01"
[02]: ./ejercicio02.png "02"

## Ejercicio 3

Escribir un fichero CSS con las reglas CSS necesarias para lograr una página web que tenga el siguiente funcionamiento:

* En su estado normal, un enlace se muestra de color rojo y sin subrayado (propiedad text-decoration).
* Cuando el usuario sitúa el cursor del ratón sobre un enlace, se invierten los colores (el texto del enlace se muestra con color blanco sobre un fondo rojo) y se muestra el subrayado.
* Cuando un enlace está activo, se muestra de color naranja y sin subrayado.
* Cuando un enlace ha sido visitado, se muestra de color verde oscuro y sin subrayado.
* Cuando un enlace tiene el foco del teclado, se muestra de color azul y se muestra el subrayado.

Código HTML:

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>Ejercicio de selectores</title>
</head>
<body>
<h1>Universidad de Alicante</h1>

<ul>
<li><a href="presentacion.html">Presentación</a></li>
<li><a href="estudios.html">Estudios</a></li>
<li><a href="alumnos.html">Alumnos</a></li>
<li><a href="deportes.html">Deportes</a></li>
<li><a href="servicios.html">Servicios</a></li>
</ul>
</body>
</html>
```

## Ejercicio 4

Estilizar una sección de noticias. Aplicando los siguientes estilos:

* Todos los títulos de noticias (`<h2>` dentro de .noticia) deben tener color darkblue y fuente Georgia.
* El primer párrafo de cada noticia debe estar en cursiva.
* Todos los enlaces dentro de .noticia deben estar subrayados solo al pasar el ratón.
* Si el enlace tiene la clase .externo, debe tener color rojo y abrir en otra pestaña.

Parte del fichero HTML:

```html
<div class="noticia">
  <h2>Última hora</h2>
  <p>Resumen introductorio...</p>
  <p>Detalles de la noticia.</p>
  <a href="#">Seguir leyendo</a>
  <a href="https://ejemplo.com" class="externo" target="_blank">Fuente externa</a>
</div>
```

## Ejercicio 5

Tabla de datos interactiva. Aplicando los siguientes estilos:

* Alterna el color de fondo de las filas (#f9f9f9 y #e0e0e0).
* La fila al pasar el ratón debe cambiar a #ddd.
* El encabezado debe tener fondo #333 y texto blanco.
* La primera columna debe estar en negrita.

Parte del fichero HTML:

```html
<table>
  <thead>
    <tr><th>Nombre</th><th>Edad</th><th>Ciudad</th></tr>
  </thead>
  <tbody>
    <tr><td>Ana</td><td>28</td><td>Madrid</td></tr>
    <tr><td>Luis</td><td>35</td><td>Barcelona</td></tr>
    <tr><td>María</td><td>22</td><td>Valencia</td></tr>
  </tbody>
</table>
```
