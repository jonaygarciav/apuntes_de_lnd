# Sistemas de Codificación

* Introducción
* Sistemas de codificación numéricos
  * Sistema binario
  * Sistema hexadecimal
* Sistemas de codificación de caracteres
  * Codigo ASCII
  * ASCII Extendido
  * Unicode

## Introducción

#TODO

## Bits como números

### Sistemas de codificación numéricos

El _sistema binario_ es un sistema de numeración en el que solo se utilizan dos dígitos: el 0 y el 1. Este sistema es la base de la informática, ya que los ordenadores trabajan internamente con este formato debido a su facilidad para representar estados de encendido y apagado (1 y 0).

A continuación se muestra una tabla con la conversión de los números en decimal del 0 al 15 a binario en grupos de 8 bits:

| **Decimal** | **Binario**   | **Decimal** | **Binario**   |
|-------------|---------------|-------------|---------------|
| 0           | 0000 0000     | 8           | 0000 1000     |
| 1           | 0000 0001     | 9           | 0000 1001     |
| 2           | 0000 0010     | 10          | 0000 1010     |
| 3           | 0000 0011     | 11          | 0000 1011     |
| 4           | 0000 0100     | 12          | 0000 1100     |
| 5           | 0000 0101     | 13          | 0000 1101     |
| 6           | 0000 0110     | 14          | 0000 1110     |
| 7           | 0000 0111     | 15          | 0000 1111     |

> __Nota__: un grupo de 8 bits se conoce como _byte_ u _octeto_.

### Sistema hexadecimal

El _sistema hexadecimal_ es un sistema de numeración que utiliza 16 dígitos: 0-9 y las letras A-F (donde A representa 10, B representa 11, y así sucesivamente hasta F, que representa 15). Cada dígito es un grupo de 4 bits:

| **Binario**         | **Hexadecimal** | **Binario**         | **Hexadecimal** |
|---------------------|-----------------|---------------------|-----------------|
| 0000                | 0               | 1000                | 8               |
| 0001                | 1               | 1000                | 8               |
| 0010                | 2               | 1010                | A               |
| 0011                | 3               | 1011                | B               |
| 0100                | 4               | 1100                | C               |
| 0101                | 5               | 1101                | D               |
| 0110                | 6               | 1110                | E               |
| 0111                | 7               | 1111                | F               |

Sus principales usos son:

* __Representación de Colores en Web (HTML/CSS)__: los colores se representan comúnmente en formato hexadecimal en diseño web. Por ejemplo, el color blanco se representa como #FFFFFF y el negro como #000000.
* __Direcciones MAC__: las direcciones MAC de los dispositivos de red (como tarjetas de red y routers) se escriben en formato hexadecimal, por ejemplo, 00:1A:2B:3C:4D:5E.
* __Codificación de Caracteres Unicode__: los caracteres Unicode pueden ser representados en hexadecimal, por ejemplo, U+0041 representa la letra "A".
* __Criptografía__: los valores de hashes y claves de cifrado, como MD5 o SHA-256, suelen presentarse en formato hexadecimal.
* __Direcciones IPv6__: las direcciones IPv6 utilizan el sistema hexadecimal para comprimir largas secuencias de bits en un formato más manejable, por ejemplo, 2001:0db8:85a3:0000:0000:8a2e:0370:7334.

> __Nota__: un grupo de 4 bits se conoce como _nibble_.

## Sistemas de codificación de caracteres

### Codigo ASCII

_ASCII_ (_American Standard Code for Information Interchange_) es un código de caracteres que se utiliza para representar texto y otros símbolos en un ordenador, dispositivos de comunicación y otros equipos que utilizan texto. ASCII se basa en el alfabeto inglés y define 128 caracteres, que incluyen letras, números, signos de puntuación, caracteres de control y otros símbolos. Cada carácter se representa mediante un valor numérico en el rango de 0 a 127 y utiliza un conjunto de 7 bits para representar cada caracter ASCII.

Los primeros 32 caracteres (0-31) y el carácter 127 son caracteres de control, utilizados para controlar dispositivos periféricos como impresoras o para enviar comandos especiales, como nueva línea o tabulación.

A continuación, se muestra la tabla de caracteres ASCII:

