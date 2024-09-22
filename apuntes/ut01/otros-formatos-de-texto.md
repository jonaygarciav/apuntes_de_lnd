# Introducción a los Lenguajes de Marcas

* Json
* Yaml
* Toml

## JSON

![][01]

__JSON__ (_JavaScript Object Notation_) es un formato de texto ligero y legible para el intercambio de datos. Es ampliamente utilizado en aplicaciones web y APIs para enviar datos estructurados entre un servidor y un cliente. Aunque se deriva de la sintaxis de JavaScript, JSON es independiente del lenguaje de programación y es compatible con casi todos los lenguajes de programación modernos. _JSON_ fue desarrollado por Douglas Crockford a principios de la década de 2000 como una alternativa más simple y fácil de usar que XML para la transferencia de datos en aplicaciones web. La facilidad de uso y la simplicidad de _JSON_, junto con su compatibilidad con JavaScript, lo hicieron rápidamente popular como el formato estándar para el intercambio de datos en la web.

Características principales de JSON:
* __Simplicidad y legibilidad__: JSON utiliza una estructura sencilla basada en pares clave-valor, listas y objetos anidados, lo que lo hace fácil de leer y escribir tanto para humanos como para máquinas.
* __Independencia de lenguaje__: aunque JSON se deriva de JavaScript, se puede utilizar con casi cualquier lenguaje de programación, lo que lo convierte en un formato altamente interoperable.
* __Estructura clara_: JSON tiene una sintaxis clara y estricta que define cómo se deben estructurar los datos, lo que facilita la validación y el procesamiento.

Un archivo JSON está compuesto por:
* __Objetos__: definidos por llaves {}, que contienen pares clave-valor.
* __Arreglos__: listas de valores definidos por corchetes [].
* __Pares clave-valor__: claves y valores separados por dos puntos :, donde las claves son cadenas y los valores pueden ser cadenas, números, booleanos, nulos, objetos o arreglos.

Ejemplo básico de JSON:

```
{
  "nombre": "Juan Pérez",
  "edad": 30,
  "esEstudiante": false,
  "cursos": ["Matemáticas", "Física", "Programación"],
  "direccion": {
    "calle": "Calle Principal",
    "ciudad": "Ciudad Ejemplo",
    "codigoPostal": 12345
  }
}
```

__Objetos JSON__

Los _objetos_ en JSON son una colección de pares clave-valor. Se encierran entre llaves «{}» y cada clave se separa de su valor correspondiente por dos puntos «:». Los pares clave-valor se separan entre sí por comas «,».

Un ejemplo de _objeto_ JSON lo podemos ver en el código siguiente:

```
{
    'nombre': 'Facundo',
    'edad': 30,
    'ciudad': 'Madrid'
}
```

Este _objeto_ JSON consta de tres pares clave-valor:

* La clave _nombre_ tiene el valor _Facundo_.
* La clave _edad_ es _30_.
* La clave _ciudad_ tiene el valor _Madrid_.

__Arreglos JSON__

Los _arreglos_ o _arrays_ JSON son simples colecciones de elementos. Estos elementos pueden ser datos como números o cadenas pero también otros arreglos u objetos JSON.

Los _arrays_ se encierran entre corchetes «[]» y los valores se separan entre sí por comas «,». Cada objeto en el array representa una persona, con información sobre su nombre, edad y ciudad:

```
[
    {
        'nombre': 'Facundo',
        'edad': 30,
        'ciudad': 'Madrid'
    },
    {
        'nombre': 'Saturnina',
        'edad': 98,
        'ciudad': 'Barcelona'
    },
    {
        'nombre': 'Adoración',
        'edad': 55,
        'ciudad': 'Sevilla'
    }
]
```
Aplicaciones comunes de JSON:
* __Intercambio de Datos en APIs__: JSON es el formato más común para enviar y recibir datos entre un servidor y un cliente en aplicaciones web, especialmente en servicios RESTful.
* __Configuración de aplicaciones__: JSON se utiliza frecuentemente para archivos de configuración debido a su legibilidad y facilidad de manipulación.
* __Almacenamiento de datos__: algunas bases de datos NoSQL, como MongoDB, utilizan estructuras similares a JSON para almacenar datos de manera flexible.

