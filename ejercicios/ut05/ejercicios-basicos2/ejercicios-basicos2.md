# Ejercicios CSS Básicos 2

# Ejercicio 1: Aplicar estilos de diseño a la estructura base de una tarjeta

Crea una tarjeta de presentación básica que contenga un título, una descripción corta y un botón. La tarjeta debe tener un ancho máximo de 300 píxeles, un borde redondeado de 10 píxeles, sombra suave, y padding interno. El título debe estar centrado, tener un tamaño de fuente de al menos 24 píxeles, y el botón debe ocupar el ancho completo de la tarjeta. Usa una clase llamada `.tarjeta` para aplicar estilos a toda la caja y propiedades de layout visual como `box-shadow`, `border-radius`, `padding`, `max-width`, y estilos tipográficos.

![][01]

# Ejercicio 2: Aplicar estilo condicional a enlaces según su estado

Crea una lista de enlaces de navegación. Usa selectores para que los enlaces cambien de color al pasar el cursor (`:hover`), al estar visitados (visited), y al hacer clic en ellos (`:active`). Los enlaces deben estar sin subrayado, tener color azul por defecto, y cambiar a verde al pasar el cursor, morado si ya fueron visitados, y rojo mientras están activos. Usa correctamente los pseudoselectores `:hover`, `:visited` y `:active` en orden adecuado para evitar conflictos de estilo.

![][02]

# Ejercicio 3: Alternar colores en filas de una tabla

Crea una tabla HTML con al menos cinco filas de datos. Utiliza selectores CSS para aplicar colores de fondo alternos (gris claro y blanco) a las filas, de modo que la tabla sea más legible. Además, al pasar el cursor sobre cualquier fila, cambia el fondo a un tono azul claro para destacar la selección. Este ejercicio refuerza el uso de los selectores `:nth-child(even)`, `:nth-child(odd)` y `:hover` en el contexto de tablas, que son muy útiles para diseño visual en interfaces de usuario.

![][03]

# Ejercicio 4: Diseñar formulario con campos personalizados

Crea un formulario con al menos tres campos de texto y un botón de envío. Aplica estilos a los campos para que tengan bordes redondeados, fondo ligeramente gris, y padding interno. Cuando un campo recibe foco (`:focus`), su borde debe volverse azul. El botón debe tener fondo verde y cambiar a oscuro al pasar el cursor. Este ejercicio combina selectores de tipo, clases y pseudoselectores como `:focus`, y promueve el diseño accesible de formularios.

![][04]

# Ejercicio 5: Lista de enlaces con estilo interactivo al pasar el ratón

Crea una lista no ordenada (`<ul>`) que contenga al menos cinco elementos (`<li>`), cada uno con un enlace (`<a>`) a una URL distinta. La lista debe tener un estilo limpio, sin los puntos de viñeta, y con espacio entre elementos. Cada enlace debe mostrarse en un color gris oscuro por defecto, con texto ligeramente agrandado. Cuando el usuario pase el ratón por encima de cualquier enlace, este debe cambiar de color a azul brillante y mostrar un subrayado. Este ejercicio te permite practicar el uso de listas como menú de navegación, el uso de pseudoselectores como `:hover`, y el control de estilos para elementos interactivos dentro de una estructura de lista.

![][05]

[01]: ./01.png "01"
[02]: ./02.png "02"
[03]: ./03.png "03"
[04]: ./04.png "04"
[05]: ./05.png "05"