| **Código ASCII** | **Binario (7 bits)** | **Hexadecimal** | **Carácter**                | **Código ASCII** | **Binario (7 bits)** | **Hexadecimal** | **Carácter**                |
|------------------|----------------------|-----------------|-----------------------------|------------------|----------------------|-----------------|-----------------------------|
| 0                | 0000000              | 00              | NUL (Carácter Nulo)         | 64               | 1000000              | 40              | @                           |
| 1                | 0000001              | 01              | SOH (Inicio de Encabezado)  | 65               | 1000001              | 41              | A                           |
| 2                | 0000010              | 02              | STX (Inicio de Texto)       | 66               | 1000010              | 42              | B                           |
| 3                | 0000011              | 03              | ETX (Fin de Texto)          | 67               | 1000011              | 43              | C                           |
| 4                | 0000100              | 04              | EOT (Fin de Transmisión)    | 68               | 1000100              | 44              | D                           |
| 5                | 0000101              | 05              | ENQ (Consulta)              | 69               | 1000101              | 45              | E                           |
| 6                | 0000110              | 06              | ACK (Reconocimiento)        | 70               | 1000110              | 46              | F                           |
| 7                | 0000111              | 07              | BEL (Campana)               | 71               | 1000111              | 47              | G                           |
| 8                | 0001000              | 08              | BS (Retroceso)              | 72               | 1001000              | 48              | H                           |
| 9                | 0001001              | 09              | HT (Tabulación Horizontal)  | 73               | 1001001              | 49              | I                           |
| 10               | 0001010              | 0A              | LF (Salto de Línea)         | 74               | 1001010              | 4A              | J                           |
| 11               | 0001011              | 0B              | VT (Tabulación Vertical)    | 75               | 1001011              | 4B              | K                           |
| 12               | 0001100              | 0C              | FF (Avance de Página)       | 76               | 1001100              | 4C              | L                           |
| 13               | 0001101              | 0D              | CR (Retorno de Carro)       | 77               | 1001101              | 4D              | M                           |
| 14               | 0001110              | 0E              | SO (Desplazamiento Salida)  | 78               | 1001110              | 4E              | N                           |
| 15               | 0001111              | 0F              | SI (Desplazamiento Entrada) | 79               | 1001111              | 4F              | O                           |
| 16               | 0010000              | 10              | DLE (Escape de Enlace de Datos) | 80           | 1010000              | 50              | P                           |
| 17               | 0010001              | 11              | DC1 (Control de Dispositivo 1) | 81            | 1010001              | 51              | Q                           |
| 18               | 0010010              | 12              | DC2 (Control de Dispositivo 2) | 82            | 1010010              | 52              | R                           |
| 19               | 0010011              | 13              | DC3 (Control de Dispositivo 3) | 83            | 1010011              | 53              | S                           |
| 20               | 0010100              | 14              | DC4 (Control de Dispositivo 4) | 84            | 1010100              | 54              | T                           |
| 21               | 0010101              | 15              | NAK (Reconocimiento Negativo) | 85            | 1010101              | 55              | U                           |
| 22               | 0010110              | 16              | SYN (Sincronización Inactiva) | 86            | 1010110              | 56              | V                           |
| 23               | 0010111              | 17              | ETB (Fin de Bloque)         | 87               | 1010111              | 57              | W                           |
| 24               | 0011000              | 18              | CAN (Cancelar)              | 88               | 1011000              | 58              | X                           |
| 25               | 0011001              | 19              | EM (Fin de Medio)           | 89               | 1011001              | 59              | Y                           |
| 26               | 0011010              | 1A              | SUB (Sustituto)             | 90               | 1011010              | 5A              | Z                           |
| 27               | 0011011              | 1B              | ESC (Escape)                | 91               | 1011011              | 5B              | [                           |
| 28               | 0011100              | 1C              | FS (Separador de Archivo)   | 92               | 1011100              | 5C              | \                           |
| 29               | 0011101              | 1D              | GS (Separador de Grupo)     | 93               | 1011101              | 5D              | ]                           |
| 30               | 0011110              | 1E              | RS (Separador de Registro)  | 94               | 1011110              | 5E              | ^                           |
| 31               | 0011111              | 1F              | US (Separador de Unidad)    | 95               | 1011111              | 5F              | _                           |
| 32               | 0100000              | 20              | Espacio                     | 96               | 1100000              | 60              | `                           |
| 33               | 0100001              | 21              | !                           | 97               | 1100001              | 61              | a                           |
| 34               | 0100010              | 22              | "                           | 98               | 1100010              | 62              | b                           |
| 35               | 0100011              | 23              | #                           | 99               | 1100011              | 63              | c                           |
| 36               | 0100100              | 24              | $                           | 100              | 1100100              | 64              | d                           |
| 37               | 0100101              | 25              | %                           | 101              | 1100101              | 65              | e                           |
| 38               | 0100110              | 26              | &                           | 102              | 1100110              | 66              | f                           |
| 39               | 0100111              | 27              | '                           | 103              | 1100111              | 67              | g                           |
| 40               | 0101000              | 28              | (                           | 104              | 1101000              | 68              | h                           |
| 41               | 0101001              | 29              | )                           | 105              | 1101001              | 69              | i                           |
| 42               | 0101010              | 2A              | *                           | 106              | 1101010              | 6A              | j                           |
| 43               | 0101011              | 2B              | +                           | 107              | 1101011              | 6B              | k                           |
| 44               | 0101100              | 2C              | ,                           | 108              | 1101100              | 6C              | l                           |
| 45               | 0101101              | 2D              | -                           | 109              | 1101101              | 6D              | m                           |
| 46               | 0101110              | 2E              | .                           | 110              | 1101110              | 6E              | n                           |
| 47               | 0101111              | 2F              | /                           | 111              | 1101111              | 6F              | o                           |
| 48               | 0110000              | 30              | 0                           | 112              | 1110000              | 70              | p                           |
| 49               | 0110001              |

* __Caracteres Imprimibles__: son aquellos que representan símbolos visibles que se pueden mostrar en la pantalla o imprimir en papel. Estos incluyen letras, números, signos de puntuación y símbolos especiales.
* __Caracteres de control__:  son aquellos que no se representan como símbolos visibles, sino que se utilizan para controlar dispositivos (como impresoras) o para gestionar el flujo de datos en la comunicación. Estos caracteres suelen realizar funciones específicas como mover el cursor, iniciar una nueva línea o enviar comandos a periféricos.


Ventajas de ASCII:

* __Simplicidad y Facilidad de Uso__: ASCII es fácil de entender y utilizar, ya que asigna un valor numérico a cada carácter común, como letras, números y símbolos.
* __Compatibilidad Universal__: debido a su antigüedad y uso extensivo, ASCII es compatible con casi todos los sistemas informáticos y dispositivos de comunicación.
* __Tamaño Reducido__: utiliza solo 7 bits por carácter, lo que lo hace eficiente en términos de almacenamiento y procesamiento de datos.
* __Estándar para la Comunicación__: ASCII se convirtió en un estándar para la transmisión de texto en comunicaciones y protocolos de red, como SMTP para correo electrónico.
* __Soporte para Caracteres de Control__ : incluye caracteres de control que permiten manejar tareas como tabulaciones, saltos de línea y comandos de dispositivos periféricos.
* __Base para Otros Códigos__: ASCII sirvió de base para la creación de otros estándares, como ASCII Extendido y UTF-8, que amplían el soporte a caracteres de diferentes idiomas.

Desventajas de ASCII:

* __Limitación de caracteres__: ASCII solo puede representar 128 caracteres, lo que lo hace insuficiente para manejar idiomas con alfabetos más grandes, como chino, árabe o cualquier otro idioma que no use el alfabeto latino.
* __Sin soporte para caracteres especiales y acentos__: no incluye caracteres con acentos, símbolos de monedas internacionales, o letras no latinas, lo que limita su utilidad en aplicaciones globales.
* __Obsoleto para aplicaciones modernas__: ASCII no puede manejar emojis, caracteres especiales modernos o gráficos, que son comunes en la comunicación actual.
* __No escalable__: la limitación de 7 bits hace que ASCII no pueda ampliarse sin perder compatibilidad con los sistemas que lo utilizan, de ahí la necesidad de códigos más completos como Unicode.

### ASCII Extendido

__ASCII Extendido__ es una ampliación del código ASCII original de 7 bits que añade 128 caracteres adicionales, ampliando así el rango de 0 a 255 (utilizando 8 bits en lugar de 7). Esta extensión permite incluir más símbolos, caracteres gráficos, acentos y letras especiales que no están presentes en el estándar ASCII básico.

Los primeros 128 caracters de código ASCII Extendido coinciden con los 128 caracteres de ASCII, con lo cual el código ASCII Extendido es compatible con el código ASCII, mientras que los últimos 128 caracteres se utilizan para representar distintos caracteres extra que no se encuentran en la codificación ASCII en función de la zona geográfica concreta. Hay distintos tipos de formatos ASCII Extendido en función de la zona geográfica:

* __ISO 8859-1__: ASCII extendido para Europa Occidental (incluye símbolos como ñ o β)
* __ISO 8859-2__: ASCII extendido para Europa Central y del Este (incluye símbolos como Ź o č)
* __ISO 8859-3__: ASCII extendido para Europa del Sur (incluye símbolos como Ġ o Ï)
* __ISO 8859-4__: ASCII extendido para Europa del Norte (incluye símbolos como ø o å)
* __ISO 8859-5__: ASCII extendido para alfabeto cirílico (incluye símbolos como д o Ж)
* __ISO 8859-6__: ASCII extendido para alfabeto árabe (incluye símbolos como ن o ي)
* __ISO 8859-7__: ASCII extendido para alfabeto griego moderno (incluye símbolos como φ o α)
* __ISO 8859-8__: ASCII extendido para alfabeto hebreo (incluye símbolos como ץ o ק)
* __ISO 8859-9__: ASCII extendido, versión de 8859-1 que incluye símbolos turcos en lugar de otros poco utilizados.
* __ISO 8859-10__: ASCII extendido, versión de 8859-4 que incluye símbolos más utilizados en las lenguas nórdicas actuales.
* __ISO 8859-11__: ASCII extendido para alfabeto tailandés (incluye símbolos como ๗ o ๔)
* __ISO 8859-12__: ASCII extendido para alfabeto devanagari de India y Nepal que ya no se usa
* __ISO 8859-13__: ASCII extendido para alfabetos bálticos con símbolos que no estaban en 8859-4
* __ISO 8859-14__: ASCII extendido para alfabeto celta (incluye símbolos como ŵ o Ẃ)
* __ISO 8859-15__: ASCII extendido, versión de 8859-1 que incluye el símbolo del euro y símbolos de lenguas bálticas. Es el recomendado actualmente para Europa Occidental.
* __ISO 8859-16__: ASCII extendido, versión de 8859-1 pensada para los países del sureste de Europa

A continuación, se muestra la tabla de caracteres ASCII Extendido 8859-15:

| **Código ASCII Extendido** | **Binario (8 bits)** | **Hexadecimal** | **Carácter** | **Código ASCII Extendido** | **Binario (8 bits)** | **Hexadecimal** | **Carácter**                |
|----------------------------|----------------------|-----------------|--------------|----------------------------|----------------------|-----------------|-----------------------------|
| 128                        | 10000000             | 80              | €            | 192                        | 11000000             | C0              | À                           |
| 129                        | 10000001             | 81              |              | 193                        | 11000001             | C1              | Á                           |
| 130                        | 10000010             | 82              | ‚            | 194                        | 11000010             | C2              | Â                           |
| 131                        | 10000011             | 83              | ƒ            | 195                        | 11000011             | C3              | Ã                           |
| 132                        | 10000100             | 84              | „            | 196                        | 11000100             | C4              | Ä                           |
| 133                        | 10000101             | 85              | …            | 197                        | 11000101             | C5              | Å                           |
| 134                        | 10000110             | 86              | †            | 198                        | 11000110             | C6              | Æ                           |
| 135                        | 10000111             | 87              | ‡            | 199                        | 11000111             | C7              | Ç                           |
| 136                        | 10001000             | 88              | ˆ            | 200                        | 11001000             | C8              | È                           |
| 137                        | 10001001             | 89              | ‰            | 201                        | 11001001             | C9              | É                           |
| 138                        | 10001010             | 8A              | Š            | 202                        | 11001010             | CA              | Ê                           |
| 139                        | 10001011             | 8B              | ‹            | 203                        | 11001011             | CB              | Ë                           |
| 140                        | 10001100             | 8C              | Œ            | 204                        | 11001100             | CC              | Ì                           |
| 141                        | 10001101             | 8D              |              | 205                        | 11001101             | CD              | Í                           |
| 142                        | 10001110             | 8E              | Ž            | 206                        | 11001110             | CE              | Î                           |
| 143                        | 10001111             | 8F              |              | 207                        | 11001111             | CF              | Ï                           |
| 144                        | 10010000             | 90              |              | 208                        | 11100000             | D0              | Ð                           |
| 145                        | 10010001             | 91              | ‘            | 209                        | 11100001             | D1              | Ñ                           |
| 146                        | 10010010             | 92              | ’            | 210                        | 11100010             | D2              | Ò                           |
| 147                        | 10010011             | 93              | “            | 211                        | 11100011             | D3              | Ó                           |
| 148                        | 10010100             | 94              | ”            | 212                        | 11100100             | D4              | Ô                           |
| 149                        | 10010101             | 95              | •            | 213                        | 11100101             | D5              | Õ                           |
| 150                        | 10010110             | 96              | –            | 214                        | 11100110             | D6              | Ö                           |
| 151                        | 10010111             | 97              | —            | 215                        | 11100111             | D7              | ×                           |
| 152                        | 10011000             | 98              | ˜            | 216                        | 11101000             | D8              | Ø                           |
| 153                        | 10011001             | 99              | ™            | 217                        | 11101001             | D9              | Ù                           |
| 154                        | 10011010             | 9A              | š            | 218                        | 11101010             | DA              | Ú                           |
| 155                        | 10011011             | 9B              | ›            | 219                        | 11101011             | DB              | Û                           |
| 156                        | 10011100             | 9C              | œ            | 220                        | 11101100             | DC              | Ü                           |
| 157                        | 10011101             | 9D              |              | 221                        | 11101101             | DD              | Ý                           |
| 158                        | 10011110             | 9E              | ž            | 222                        | 11101110             | DE              | Þ                           |
| 159                        | 10011111             | 9F              | Ÿ            | 223                        | 11101111             | DF              | ß                           |
| 160                        | 10100000             | A0              |              | 224                        | 11110000             | E0              | à                           |
| 161                        | 10100001             | A1              | ¡            | 225                        | 11110001             | E1              | á                           |
| 162                        | 10100010             | A2              | ¢            | 226                        | 11110010             | E2              | â                           |
| 163                        | 10100011             | A3              | £            | 227                        | 11110011             | E3              | ã                           |
| 164                        | 10100100             | A4              | ¤            | 228                        | 11110100             | E4              | ä                           |
| 165                        | 10100101             | A5              | ¥            | 229                        | 11110101             | E5              | å                           |
| 166                        | 10100110             | A6              | Š            | 230                        | 11110110             | E6              | æ                           |
| 167                        | 10100111             | A7              | §            | 231                        | 11110111             | E7              | ç                           |
| 168                        | 10101000             | A8              | ¨            | 232                        | 11111000             | E8              | è                           |
| 169                        | 10101001             | A9              | ©            | 233                        | 11111001             | E9              | é                           |
| 170                        | 10101010             | AA              | ª            | 234                        | 11111010             | EA              | ê                           |
| 171                        | 10101011             | AB              | «            | 235                        | 11111011             | EB              | ë                           |
| 172                        | 10101100             | AC              | ¬            | 236                        | 11111100             | EC              | ì                           |
| 173                        | 10101101             | AD              |              | 237                        | 11111101             | ED              | í                           |
| 174                        | 10101110             | AE              | ®            | 238                        | 11111110             | EE              | î                           |
| 175                        | 10101111             | AF              | ¯            | 239                        | 11111111             | EF              | ï                           |
| 176                        | 10110000             | B0              | °            |                          |                      |                 |                             |
| 177                        | 10110001             | B1              | ±            |                          |                      |                 |                             |
| 178                        | 10110010             | B2              | ²            |                          |                      |                 |                             |
| 179                        | 10110011             | B3              | ³            |                          |                      |                 |                             |
| 180                        | 10110100             | B4              | ´            |                          |                      |                 |                             |
| 181                        | 10110101             | B5              | µ            |                          |                      |                 |                             |
| 182                        | 10110110             | B6              | ¶            |                          |                      |                 |                             |
| 183                        | 10110111             | B7              | ·            |                          |                      |                 |                             |
| 184                        | 10111000             | B8              | ¸            |                          |                      |                 |                             |
| 185                        | 10111001             | B9              | ¹            |                          |                      |                 |                             |
| 186                        | 101

Ventajas del ASCII extendido:

* Mayor Soporte de Caracteres Especiales: incluye caracteres adicionales como letras con acentos, diéresis, símbolos de moneda y otros caracteres gráficos, lo que facilita la escritura en varios idiomas europeos.
* Compatibilidad con Sistemas Antiguos: fue ampliamente utilizado en sistemas operativos antiguos como MS-DOS y primeras versiones de Windows, lo que lo hace útil para mantener la compatibilidad con software y hardware legados.
* Representación de Símbolos Gráficos: proporciona varios símbolos gráficos que permitieron crear interfaces de usuario y gráficos simples en los sistemas de texto antiguos.
* Soporte para Símbolos de Moneda: incluye símbolos de moneda como el euro (€), libra (£) y yen (¥), lo cual es útil para aplicaciones financieras básicas.
* Mayor Flexibilidad Lingüística: permite escribir en idiomas europeos, con acceso a caracteres que no están presentes en el ASCII estándar, como las letras acentuadas y otros símbolos necesarios para el alemán, español, francés, etc.

Desventajas del ASCII Extendido: 

* __Falta de Estandarización Universal__: no existe una única versión del ASCII extendido; diferentes versiones y variantes existen (como ISO 8859-1, ISO 8859-15), lo que puede causar inconsistencias y problemas de compatibilidad entre sistemas.
* __Limitaciones en la codificación de idiomas globales__: a pesar de su extensión, no cubre muchos idiomas no europeos, como el chino, japonés, árabe, o ruso, limitando su uso en un contexto verdaderamente internacional.
* __Obsoleto en sistemas modernos__: con la introducción de Unicode, que soporta miles de caracteres de todos los idiomas, el ASCII extendido ha quedado obsoleto y rara vez se utiliza en aplicaciones modernas.
* __Problemas de codificación y pérdida de datos__: los problemas de compatibilidad entre diferentes versiones de ASCII extendido pueden llevar a la pérdida de datos o caracteres incorrectamente interpretados, especialmente en la migración de datos antiguos a sistemas modernos.
* __Limitado a 8 Bits__: a pesar de su extensión, sigue estando limitado a 8 bits, lo que restringe el número total de caracteres a 256, insuficiente para cubrir todas las necesidades de representación de texto y símbolos en la actualidad.
* __Incompatibilidad con estándares modernos__: no es compatible con Unicode, lo que dificulta la integración con sistemas y aplicaciones actuales que dependen de este estándar más amplio y flexible.

El ASCII extendido fue una evolución necesaria del ASCII original, añadiendo soporte para más caracteres y símbolos. Sin embargo, su falta de estandarización y capacidad limitada han llevado a su reemplazo por estándares más robustos como Unicode. Aunque sigue siendo útil para trabajar con sistemas antiguos y específicos, en el contexto moderno, sus desventajas superan las ventajas, especialmente cuando se trata de aplicaciones globales y multilingües.

### Unicode

_Unicode_ es un estándar de codificación de caracteres que se diseñó para proporcionar un conjunto único y universal para representar texto en la mayoría de los sistemas de escritura del mundo. Su objetivo es superar las limitaciones de los estándares anteriores, como ASCII y sus variantes extendidas, permitiendo una codificación coherente y consistente de textos multilingües en aplicaciones y sistemas informáticos.

Características de Unicode:
* __Universalidad__: soporta la mayoría de los caracteres de todos los lenguajes, incluidos los símbolos, emoticonos y caracteres especiales.
* __Escalabilidad__: puede representar más de un millón de caracteres diferentes gracias a su estructura flexible.
* __Compatibilidad__: compatible con ASCII y muchas otras codificaciones, facilitando la interoperabilidad entre sistemas antiguos y modernos.
* __Codificaciones de Unicode__: UTF-8, UTF-16 y UTF-32

Unicode puede ser codificado de diferentes maneras, siendo las más comunes UTF-8, UTF-16 y UTF-32. Cada una tiene sus propias características, ventajas y desventajas.

__UTF-8 (8-bit Unicode Transformation Format)__

_UTF-8_ es una codificación de longitud variable que utiliza entre 1 y 4 bytes para representar un carácter. Los primeros 128 caracteres (0-127) coinciden con los caracteres del código ASCII, lo que garantiza la compatibilidad con ASCII y con los primeros 128 primeros caracteres de cualquier codificación ASCII Extendido. Es muy eficiente en términos de almacenamiento para textos predominantemente en inglés y otros idiomas que utilizan caracteres latinos:
* __Carácter de 1 byte__: los caracteres ASCII básicos, como letras y números, utilizan solo 1 byte en UTF-8, por ejemplo, el carácter A, código UTF-8 41 (Hexadecimal).
* __Carácter de 2 bytes__: caracteres acentuados y símbolos de lenguas europeas que no están en el conjunto ASCII, como la ñ, utilizan 2 bytes, por ejemplo, el carácter ñ, código UTF-8 C3 B1 (Hexadecimal)
* __Carácter de 3 bytes__: los caracteres de lenguas asiáticas como el chino, japonés o coreano generalmente requieren 3 bytes. Por ejemplo, 日 (Kanji para "sol" en japonés), código UTF-8 E6 97 A5 (Hexadecimal)
* __Carácter de 4 bytes__: los caracteres especiales como emojis y algunos símbolos raros requieren 4 bytes.  Por ejemplo, 😀 (Emoji de cara sonriente).

Ventajas:
* __Ahorra espacio__: utiliza solo un byte para los caracteres más comunes.
* __Uso extendido__: es la codificación preferida para la web, ya que HTML y muchos otros protocolos están optimizados para UTF-8.

Desventajas:
* Para caracteres de scripts más complejos (como chino o japonés), requiere más bytes (hasta 4), lo que puede hacer que los archivos sean más grandes.
* No siempre es la opción más rápida para operaciones que requieren acceso aleatorio a los caracteres debido a su longitud variable.

__UTF-16 (16-bit Unicode Transformation Format)__

_UTF-16_ utiliza uno o dos bloques de 16 bits (2 o 4 bytes) para representar un carácter. Utiliza 2 o 4 bytes para representar los caracteres: los caracteres más comunes se representan con un solo bloque de 16 bits, mientras que los caracteres menos comunes se representan con dos bloques de 16 bits.

Ventajas:
* Es eficiente para representar la mayoría de los idiomas asiáticos, ya que muchos de estos caracteres encajan en un solo bloque de 16 bits.
* Buena opción para aplicaciones que necesitan un equilibrio entre espacio y facilidad de acceso aleatorio.

Desventajas:
* No es compatible con ASCII, lo que puede causar problemas de compatibilidad si no se maneja correctamente.
* Mayor uso de espacio para textos que usan predominantemente caracteres latinos o ASCII.

__UTF-32 (32-bit Unicode Transformation Format)__

__UTF-32__ utiliza un bloque fijo de 4 bytes (32 bits) para cada carácter, lo que significa que todos los caracteres se representan con exactamente 4 bytes. Debido a su longitud fija, cada carácter tiene una dirección y tamaño predecible, lo que facilita el acceso y la manipulación de texto.

Ventajas:
* Ideal para sistemas donde la simplicidad y el acceso aleatorio rápido a los caracteres son más importantes que la eficiencia en el uso del espacio.
* No hay ambigüedad en la codificación, ya que cada carácter ocupa siempre 4 bytes.

Desventajas:
* Uso de memoria extremadamente alto: ocupa mucho más espacio que UTF-8 y UTF-16, lo que lo hace ineficiente para la mayoría de las aplicaciones.
* Poco utilizado en la web debido a su ineficiencia de almacenamiento.

Comparativa Resumida de UTF-8, UTF-16 y UTF-32:

| **Codificación** | **Bytes por carácter** | **Ventajas**                                        | **Desventajas**                                      |
|------------------|------------------------|-----------------------------------------------------|------------------------------------------------------|
| **UTF-8**        | 1-4                    | Compatibilidad con ASCII, eficiente para caracteres latinos | Ineficiente para algunos idiomas asiáticos           |
| **UTF-16**       | 2 o 4                  | Buena para muchos idiomas, equilibrio en espacio y acceso | No compatible con ASCII, mayor uso de espacio para caracteres latinos |
| **UTF-32**       | 4                      | Simplicidad y acceso directo                        | Muy ineficiente en espacio, uso limitado             |

Conclusión:
* __UTF-8__: es la codificación más utilizada y recomendada para la web y aplicaciones generales debido a su eficiencia y compatibilidad.
* __UTF-16__: se utiliza principalmente en entornos que requieren un compromiso entre espacio y rendimiento, como algunas aplicaciones de Windows y Java.
* __UTF-32__ es ideal para sistemas que necesitan una codificación fija por carácter, aunque su alto consumo de memoria limita su uso.

Estas codificaciones permiten a Unicode representar y gestionar texto de cualquier idioma de manera coherente y flexible, facilitando la comunicación y la interoperabilidad en la era digital.