Ventajas de JSON:
* __Ligero y eficiente__: JSON tiene una sintaxis concisa que facilita la transmisión de datos con menos sobrecarga en comparación con otros formatos.
* __Fácil de analizar__: la mayoría de los lenguajes de programación ofrecen librerías y funciones integradas para analizar y generar JSON, lo que simplifica su uso en el desarrollo.
* __Legibilidad__: a diferencia de formatos como XML, JSON es mucho más fácil de leer y escribir para los desarrolladores, lo que reduce los errores y facilita la depuración.

Desventajas de JSON:
* __Sin comentarios__: JSON no soporta comentarios, lo que puede dificultar la documentación de los datos directamente en el archivo.
* __Menos estricto que XML__: JSON carece de validación de esquema incorporada, lo que significa que los datos mal formateados pueden causar errores durante el procesamiento.

Comparación con otros formatos de datos:
* __JSON vs XML__: aunque XML fue inicialmente utilizado para los servicios web y el intercambio de datos en general, con el tiempo JSON ha venido desplazando a XML debido a su simplicidad y eficiencia. JSON tiene una sintaxis más simple y es más fácil de leer y escribir que XML. Además, JSON es más ligero, no solo para su transmisión sino también para el procesamiento de los datos. Por ello resulta más eficiente.
* __JSON vs CSV__: CSV es otro formato comúnmente utilizado para el intercambio de datos, especialmente útil para exportar información. Aunque CSV es simple y ligero, no es tan fácil de leer y asimilar qué función realiza cada dato. Además CSV no resulta nada flexible, porque las columnas siempre tienen una serie limitada y definida de valores. En cambio JSON soporta estructuras de datos complejas y variables entre sí. 

JSON ha revolucionado la forma en que las aplicaciones web y los sistemas distribuidos manejan los datos, convirtiéndose en un estándar debido a su simplicidad y eficacia. Desde la configuración de aplicaciones hasta la transferencia de datos en tiempo real, JSON sigue siendo una herramienta esencial en el desarrollo moderno.

A continuación, se muestra el código de un fichero en Python llamado _lee-json.py_ que lee el archivo en formato JSON _usuarios.json_ y lo muestra por pantalla:

```
import json

# Nombre del fichero JSON que se va a leer
nombre_fichero = 'usuarios.json'

# Función para abrir y leer el fichero JSON
def leer_fichero_json(fichero):
    try:
        # Abrir el fichero en modo lectura
        with open(fichero, 'r', encoding='utf-8') as archivo:
            # Cargar el contenido del JSON
            datos = json.load(archivo)
            
            # Comprobar si los datos son una lista
            if isinstance(datos, list):
                print("Contenido del archivo JSON:")
                # Iterar sobre cada elemento de la lista
                for i, item in enumerate(datos, start=1):
                    print(f"\nRegistro {i}:")
                    for clave, valor in item.items():
                        print(f"{clave}: {valor}")
            else:
                print("El contenido del JSON no es una lista.")
                
    except FileNotFoundError:
        print(f"El archivo {fichero} no se encontró.")
    except json.JSONDecodeError:
        print("Error al decodificar el archivo JSON.")
    except Exception as e:
        print(f"Ocurrió un error: {e}")

# Llamada a la función para leer el fichero JSON
leer_fichero_json(nombre_fichero)
```

El programa _usuarios.json_ tiene el siguiente contenido:

```
$ cat alumnos.json 
[
    {
        "ID": 1,
        "Nombre": "Juan Pérez",
        "Correo": "juan.perez@mail.com",
        "Fecha de Registro": "2024-09-15"
    },
    {
        "ID": 2,
        "Nombre": "María García",
        "Correo": "maria.garcia@mail.com",
        "Fecha de Registro": "2024-09-16"
    },
    {
        "ID": 3,
        "Nombre": "Carlos Sánchez",
        "Correo": "carlos.sanchez@mail.com",
        "Fecha de Registro": "2024-09-17"
    },
    {
        "ID": 4,
        "Nombre": "Ana López",
        "Correo": "ana.lopez@mail.com",
        "Fecha de Registro": "2024-09-18"
    },
    {
        "ID": 5,
        "Nombre": "Luis Fernández",
        "Correo": "luis.fernandez@mail.com",
        "Fecha de Registro": "2024-09-19"
    }
]
```

