# Introducción a los Lenguajes de Marcas

* Introducción
* Evolución de los Lenguajes de Marcas
  * GML
  * SGML
  * XML
  * HTML
  * XHTML
  * Markdown

## Introducción

Los __lenguajes de marcas__ son sistemas de codificación que utilizan etiquetas para definir la estructura, presentación y significado de los contenidos dentro de un documento. A diferencia de los lenguajes de programación, los lenguajes de marcas se centran en describir cómo se organiza y presenta la información en lugar de dictar acciones específicas para que una computadora las ejecute.

Surgieron como una forma de separar el contenido de su presentación, permitiendo que el mismo contenido pueda mostrarse de diferentes maneras sin ser modificado. Esta idea se remonta a los primeros sistemas de impresión y procesamiento de texto, donde se requería una forma de especificar títulos, párrafos y otros elementos de diseño dentro del texto.

Uno de los primeros lenguajes de marcas fue SGML (Standard Generalized Markup Language), desarrollado en los años 80, que estableció las bases para lenguajes más conocidos como HTML (HyperText Markup Language) y XML (Extensible Markup Language).

Características comunes:
* __Uso de Etiquetas__: Los lenguajes de marcas emplean etiquetas (tags) para definir la estructura de los contenidos. Estas etiquetas indican qué tipo de información contienen (por ejemplo, títulos, párrafos, listas, etc.).
* __Separación de contenido y presentación__: los lenguajes de marcas permiten separar el contenido de su formato o presentación, lo que facilita la reutilización de datos en diferentes contextos y dispositivos.
* __Legibilidad para humanos y máquinas__: los documentos creados con lenguajes de marcas son comprensibles tanto para los humanos como para los sistemas de procesamiento automático, lo que permite una gran interoperabilidad.

## Evolución de los Lenguajes de Marcas

### GML

![][01]

__GML__ (_IBM Generalized Markup Language_), es un lenguaje de marcas desarrollado por IBM a finales de los años 60 y principios de los 70. Se utilizó principalmente para crear documentos estructurados y formateados que podían ser interpretados y presentados en diferentes dispositivos sin modificar el contenido del archivo original.

El lenguaje fue creado por _Charles Goldfarb_, _Edward Mosher_ y _Raymond Lorie_, quienes eligieron las iniciales de sus apellidos para dar nombre a _GML_. A través del uso de etiquetas, _GML_ permitía definir la estructura de un documento, como encabezados, párrafos y listas, separando así el contenido de su presentación.

Con _GML_, los documentos se podían adaptar automáticamente a varios dispositivos, como impresoras láser o de matriz de puntos, solo especificando un perfil de formato para cada dispositivo. Esta funcionalidad facilitó enormemente la creación de documentos flexibles y reutilizables, sentando las bases para los estándares que seguirían, como _SGML_ y _XML_.

El siguiente ejemplo de GML, aunque adaptado, muestra cómo se estructuran los documentos utilizando este lenguaje:

```
:h1.Capítulo 1: Introducción
:p.El GML define la estructura de documentos usando etiquetas específicas 
para distintos tipos de contenido, como párrafos y listas.

:h2.Secciones del Documento
:p.Con GML, es posible definir estructuras jerárquicas, como:
:ol.
:li.Listas numeradas,
:li.Listas con viñetas, y
:li.Listas de definiciones.
:eol.

p.El marcado en GML puede simplificarse, permitiendo omitir las etiquetas 
de cierre en elementos como "h1" y "p".
```

Aquí tienes una lista explicando qué significa cada etiqueta usada en un ejemplo de GML:

* __:h1.__ (Encabezado de Nivel 1): define un encabezado de primer nivel, similar a un título principal en un documento. Utilizado para marcar la sección más importante o un capítulo.
* __:h2.__ (Encabezado de Nivel 2): define un encabezado de segundo nivel, generalmente usado para subsecciones dentro de un capítulo o sección mayor marcada con :h1..
* __:p.__ (Párrafo): define un párrafo de texto. Se utiliza para agrupar oraciones o bloques de texto separados por un salto de línea.
* __:ol.__ (Lista Ordenada): inicia una lista ordenada (numerada). Cada elemento dentro de esta lista se marcará con números o letras, según el dispositivo de salida.
* __:li.__ (Elemento de Lista (List Item)): marca un elemento dentro de una lista (:ol. para listas ordenadas o :ul. para listas no ordenadas). Define cada punto o entrada de la lista.
* __:eol.__ (Fin de Lista Ordenada): indica el final de una lista ordenada iniciada con :ol.. Esta etiqueta cierra la estructura de la lista.

