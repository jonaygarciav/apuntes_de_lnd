# XSLT (Ejercicios)

__Ejercicio 1__. Generar mediante XSLT una lista HTML desordenada `<ul>` con los nombres de las frutas. a partir del siguiente HTML.

XML de entrada:

```xml
<fruits>
  <fruit>Apple</fruit>
  <fruit>Banana</fruit>
  <fruit>Cherry</fruit>
</fruits>
```

Salida:

```html
<ul>
  <li>Apple</li>
  <li>Banana</li>
  <li>Cherry</li>
</ul>
```

__Ejercicio 2__. Crear una tabla HTML de libros con las columnas "Título" y "Autor".

XML de entrada:

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

Salida:

```html
<table border="1">
  <tr>
    <th>Title</th>
    <th>Author</th>
  </tr>
  <tr>
    <td>1984</td>
    <td>George Orwell</td>
  </tr>
  <tr>
    <td>Brave New World</td>
    <td>Aldous Huxley</td>
  </tr>
</table>
```

__Ejercicio 3__. Crear un fichero HTML con un encabezado en cada sección. Generar encabezados `<h2>` y párrafos `<p>` para cada sección.

XML de entrada:

```xml
<sections>
  <section>
    <title>Introduction</title>
    <content>Welcome to the tutorial.</content>
  </section>
  <section>
    <title>Chapter 1</title>
    <content>This is the first chapter.</content>
  </section>
</sections>
```

Salida:

```html
<h2>Introduction</h2>
<p>Welcome to the tutorial.</p>
<h2>Chapter 1</h2>
<p>This is the first chapter.</p>
```

__Ejercicio 4__. Generar un fichero HTML donde se resalten los productos con precio mayor a 500 en negrita `<b>`.

XML de entrada:

```xml
<products>
  <product>
    <name>Laptop</name>
    <price>1000</price>
  </product>
  <product>
    <name>Mouse</name>
    <price>25</price>
  </product>
</products>
```

Salida:

```html
<p><b>Laptop</b> - $1000</p>
<p>Mouse - $25</p>
```

__Ejercicio 5__. Generar un fichero HTML con una lista de navegación `<nav>`.

XML de entrada:

```
<menu>
  <item>Home</item>
  <item>About</item>
  <item>Contact</item>
</menu>
```

Salida:

```html
<nav>
  <ul>
    <li>Home</li>
    <li>About</li>
    <li>Contact</li>
  </ul>
</nav>
```

__Ejercicio 6__. Generar un fichero JSON con la lista de frutas.

XML de entrada:

```xml
<fruits>
  <fruit>Apple</fruit>
  <fruit>Banana</fruit>
  <fruit>Cherry</fruit>
</fruits>
```

Salida:

```json
[
  "Apple",
  "Banana",
  "Cherry"
]
```

__Ejercicio 7__. Crear un fichero JSON con los productos y sus respectivos precios.

XML de entrada:

```xml
<products>
  <product>
    <name>Laptop</name>
    <price>1000</price>
  </product>
  <product>
    <name>Mouse</name>
    <price>25</price>
  </product>
</products>
```

Salida:

```json
[
  {
    "name": "Laptop",
    "price": 1000
  },
  {
    "name": "Mouse",
    "price": 25
  }
]
```

__Ejercicio 8__. Crear un Objeto JSON con los nombres de usuarios.

XML de entrada:

```xml
<users>
  <user>
    <id>1</id>
    <name>John Doe</name>
    <email>john@example.com</email>
  </user>
  <user>
    <id>2</id>
    <name>Jane Smith</name>
    <email>jane@example.com</email>
  </user>
</users>
```

Salida: 

```json
[
  {
    "id": "1",
    "name": "John Doe",
    "email": "john@example.com"
  },
  {
    "id": "2",
    "name": "Jane Smith",
    "email": "jane@example.com"
  }
]
```

__Ejercicio 9__. Crear un fichero JSON con las categorías y los productos:

XML de entrada:

```xml
<store>
  <category name="Electronics">
    <product>
      <name>Laptop</name>
      <price>1000</price>
    </product>
    <product>
      <name>Smartphone</name>
      <price>700</price>
    </product>
  </category>
  <category name="Books">
    <product>
      <name>1984</name>
      <price>15.99</price>
    </product>
    <product>
      <name>Brave New World</name>
      <price>12.49</price>
    </product>
  </category>
</store>
```

Salida: 

```json
{
  "Electronics": [
    {
      "name": "Laptop",
      "price": 1000
    },
    {
      "name": "Smartphone",
      "price": 700
    }
  ],
  "Books": [
    {
      "name": "1984",
      "price": 15.99
    },
    {
      "name": "Brave New World",
      "price": 12.49
    }
  ]
}
```

__Ejercicio 10__. Crear un fichero JSON con los titulos de secciones y su contenido.

XML de entrada:

```xml
<document>
  <section>
    <title>Introduction</title>
    <content>Welcome to this tutorial.</content>
  </section>
  <section>
    <title>Chapter 1</title>
    <content>This is the first chapter.</content>
  </section>
</document>
```

Salida: 

```json
[
  {
    "title": "Introduction",
    "content": "Welcome to this tutorial."
  },
  {
    "title": "Chapter 1",
    "content": "This is the first chapter."
  }
]
```