La ejecución del programa _lee-json.py_ sería la siguiente:

```
$ python3 lee-json.py 
Contenido del archivo JSON:

Registro 1:
ID: 1
Nombre: Juan Pérez
Correo: juan.perez@mail.com
Fecha de Registro: 2024-09-15

Registro 2:
ID: 2
Nombre: María García
Correo: maria.garcia@mail.com
Fecha de Registro: 2024-09-16

Registro 3:
ID: 3
Nombre: Carlos Sánchez
Correo: carlos.sanchez@mail.com
Fecha de Registro: 2024-09-17

Registro 4:
ID: 4
Nombre: Ana López
Correo: ana.lopez@mail.com
Fecha de Registro: 2024-09-18

Registro 5:
ID: 5
Nombre: Luis Fernández
Correo: luis.fernandez@mail.com
Fecha de Registro: 2024-09-19
```

## YAML

![][02]

__YAML__ es un lenguaje de serialización de datos diseñado para ser legible tanto para humanos como para máquinas. A menudo se utiliza en la configuración de aplicaciones, scripts de automatización, y como una alternativa más simple y comprensible a JSON y XML. YAML está diseñado para ser fácil de leer y escribir, con una sintaxis limpia y mínima que hace énfasis en la claridad. YAML fue desarrollado en 2001 por Clark Evans, con la ayuda de Ingy döt Net y Oren Ben-Kiki, como un lenguaje de serialización que se centra en la simplicidad y la legibilidad. Originalmente, YAML significaba _"Yet Another Markup Language"_, pero sus creadores cambiaron el nombre a _"YAML Ain't Markup Language"_ para enfatizar que no es un lenguaje de marcado, sino un lenguaje de serialización.

Características principales de YAML:
* __Legibilidad__: YAML está diseñado para ser legible por humanos, utilizando una estructura de sangría que facilita la comprensión del contenido.
* __Sintaxis simple__: utiliza espacios en blanco, guiones, y dos puntos para definir listas, objetos y pares clave-valor, eliminando la necesidad de símbolos complicados como corchetes o llaves.
* __Compatibilidad con JSON__: YAML es un superconjunto de JSON, lo que significa que cualquier archivo JSON válido también es un archivo YAML válido. Esto facilita la interoperabilidad entre los dos formatos.

Estructura Básica de YAML:
* __Listas__: se definen con guiones -.
* __Objetos__: utilizan pares clave-valor con dos puntos :.
* __Comentarios__: se agregan con #, lo cual es útil para documentar y explicar el contenido.

Ejemplo básico de YAML:

```
nombre: Juan Pérez
edad: 30
esEstudiante: false
cursos:
  - Matemáticas
  - Física
  - Programación
direccion:
  calle: Calle Principal
  ciudad: Ciudad Ejemplo
  codigoPostal: 12345
```

Aplicaciones comunes de YAML:
* __Archivos de configuración__: YAML se utiliza ampliamente en archivos de configuración para aplicaciones y herramientas de desarrollo como Docker (docker-compose.yml), Kubernetes, Ansible, y otros sistemas de automatización.
* __Automatización y DevOps__: herramientas de automatización como Ansible utilizan YAML para definir playbooks y tareas debido a su claridad y facilidad de uso.
* __Definición de infraestructura__: plataformas como Kubernetes utilizan YAML para describir la configuración y despliegue de servicios, contenedores, y recursos.

Ventajas de YAML: 
* __Fácil de leer y escribir__: gracias a su sintaxis basada en sangrías y espacios en blanco, es intuitivo y accesible para personas que no tienen conocimientos técnicos profundos.
* __Flexible y extensible__: permite definir estructuras de datos complejas de manera sencilla y sin la necesidad de caracteres innecesarios.
* __Compatibilidad con JSON__: permite una integración fluida con otras aplicaciones y lenguajes que utilizan JSON, gracias a su compatibilidad.

Desventajas de YAML:
* __Sensibilidad a la sangría__: al igual que Python, YAML es sensible a los espacios y sangrías, lo que puede llevar a errores si no se tiene cuidado al formatear el documento.
* __Complejidad en datos anidados__: aunque es legible, YAML puede volverse complejo y difícil de mantener en archivos muy grandes o con muchas estructuras anidadas.