Algunas limitaciones de GML eran:
* __Falta de estandarización formal__: GML no era un estándar formalizado a nivel internacional, lo que significaba que su implementación podía variar y no estaba universalmente reconocida fuera del entorno de IBM. Esto limitaba su interoperabilidad y su adopción por parte de otras empresas.
* __Dependencia de IBM y su software__: GML estaba estrechamente vinculado a los sistemas y software de IBM, como el procesador de texto SCRIPT y el Document Composition Facility (DCF). Esto lo hacía poco accesible para organizaciones que no utilizaban las plataformas de IBM, restringiendo su uso más allá de entornos específicos.
* __Falta de compatibilidad multiplataforma__: GML fue diseñado específicamente para los sistemas de IBM, lo que limitaba su aplicabilidad en otras plataformas y dispositivos que no utilizaban el software específico de IBM, reduciendo su alcance y utilidad fuera de ese ecosistema.
* __Desactualización frente a nuevos requerimientos__: con el tiempo, las necesidades de documentación y publicación evolucionaron, y GML no pudo adaptarse fácilmente a estos cambios, como la necesidad de intercambiar datos de manera más abierta y flexible entre diferentes sistemas. Esto llevó al desarrollo de SGML, que estandarizó y amplió las capacidades introducidas por GML.

_GML_ sentó las bases para el desarrollo de __SGML__ (_Standard Generalized Markup Language_), que se convirtió en un estándar ISO y más tarde evolucionó en XML (Extensible Markup Language). Estas evoluciones llevaron la estructuración de documentos a nuevos niveles, influyendo enormemente en la forma en que los datos se gestionan y se comparten en la actualidad.

### SGML

__SGML__ (_Standard Generalized Markup Language_) es un estándar ISO (ISO 8879:1986) que define un marco para la creación de lenguajes de marcado utilizados para estructurar y describir documentos de manera independiente del formato de presentación. SGML se considera uno de los lenguajes de marcado más influyentes, ya que sirvió como base para otros lenguajes como HTML y XML.

_SGML_ fue desarrollado a partir de _GML_ (_Generalized Markup Language_) en la década de 1980 por Charles Goldfarb y su equipo. Su objetivo era crear un sistema más estandarizado para la estructuración de documentos, que pudiera ser usado por cualquier organización o industria.
En 1986, SGML fue adoptado como un estándar internacional por la Organización Internacional de Normalización (ISO). Esta estandarización permitió que SGML se convirtiera en una herramienta esencial para la gestión y publicación de documentos complejos.

