# Ejercicios de Introducción a XML

## Introducción al Lenguaje de Marcas

__Ejercicio 1__

Crear un documento XML llamado `libreria.xml` sobre una librería de libros siguiendo las siguientes indicaciones:

* Cada libro debe tener las siguientes etiquetas: título, autor, año de publicación y precio.
* Añade un atributo moneda al precio para especificar si el precio está en USD o EUR.

| Título                        | Autor         | Año  | Precio  | Moneda |
|-------------------------------|---------------|------|---------|--------|
| XML para principiantes         | Juan Pérez    | 2022 | 25.00   | USD    |
| Guía avanzada de XML           | Ana García    | 2020 | 30.00   | EUR    |
| Introducción a XML             | Marta Fernández| 2019 | 20.00   | USD    |
| Fundamentos de XML             | Carlos López  | 2021 | 35.00   | EUR    |
| XML en profundidad             | Luis Martínez | 2018 | 40.00   | USD    |

El documento debe contener la cabecera XML con los atributos `version` y `encoding`.

__Ejercicio 2__

Crea un documento XML llamado `filmoteca.xml` que describa una colección de películas siguiendo las siguientes indicaciones:

* Cada película debe tener las siguientes etiquetas: título, director, año de lanzamiento, duración, y género.
* El campo _duración_ debe tener un atribute que indique la unidad de tiempo, en este caso _minutos_.
* Añade un atributo calificación que puede ser G, PG, PG-13, R.

| Título                     | Director        | Año  | Duración (min) | Género           | Calificación |
|----------------------------|-----------------|------|----------------|------------------|--------------|
| El Viaje Fantástico         | Pedro González  | 2020 | 120            | Ciencia Ficción  | PG           |
| La Venganza del Dragón      | Ana Martínez    | 2019 | 140            | Acción           | R            |
| La Aventura del Tiempo      | José Sánchez    | 2018 | 115            | Aventura         | PG-13         |
| Misterios del Universo      | Laura López     | 2021 | 130            | Documental       | G            |
| Un Viaje Extraordinario     | Marta Fernández | 2017 | 100            | Drama            | PG           |

El documento debe contener la cabecera XML con los atributos `version` y `encoding`.

__Ejercicio 3__

Crea un documento XML llamado `personas.xml` que describa una lista de personas siguiendo las siguientes indicaciones:

* Cada persona debe tener los siguientes datos: nombre, apellidos, teléfono, email, dirección.
* El campo dirección contiene los siguientes elementos: tipo de vía, nombre, numero.
* Cada persona debe tener un atributo _identificador_ único llamado id.

| ID  | Nombre   | Apellidos         | Teléfono   | Email                    | Vía     | Nombre de la Vía | Número |
|-----|----------|-------------------|------------|--------------------------|---------|------------------|--------|
| 1   | Juan     | Pérez López       | 123456789  | juan.perez@example.com    | Calle   | Gran Vía          | 100    |
| 2   | María    | García Fernández  | 987654321  | maria.garcia@example.com  | Avenida | Constitución      | 50     |
| 3   | Carlos   | López Martínez    | 1122334455 | carlos.lopez@example.com  | Calle   | Serrano           | 35     |
| 4   | Ana      | Ruiz Sánchez      | 2233445566 | ana.ruiz@example.com      | Plaza   | Mayor             | 10     |
| 5   | Laura    | Torres Gómez      | 3344556677 | laura.torres@example.com  | Camino  | El Prado          | 8      |

El documento debe contener la cabecera XML con los atributos `version` y `encoding`.

__Ejercicio 4__

Crea un documento XML llamado `maquinas-virtuales.xml` que modele la configuración de tres máquinas virtuales que tengas configuradas en VirtualBox. Cada máquina virtual debe contener los siguientes campos:

* Nombre de la máquina virtual
* CPU (número de núcleos)
* RAM (en MB): especificar un atributo que indique la unidad de almacenamiento.
* Disco: ruta absoluta en el sistema al archivo del disco duro. Especificar un atributo que indique el tipo de disco (puede ser vdi o vmdk).
* Tamaño del disco (en GB): especificar un atributo que indique la unidad de almacenamiento.
* Adaptador de red: especificar si el adaptador de red está en modo `NAT` o `adaptador puente`.
* Cada máquina virtual debe tener un atributo _identificador_ único llamado id.

Si el adaptador NAT está en modo `NAT`, se deben especificar también las reglas de reenvío de puertos configuradas.

__Ejercicio 5__

Crea un docuemnto XML llamado `factura.xml`que modele la siguiente factura:

![][01]

[01]: ./factura01.webp "01"