YAML es una herramienta poderosa y flexible para la configuración y serialización de datos, especialmente en entornos de DevOps y automatización. Su diseño centrado en la legibilidad lo hace ideal para tareas que requieren claridad y simplicidad en la definición de estructuras de datos.

## TOML

![][03]

__TOML__ es un lenguaje de configuración diseñado para ser fácil de leer y escribir debido a su estructura clara y mínima. Fue creado por Tom Preston-Werner, uno de los cofundadores de GitHub, como una alternativa más simple y legible a otros formatos de configuración como JSON, YAML y XML. TOML fue creado por Tom Preston-Werner en 2013 con el objetivo de proporcionar un formato de configuración que sea sencillo y directo, eliminando la complejidad y verbosidad de otros lenguajes. Su principal objetivo es definir configuraciones de software de manera que los archivos resultantes sean fáciles de comprender y modificar, incluso para personas que no son desarrolladores.

Características principales de TOML:
* __Legibilidad__: TOML está diseñado para ser intuitivo y fácil de leer, con una sintaxis que recuerda a INI pero con mayor estructura y capacidad de anidación.
* __Estructura clara__: utiliza secciones, tablas y pares clave-valor, lo que hace que el formato sea limpio y bien organizado.
* __Compatibilidad con múltiples tipos de datos__: soporta tipos de datos comunes como cadenas, números, booleanos, fechas, arreglos, y tablas, lo que permite la creación de configuraciones complejas de manera sencilla.

Estructura básica de TOML:
* __Tablas__: las tablas son secciones de configuración definidas por corchetes [].
* __Claves y valores__: definidos mediante un signo igual =, donde las claves son siempre cadenas sin necesidad de comillas.
* __Arreglos__: listas de valores definidos por corchetes [].
* __Comentarios__: utilizan # y se pueden añadir en cualquier parte del archivo.

Ejemplo Básico de TOML:

```
# Configuración del usuario
nombre = "Juan Pérez"
edad = 30
es_estudiante = false

# Cursos del usuario
cursos = ["Matemáticas", "Física", "Programación"]

# Dirección del usuario
[direccion]
calle = "Calle Principal"
ciudad = "Ciudad Ejemplo"
codigo_postal = 12345
```

Aplicaciones Comunes de TOML:
* __Archivos de configuración de software__: TOML se utiliza en muchas aplicaciones para definir configuraciones de software, especialmente en proyectos de desarrollo como Rust y Go, donde TOML es utilizado por defecto en herramientas de administración de paquetes como Cargo.
* __Configuración de entornos y herramientas__: utilizado en herramientas de desarrollo como configuraciones de entornos, servidores, y aplicaciones donde la claridad y la facilidad de modificación son esenciales.
* __Automatización__: utilizado en scripts y aplicaciones de automatización debido a su capacidad para gestionar configuraciones de forma simple y accesible.

Ventajas de TOML:
* __Simplicidad y estructura__: TOML es fácil de leer y escribir, con una sintaxis que evita la complejidad de YAML y la verbosidad de JSON.
* __Separación clara de secciones__: las tablas permiten organizar la configuración en secciones claras y diferenciadas, mejorando la organización del contenido.
* __Soporte de tipos complejos__: permite gestionar múltiples tipos de datos, incluyendo fechas y horas, lo que lo hace adecuado para una amplia gama de aplicaciones.

Desventajas de TOML:
* __Menos soporte en herramientas antiguas__: aunque su popularidad está creciendo, TOML aún no es tan ampliamente soportado como JSON o YAML en algunas herramientas más antiguas.
* __Limitaciones en complejidad__: aunque es excelente para configuraciones sencillas y moderadamente complejas, TOML no es ideal para datos muy anidados o altamente estructurados, donde YAML podría ser más flexible.

TOML es un lenguaje de configuración eficiente y fácil de usar que se está convirtiendo en una opción popular para los desarrolladores que necesitan un formato de configuración simple y accesible. Su claridad y legibilidad hacen de TOML una excelente opción para gestionar configuraciones de software y entornos.

[01]: ../img/ut01/json-logo.png "01"
[02]: ../img/ut01/yaml-logo.png "02"
[03]: ../img/ut01/toml-logo.png "03"