[ISO 8879:1986 Information processing — Text and office systems — Standard Generalized Markup Language (SGML)](https://www.iso.org/standard/16387.html)

Características principales de SGML:
* __Extensibilidad__: SGML no define etiquetas específicas, sino que permite a los usuarios crear sus propios conjuntos de etiquetas según las necesidades de sus documentos, haciéndolo muy flexible y adaptable a diferentes sectores.
Separación de Contenido y Presentación: SGML enfoca su estructura en el contenido del documento, dejando la presentación a herramientas externas, lo cual facilita la reutilización de los datos.
* __Definición de DTD__ (_Document Type Definition_): SGML utiliza DTDs para definir la estructura, reglas y etiquetas permitidas en un documento. Esto asegura la consistencia y la validez de los documentos estructurados bajo las mismas reglas.
* __Independencia de Plataforma__: SGML fue diseñado para ser independiente de cualquier sistema operativo o software, lo que lo hace ideal para la creación de documentos que deben ser intercambiados y utilizados en múltiples entornos.

_SGML_ fue ampliamente utilizado en la industria de la publicación técnica y en la creación de manuales de usuario, documentación técnica, y bases de datos de documentos en sectores como la aviación y la defensa. Periódicos y revistas utilizaron SGML para manejar la estructura y la gestión del contenido editorial de manera eficiente. Se usó en bibliotecas digitales para definir estructuras estandarizadas de datos, facilitando la búsqueda y recuperación de la información.

Un documento SGML típico comienza con una declaración de tipo de documento (<!DOCTYPE>) que define el DTD seguido por las etiquetas estructurales:

```
<!DOCTYPE manual SYSTEM "manual.dtd">
<manual>
    <title>Manual de Usuario</title>
    <section>
        <title>Introducción</title>
        <para>Este manual describe cómo utilizar el software...</para>
    </section>
    <section>
        <title>Instalación</title>
        <para>Siga los siguientes pasos para instalar el software...</para>
    </section>
</manual>
```

Explicación de las Etiquetas:

* __\<!DOCTYPE manual SYSTEM "manual.dtd"\>__: define el tipo de documento y especifica que el documento seguirá la estructura definida en el DTD (Document Type Definition) llamado "manual.dtd". El fichero DTD establece las reglas y la estructura del documento asegurando que todas las etiquetas utilizadas sean válidas según las definiciones establecidas en el DTD.
* __\<manual\> y \</manual\>__: define el inicio y el fin del documento SGML principal. Actúa como el contenedor principal del contenido del manual, agrupando todas las secciones y elementos relacionados.
* __\<title\> y \</title\>__: marca un título dentro del documento. Utilizada para definir títulos tanto del documento principal como de las subsecciones. En el ejemplo, se usa para "Manual de Usuario", "Introducción" y "Instalación".
* __\<section\> y \</section\>__: define una sección del documento, que puede contener múltiples títulos y párrafos. Organiza el contenido en bloques lógicos, facilitando la estructuración del texto en partes diferenciadas.
* __\<para\> y \</para\>__: define un párrafo de texto dentro de una sección. Usada para incluir el contenido explicativo o descriptivo en un formato estructurado dentro de las secciones.

Cada etiqueta tiene un propósito específico que facilita la organización lógica del documento, permitiendo una clara separación entre diferentes partes del texto.

El archivo manual.dtd (Document Type Definition) define la estructura y las reglas para los documentos SGML como el ejemplo anterior. A continuación, te muestro un ejemplo de cómo podría estar estructurado un archivo manual.dtd para el documento SGML mencionado:

```
<!-- Definición del tipo de documento -->
<!ELEMENT manual (title, section+)>

<!-- Definición de un título que contiene texto -->
<!ELEMENT title (#PCDATA)>

<!-- Definición de una sección que contiene un título y uno o más párrafos o subsecciones -->
<!ELEMENT section (title, (para | section)*)>

<!-- Definición de un párrafo que contiene solo texto -->
<!ELEMENT para (#PCDATA)>
```

Explicación de las Definiciones en el manual.dtd:

* __ELEMENT manual (title, section+)__: define que el elemento manual debe contener un title y una o más (+) section. Esto establece la estructura básica del documento.
* __!ELEMENT title (#PCDATA)__: define que el elemento title contiene datos de texto (#PCDATA, Parsed Character Data). Este tipo de datos permite que el título incluya solo texto plano.
* __!ELEMENT section (title, (para | section)\*)__: define una section que debe contener un title y puede contener cero o más (*) elementos de tipo para (párrafo) o section (subsección).
* __!ELEMENT para (#PCDATA)__: define que un _para_ es un párrafo que contiene solo datos de texto.

_SGML_ sentó las bases para la creación de HTML, que se simplificó para la web, y XML, que adoptó muchas de las fortalezas de SGML pero con una sintaxis más sencilla y más compatible con la web. Aunque SGML fue un estándar revolucionario, su complejidad y la necesidad de herramientas específicas para su procesamiento llevaron a la adopción de XML, que ofrecía una alternativa más ligera y fácil de implementar.
SGML fue un pionero en la estructuración de documentos, permitiendo un control detallado sobre la organización y definición de los datos. A pesar de que su uso ha disminuido, sus principios fundamentales siguen siendo una piedra angular en la forma en que se manejan los datos en la actualidad.

## XML

![][02]

__XML__ (e_X_tensible _M_arkup _L_anguage) es un lenguaje de marcado desarrollado para almacenar, transportar y estructurar datos de manera que sean legibles tanto para humanos como para máquinas. XML es un estándar del W3C (World Wide Web Consortium) y se ha convertido en un componente fundamental para el intercambio de datos en la web y en muchas aplicaciones de software.

Proviene del lenguaje _SGML_ y permite definir la gramática de lenguajes específicos (de la misma manera que HTML es a su vez un lenguaje definido por SGML) para estructurar documentos grandes. A diferencia de otros lenguajes, XML da soporte a bases de datos, siendo útil cuando varias aplicaciones deben comunicarse entre sí o integrar información.

Historial de versiones:

| Versión                       | Año  | Nombre del Estándar                                 |
|-------------------------------|------|-----------------------------------------------------|
| XML 1.0                       | 1998 | Extensible Markup Language (XML) 1.0                |
| XML 1.0 (Segunda Edición)     | 2000 | Extensible Markup Language (XML) 1.0 Second Edition |
| XML 1.0 (Tercera Edición)     | 2004 | Extensible Markup Language (XML) 1.0 Third Edition  |
| XML 1.0 (Cuarta Edición)      | 2006 | Extensible Markup Language (XML) 1.0 Fourth Edition |
| XML 1.0 (Quinta Edición)      | 2008 | Extensible Markup Language (XML) 1.0 Fifth Edition  |
| XML 1.1                       | 2004 | Extensible Markup Language (XML) 1.1                |

Descripción de las Versiones:
* __XML 1.0__: Fue la primera versión del estándar, lanzada en 1998, y ha sido revisada varias veces para corregir errores y mejorar su claridad sin cambiar su funcionalidad fundamental.
* __XML 1.1__: Introducido en 2004 para agregar soporte a un rango más amplio de caracteres y resolver problemas relacionados con los nombres de elementos y atributos que no eran compatibles con XML 1.0.

Características principales de XML: 
* __Extensible__: XML permite definir etiquetas personalizadas, lo que significa que no está limitado a un conjunto específico de etiquetas como HTML. Esto da flexibilidad para describir datos en cualquier contexto.
* __Legibilidad para humanos y máquinas__: XML está diseñado para ser legible tanto por desarrolladores como por aplicaciones de software, facilitando la comprensión y manipulación de datos.
* __Separación de datos y presentación__: a diferencia de HTML, XML se centra en describir la estructura y el contenido, sin especificar cómo se debe presentar. Esto permite que los datos se utilicen en diversos contextos sin cambios en el contenido.
* __Compatible con múltiples plataformas__: XML es independiente de la plataforma, lo que lo hace ideal para el intercambio de datos entre diferentes sistemas operativos y aplicaciones.
* __Uso de DTD o XSD__: XML permite validar los datos contra una DTD (Document Type Definition) o un XSD (XML Schema Definition) para asegurar que los documentos cumplen con una estructura específica.

Un documento XML está compuesto por etiquetas que definen los elementos y atributos de los datos. Los documentos deben tener un elemento raíz que contenga todos los demás elementos.

Ejemplo de un Documento XML Simple:

```
<?xml version="1.0" encoding="UTF-8"?>
<libro>
    <titulo>Introducción a XML</titulo>
    <autor>Juan Pérez</autor>
    <editorial>Ediciones Tech</editorial>
    <precio moneda="USD">29.99</precio>
</libro>
```

Aplicaciones Comunes de XML:
* __Intercambio de datos__: XML se utiliza ampliamente para el intercambio de datos entre aplicaciones a través de APIs y servicios web.
* __Configuración de Software__: muchos programas utilizan XML para definir configuraciones y preferencias de usuario.
* __Almacenamiento de datos__: XML es usado para almacenar y transportar datos estructurados en documentos como feeds RSS, archivos de configuración, y más.
* __Documentación y Publicaciones__: XML se utiliza en la producción de documentos técnicos y publicaciones, incluyendo manuales y artículos.

Ventajas de XML:
* __Estándar abierto__: cualquier desarrollador puede usar XML sin necesidad de licencias.
* __Validación de datos__: permite validar documentos para asegurar que cumplen con las estructuras definidas, mejorando la consistencia y la integridad de los datos.
* __Flexible y extensible__: se adapta a diferentes necesidades, desde documentos simples hasta aplicaciones complejas.

Ejemplo de Documento XML con su DTD, archivo XML (libro.xml):

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE libro SYSTEM "libro.dtd">
<libro>
    <titulo>Introducción a XML</titulo>
    <autor>Juan Pérez</autor>
    <editorial>Ediciones Tech</editorial>
    <precio moneda="USD">29.99</precio>
</libro>
```

Archivo DTD (libro.dtd):

```
<!ELEMENT libro (titulo, autor, editorial, precio)>
<!ELEMENT titulo (#PCDATA)>
<!ELEMENT autor (#PCDATA)>
<!ELEMENT editorial (#PCDATA)>
<!ELEMENT precio (#PCDATA)>
<!ATTLIST precio moneda CDATA #REQUIRED>
```

Explicación de las Definiciones en el DTD:

* __\<!ELEMENT libro (titulo, autor, editorial, precio)\>__: define que el elemento \<libro\> debe contener los elementos \<titulo\>, \<autor\>, \<editorial\>, y \<precio\> en ese orden.
* __\<!ELEMENT titulo (#PCDATA)>, <!ELEMENT autor (#PCDATA)>, <!ELEMENT editorial (#PCDATA)>, <!ELEMENT precio (#PCDATA)\>__: cada uno de estos define que los elementos \<titulo\>, \<autor\>, \<editorial\>, y \<precio\> contienen solo datos de texto (PCDATA - Parsed Character Data).
* __\<!ATTLIST precio moneda CDATA #REQUIRED\>__: define un atributo moneda para el elemento \<precio\>, que es de tipo CDATA (Character Data) y es obligatorio (#REQUIRED).

> __Nota__: el DTD asegura que el documento XML tenga una estructura válida y define claramente qué elementos y atributos son necesarios. Esto es fundamental en sistemas donde la integridad de los datos y la consistencia del formato son esenciales.

### HTML

![][03]

__HTML__ (_HyperText Markup Language_) es el lenguaje estándar para la creación de páginas web y aplicaciones web. Es un lenguaje de marcado que define la estructura de un documento mediante el uso de etiquetas (tags), y es la base de todo el contenido visible en la web. Fue creado en 1991 por Tim Berners-Lee, el inventor de la World Wide Web, como una forma de compartir documentos científicos y técnicos en la web. Desde su creación, HTML ha pasado por varias versiones, desde HTML 1.0 hasta la actual HTML 5, que ha añadido soporte para multimedia, gráficos, y una mejor integración con tecnologías modernas como CSS y JavaScript.

Características principales de HTML:
* __Estructura de documentos__: HTML utiliza una jerarquía de etiquetas para estructurar el contenido de una página web. Las etiquetas básicas incluyen \<html\>, \<head\>, \<body\>, \<h1\> a \<h6\> (encabezados), \<p\> (párrafos), \<a\> (enlaces), \<img\> (imágenes), y muchas más.
* __Elementos Semánticos__: HTML5 introdujo elementos semánticos como \<header\>, \<footer\>, \<article\>, \<section\>, y \<aside\> que mejoran la accesibilidad y la estructura del contenido para usuarios y motores de búsqueda.
* __Interactividad y Multimedia__: HTML permite la inclusión de multimedia (audio, video) y gráficos vectoriales (\<canvas\>, \<svg\>), así como la integración de scripts y estilos mediante JavaScript y CSS.

Sintaxis Básica de HTML:
* __Etiquetas__: cada elemento HTML comienza con una etiqueta de apertura y, en la mayoría de los casos, se cierra con una etiqueta de cierre. Ejemplo: \<p\>Este es un párrafo.\</p\>.
* __Atributos__: las etiquetas HTML pueden tener atributos que proporcionan información adicional sobre los elementos. Ejemplo: \<img src="imagen.jpg" alt="Descripción de la imagen"\>.

Ejemplo de un Documento HTML básico:

```
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Introducción a HTML</title>
</head>
<body>
    <h1>Bienvenido a HTML</h1>
    <p>Este es un ejemplo básico de una página HTML.</p>
    <a href="https://www.example.com">Visita nuestro sitio web</a>
</body>
</html>
```

Estructura de un documento HTML:
* \<!DOCTYPE html\>: indica al navegador que se está utilizando la versión HTML5.
* \<html\>: el contenedor principal del documento.
* \<head\>: contiene metadatos, enlaces a hojas de estilo y scripts.
* \<body\>: contiene el contenido visible de la página, como texto, imágenes y enlaces.

Aplicaciones y uso de HTML:
* __Desarrollo Web__: es el lenguaje fundamental para crear la estructura de sitios web, blogs, tiendas en línea, aplicaciones web, y más.
* __Correos electrónicos__: HTML se utiliza para diseñar correos electrónicos visualmente atractivos y con enlaces interactivos.
* __Documentación y presentación de información__: se emplea para crear documentos estructurados accesibles a través de la web.

Ventajas de HTML:
* __Simplicidad y facilidad de uso__: rs fácil de aprender y escribir, lo que permite a los desarrolladores crear páginas web de manera rápida.
* __Estándar abierto y universal__: HTML es un estándar mantenido por el W3C y es compatible con todos los navegadores web modernos.
* __Integración con otras tecnologías__: funciona de la mano con CSS para diseño y con JavaScript para interactividad, lo que lo hace muy flexible y poderoso.

Desventajas de HTML:
* __Limitado en Funcionalidades Dinámicas__: HTML solo define la estructura y contenido, pero no puede manejar lógica de negocio o interactividad avanzada sin la ayuda de lenguajes de scripting como JavaScript.
* __Dependencia de CSS y JavaScript__: para crear páginas modernas y atractivas, HTML necesita combinarse con CSS y JavaScript, lo que incrementa la complejidad del desarrollo.

La siguiente tabla muestra las distintas versiones de HTML y su año de lanzamiento:

| Versión     | Año de Lanzamiento | Nombre del Estándar                       |
|-------------|--------------------|-------------------------------------------|
| HTML 1.0    | 1993               | HyperText Markup Language (HTML) 1.0      |
| HTML 2.0    | 1995               | HyperText Markup Language (HTML) 2.0      |
| HTML 3.2    | 1997               | HyperText Markup Language (HTML) 3.2      |
| HTML 4.0    | 1997               | HyperText Markup Language (HTML) 4.0      |
| HTML 4.01   | 1999               | HyperText Markup Language (HTML) 4.01     |
| HTML 5      | 2014               | HTML5                                     |

Descripción de las versiones:
* __HTML 1.0__: primera versión oficial de HTML, creada por Tim Berners-Lee, estableciendo las bases para la estructura de los documentos web.
* __HTML 2.0__: estandarizó muchas características que se usaban en HTML 1.0, como formularios y tablas.
* __HTML 3.2__: introdujo nuevas capacidades como scripts y soportes de elementos para mejorar la presentación.
* __HTML 4.0__: aumentó el soporte para multimedia, scripts y el uso de CSS para la separación de estilo y contenido.
* __HTML 4.01__: mejoró la especificación previa con correcciones y aclaraciones.
* __HTML 5__: la versión más moderna, introdujo nuevas APIs, soportes para gráficos, multimedia, y un enfoque en la interoperabilidad de la web.

## XHTML

__XHTML__ (_Extensible HyperText Markup Language_) es una versión de _HTML_ que sigue las reglas más estrictas de _XML_, combinando la flexibilidad de _HTML_ con la estructura rigurosa de _XML_. _XHTML_ fue desarrollado para asegurar que los documentos web fueran más consistentes y más fácilmente comprensibles tanto por los navegadores como por otras aplicaciones.

Las versiones de XHTML son las siguientes:

| Versión     | Año de Lanzamiento | Nombre del Estándar                       |
|-------------|--------------------|-------------------------------------------|
| XHTML 1.0   | 2000               | Extensible HyperText Markup Language 1.0  |
| XHTML 1.1   | 2001               | Extensible HyperText Markup Language 1.1  |

Descripción de las versiones:
* __XHTML 1.0 y 1.1__: una reformulación de HTML 4.0 siguiendo las reglas de XML para un mayor rigor sintáctico.

Características de XHTML:
* __XHTML 1.0__: Incluye tres variantes: Strict, Transitional, y Frameset.
* __XHTML 1.1__: Más modular y adaptable, utilizado principalmente en contextos donde se requiere un marcado limpio y riguroso.

* __Sintaxis Estricta__: XHTML exige que todos los elementos estén correctamente anidados y cerrados, y que los nombres de las etiquetas y atributos sean siempre en minúsculas.
* __Compatibilidad con XML__: XHTML se puede manipular con herramientas XML, lo que facilita la integración de la web con otras tecnologías basadas en XML.
* __Compatibilidad con HTML__: XHTML mantiene la misma estructura básica y semántica que HTML, lo que hace que la transición sea relativamente sencilla para los desarrolladores.

__XHTML 1.0 Strict__
El DTD "Strict" no permite etiquetas de presentación obsoletas como \<font\> ni atributos como align que controlan la presentación directamente:

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" 
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="es">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <title>Documento XHTML Ejemplo (Strict)</title>
</head>
<body>
    <h1>Bienvenido a XHTML Strict</h1>
    <p>Este es un ejemplo de un documento escrito en XHTML Strict.</p>
    <img src="imagen.jpg" alt="Descripción de la imagen" />
    <a href="https://www.ejemplo.com">Visita nuestro sitio web</a>
</body>
</html>
```

__XHTML 1.0 Transitional__

El DTD "Transitional" permite etiquetas y atributos obsoletos que fueron eliminados en la versión Strict, lo que facilita la transición de HTML más antiguo a XHTML.

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="es">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <title>Documento XHTML Ejemplo (Transitional)</title>
</head>
<body>
    <h1>Bienvenido a XHTML Transitional</h1>
    <p>Este es un ejemplo de un documento escrito en XHTML Transitional.</p>
    <img src="imagen.jpg" alt="Descripción de la imagen" />
    <a href="https://www.ejemplo.com">Visita nuestro sitio web</a>
</body>
</html>
```

__XHTML 1.0 Frameset__
El DTD "Frameset" permite el uso de marcos (\<frameset\>), que reemplazan al uso de \<body\>. Este tipo de documento se usa cuando se desea dividir la pantalla del navegador en múltiples ventanas.

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" 
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="es">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <title>Documento XHTML Ejemplo (Frameset)</title>
</head>
<frameset cols="50%,50%">
    <frame src="contenido1.html" />
    <frame src="contenido2.html" />
</frameset>
</html>
```

Descripción de las diferencias:

* __Strict__: requiere un uso más moderno y limpio de las etiquetas, sin elementos de presentación obsoletos.
* __Transitional__: permite el uso de etiquetas de presentación para facilitar la transición de versiones anteriores de HTML a XHTML.
* __Frameset__: específicamente para documentos que necesitan dividir la pantalla en marcos.

Cada DTD tiene su propio conjunto de reglas que define qué tipo de contenido es válido en un documento XHTML, ayudando a los desarrolladores a estructurar sus documentos de acuerdo con las mejores prácticas o necesidades específicas de compatibilidad.

XHTML 1.1 es una versión más estricta y modular de XHTML, diseñada para ser completamente compatible con XML y eliminar los elementos y atributos obsoletos:

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" 
    "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="es">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <title>Documento XHTML 1.1 Ejemplo</title>
</head>
<body>
    <h1>Bienvenido a XHTML 1.1</h1>
    <p>Este es un ejemplo de un documento escrito en XHTML 1.1.</p>
    <img src="imagen.jpg" alt="Descripción de la imagen" />
    <a href="https://www.ejemplo.com">Visita nuestro sitio web</a>
</body>
</html>
```

Diferencias y características de XHTML 1.1:

* __\<!DOCTYPE\>__: declara que el documento es de tipo XHTML 1.1, utilizando su DTD específico.
* __Compatibilidad completa con XML__: XHTML 1.1 está diseñado para ser completamente compatible con XML, eliminando cualquier elemento o atributo que no cumpla con las normas estrictas de XML.
* __Modularidad__: XHTML 1.1 es más modular que las versiones anteriores, lo que permite incluir solo los módulos necesarios para una aplicación específica.
* __xml:lang__ en lugar de __lang__: se utiliza el atributo xml:lang para definir el idioma del documento, en línea con los estándares XML.

> __Nota__: XHTML 1.1 se centra en una estructura más limpia y estandarizada, eliminando características de presentación que deberían ser manejadas por CSS, lo que promueve la separación total de contenido y presentación. Esta versión es ideal para aplicaciones donde la conformidad estricta con XML es crítica.

## Markdown

![][04]

__Markdown__ es un lenguaje de marcado ligero que permite escribir texto con formato utilizando una sintaxis sencilla y fácil de leer. Fue creado por John Gruber en 2004 con la intención de que los textos escritos en Markdown fueran legibles en su forma original, sin requerir una conversión previa para entender el formato aplicado, como sucede con otros lenguajes de marcado como HTML.

Características de Markdown:

* __Simplicidad y facilidad de uso__: Markdown utiliza una sintaxis muy simple y mínima, lo que lo hace fácil de aprender y usar. Se centra en la escritura, permitiendo a los usuarios agregar formato sin distraerse con complejas etiquetas de marcado.
* __Legibilidad__: los documentos en Markdown son legibles en texto plano sin necesidad de procesarlos primero, lo que facilita su uso en entornos donde la accesibilidad y la claridad son importantes, como documentación y correos electrónicos.
* __Conversión a HTML y otros formatos__: Markdown está diseñado para ser convertido fácilmente a HTML, PDF, y otros formatos utilizando conversores como Pandoc o el propio Markdown.pl, la implementación original del lenguaje.

Markdown permite aplicar varios estilos de formato de texto, como:

* __Encabezados__: se usan \# para crear encabezados (\# Encabezado 1, \#\# Encabezado 2, etc.).
* __Listas__: se crean listas con guiones -, asteriscos *, o números para listas ordenadas.
* __Enlaces__: se crean utilizando \[texto del enlace\](URL).
* __Énfasis__: se aplica negrita y cursiva con asteriscos (\_\_negrita\_\_) o guiones bajos (\_cursiva\_).
* __Bloques de código__: se encierran bloques de código con tres acentos graves ``` para mostrar código formateado.

Ejemplo básico de Markdown:

```
# Bienvenido a Markdown

Markdown es un lenguaje de marcado __ligero__ que permite crear contenido con formato de una manera _sencilla_.

## Características Principales

* Fácil de leer y escribir
* Se convierte fácilmente a HTML
* Muy utilizado en documentación y publicaciones web
```

Markdown es ampliamente utilizado debido a su simplicidad, versatilidad y capacidad para formatear texto de manera clara y efectiva. Algunos de los usos más comunes de Markdown son:
* __Documentación técnica y archivos README__: Markdown es la elección preferida para la documentación de software, especialmente en plataformas como GitHub y GitLab. Los archivos README (README.md) escritos en Markdown explican cómo instalar, configurar y usar un software, y se muestran de manera formateada directamente en la interfaz de estas plataformas.
* __Publicaciones en blogs y plataformas Web__: muchas plataformas de blogs como Medium y Dev.to, así como herramientas de escritura como Ghost y Jekyll, permiten a los usuarios escribir contenido en Markdown debido a su facilidad para crear texto enriquecido sin la complejidad de HTML.
* __Notas y aplicaciones de productividad__: aplicaciones como Notion, Obsidian, Bear, y Typora utilizan Markdown para la toma de notas debido a su facilidad de uso y su capacidad para dar formato rápidamente al texto. Markdown facilita la escritura y el formateo de notas con encabezados, listas, enlaces y bloques de código.
* __Correo Electrónico__ : Markdown se usa en aplicaciones de correo electrónico que soportan la conversión de Markdown a HTML para enviar correos electrónicos con formato. Esto es útil para crear correos electrónicos más atractivos sin necesidad de editar en un editor HTML completo.
* __Presentaciones__: herramientas como Reveal.js permiten crear presentaciones de diapositivas a partir de documentos Markdown, facilitando la producción de contenido visualmente atractivo sin la complejidad de los programas tradicionales de presentación.
* __Wikis y documentos internos__: muchas organizaciones utilizan Markdown en wikis internos para documentar procesos, políticas y conocimientos técnicos. Plataformas como Confluence y GitHub Wikis soportan Markdown para crear documentación colaborativa.
* __Escritura y publicación de Libros__: Markdown se utiliza para escribir libros y publicaciones debido a su capacidad para exportar a múltiples formatos, como HTML, PDF, y ePub, mediante herramientas como Pandoc y Scrivener.
* __Comentarios y foros__: plataformas como Reddit, Stack Overflow, y Discord permiten usar Markdown para formatear comentarios y discusiones, haciendo que los mensajes sean más legibles y estructurados.

Ventajas del uso de Markdown:
* __Simplicidad y facilidad de aprendizaje__: Markdown es intuitivo y no requiere conocimientos avanzados de programación o diseño.
* __Legibilidad en texto plano__: los documentos son legibles en su forma sin procesar, lo que facilita la edición y revisión.
* __Portabilidad__: Markdown se puede convertir fácilmente a HTML y otros formatos, lo que lo hace extremadamente versátil.

> __Nota__: Markdown, aunque comparte la simplicidad de YAML y JSON, no se utiliza para la estructura de datos sino para formatear texto, lo que lo hace más cercano a los _lenguajes de marcas_.

[01]: ../img/ut01/gml-logo.png "01"
[02]: ../img/ut01/xml-logo.png "02"
[03]: ../img/ut01/html5-logo.png "03"
[04]: ../img/ut01/markdown-logo.png "04"
