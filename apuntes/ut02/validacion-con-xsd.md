# Validación de Documentos XML con XSD

* Introducción
* Definición de Esquema XML
* Tipos de XSD
    * XSD interno
    * XSD externo
* Elemento XSD
* Atributo XSD
* Tipo simple XSD
* Tipo complejo XSD
* Grupo de elementos XSD
* Restricciones de los elementos
    * Restricción en xs:string
    * Restricción en xs:date
    * Restricción en xs:integer
    * Otras restricciones
* Grupo de atributos XSD
* Tipos de datos integrados
    * Tipos numéricos
    * Tipos de fecha y hora
    * Tipos booleanos
    * Tipos de texto y cadenas de caracteres
    * Tipos binarios
    * Tipos derivados de xs:string
    * Listas y uniones
* Namespaces
* Diferencia entre DTD y XSD: ejemplo comparativo

## Introducción

__XSD__ (XML Schema Definition) es un lenguaje utilizado para definir la estructura y restricciones de los documentos XML. Un esquema XSD especifica las reglas que deben cumplir los datos en XML, permitiendo validarlos y asegurar que cumplen con un formato específico.

Ventajas de XSD sobre DTD:
* __Soporte de tipos de datos__: XSD incluye tipos de datos integrados (string, int, date, boolean, etc.) y permite crear tipos personalizados, lo que facilita la validación de datos.
* __Sintaxis basada en XML__: XSD está escrito en XML, lo que hace que sea fácil de leer, entender e integrar con otras tecnologías XML.
* __Soporte de espacios de nombres (Namespaces)__: permite evitar conflictos en documentos XML complejos que combinan diferentes vocabularios.
* __Estructuras complejas y reutilizables__: XSD permite definir estructuras jerárquicas complejas, derivar nuevos tipos mediante herencia (extensión y restricción) y reutilizar componentes.

## Definición de Esquema XML

Un esquema XML es un documento XSD que define reglas y restricciones para un documento XML. Se utiliza para:
* Especificar elementos y atributos permitidos y sus tipos de datos.
* Establecer la estructura y jerarquía de los elementos.
* Definir restricciones adicionales, como valores permitidos, obligatorios, rangos de valores, etc.

Ejemplo de definición de esquema XSD:

```bash
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="persona">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="nombre" type="xs:string"/>
        <xs:element name="edad" type="xs:int"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

XML válido para el esquema XSD anterior:

```bash
<persona>
  <nombre>Juan Pérez</nombre>
  <edad>30</edad>
</persona>
```

## Tipos de XSD

En XSD, los esquemas pueden definirse tanto internamente (dentro del documento XML) como externamente (en un archivo independiente), al igual que en DTD. Los esquemas XSD internos suelen usarse en documentos XML simples, mientras que los esquemas externos son más comunes cuando el esquema debe reutilizarse o compartirse entre múltiples documentos XML.

### XSD interno

Un XSD interno se define dentro del propio documento XML, usando el elemento <xs:schema>, y se especifica dentro de la sección <xml> sin necesidad de un archivo separado. Esto es útil para documentos XML independientes y de estructura sencilla.

Ejemplo de XSD Interno:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<libro xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:noNamespaceSchemaLocation="libro.xsd">
  <titulo>XML Avanzado</titulo>
  <autor>Pedro Gómez</autor>
  <precio>30.00</precio>
</libro>

<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="libro">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="titulo" type="xs:string"/>
        <xs:element name="autor" type="xs:string"/>
        <xs:element name="precio" type="xs:decimal"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

Explicación del ejemplo:
* En este ejemplo, el esquema está contenido dentro del documento XML.
* Se utiliza el prefijo `xs:` para elementos de XSD.
* El esquema define el elemento raíz libro, que contiene los subelementos titulo, autor y precio, con sus respectivos tipos de datos.

### XSD externo

Un XSD externo se define en un archivo separado (por ejemplo, libro.xsd) y se referencia en el documento XML mediante el atributo xsi:schemaLocation o xsi:noNamespaceSchemaLocation en la raíz del XML.

Ejemplo de referencia a un XSD externo:

Archivo XML:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<libro xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:noNamespaceSchemaLocation="libro.xsd">
  <titulo>XML Avanzado</titulo>
  <autor>Pedro Gómez</autor>
  <precio>30.00</precio>
</libro>
```

Archivo _libro.xsd_:

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="libro">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="titulo" type="xs:string"/>
        <xs:element name="autor" type="xs:string"/>
        <xs:element name="precio" type="xs:decimal"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

Explicación del ejemplo:
* En el documento XML, el esquema externo se referencia mediante xsi:noNamespaceSchemaLocation="libro.xsd".
* El archivo XSD (libro.xsd) define el elemento libro y su estructura.
* El elemento libro contiene los elementos titulo, autor y precio con sus tipos de datos especificados (xs:string y xs:decimal).

## Elemento XSD

Un elemento XSD es una estructura que puede tener datos en un documento XML. Los elementos pueden ser:
* Simples: solamente contienen datos de texto.
* Complejos: contienen otros elementos o atributos.

Tipos de elementos:
* __Globales__: se declaran en el nivel superior del esquema y pueden referenciarse en otros lugares.
* __Locales__: están definidos dentro de otros elementos o tipos y no pueden reutilizarse.

Ejemplo de elementos globales y locales:

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="libro" type="LibroType"/>

  <xs:complexType name="LibroType">
    <xs:sequence>
      <xs:element name="titulo" type="xs:string"/>
      <xs:element name="autor" type="xs:string"/>
      <xs:element name="isbn" type="xs:string"/>
    </xs:sequence>
  </xs:complexType>
</xs:schema>
```

XML válido para el esquema XSD anterior:

```xml
<libro>
  <titulo>El Quijote</titulo>
  <autor>Miguel de Cervantes</autor>
  <isbn>978-3-16-148410-0</isbn>
</libro>
```

El elemento global en este XSD es el elemento `libro`. Está definido en el nivel superior del esquema (directamente dentro del elemento raíz `<xs:schema>`) con la siguiente declaración:

```xml
<xs:element name="libro" type="LibroType"/>
```

Características de los elementos globales:
* Pueden ser referenciados o reutilizados en otros tipos, elementos, o grupos dentro del esquema.
* Están disponibles en todo el esquema XSD y, si se define un targetNamespace, también están disponibles en otros esquemas que importen este namespace.
* En este caso, libro es el elemento raíz y puede aparecer como tal en el documento XML.

Los elementos locales en este XSD son los elementos `titulo`, `autor` e `isbn`. Estos están definidos dentro del tipo complejo `LibroType`, y solo son accesibles dentro del contexto de `LibroType`, que a su vez está asociado con libro.

```xml
<xs:complexType name="LibroType">
  <xs:sequence>
    <xs:element name="titulo" type="xs:string"/>
    <xs:element name="autor" type="xs:string"/>
    <xs:element name="isbn" type="xs:string"/>
  </xs:sequence>
</xs:complexType>
```

Características de los elementos locales:
* No se pueden reutilizar fuera del contexto en el que están definidos, es decir, en este caso, solo existen dentro del tipo complejo LibroType.
* No son visibles globalmente en el esquema.
* Esto es útil para agrupar atributos o elementos que solo tienen sentido en el contexto específico de un elemento (como titulo, autor e isbn en el contexto de un libro).

## Atributo XSD

Un atributo XSD define datos adicionales asociados a un elemento. Los atributos se usan comúnmente para valores pequeños o propiedades descriptivas.

Tipos de Atributos:
* __Globales__: definidos en el nivel superior del esquema, pueden ser referenciados en varios elementos.
* __Locales__: definidos dentro de un elemento o tipo complejo específico.

Ejemplo de Atributos globales y locales:

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <!-- Atributo global -->
  <xs:attribute name="pais" type="xs:string"/>

  <!-- Elemento con un atributo local -->
  <xs:element name="persona">
    <xs:complexType>
      <xs:attribute name="id" type="xs:int" use="required"/>
      <xs:attribute ref="pais"/>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

XML válido para el esquema XSD anterior:

```xml
<persona id="1" pais="España">
  <nombre>Carlos Díaz</nombre>
</persona>
```

## Tipo Simple XSD

Un tipo simple define datos sin estructura interna, es decir, solo texto. Sirve para restringir el valor de un atributo o elemento simple.

Ejemplo de tipo simple con restricciones:

```xml
<xs:simpleType name="EdadType">
  <xs:restriction base="xs:int">
    <xs:minInclusive value="0"/>
    <xs:maxInclusive value="120"/>
  </xs:restriction>
</xs:simpleType>

<xs:element name="persona">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="nombre" type="xs:string"/>
      <xs:element name="edad" type="EdadType"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

XML válido para el esquema XSD anterior:

```xml
<persona>
  <nombre>Ana García</nombre>
  <edad>28</edad>
</persona>
```

En este ejemplo, el tipo simple EdadType está diseñado para restringir los valores que puede tener el elemento edad dentro del elemento persona. Este tipo de restricción es muy útil para asegurar que los valores ingresados en el documento XML cumplan con ciertos requisitos, en este caso, un rango específico para la edad.

## Tipo Complejo XSD

Un tipo complejo es un tipo de datos que permite definir una estructura de datos más detallada y jerárquica dentro de un documento XML. A diferencia de los tipos simples, que solo contienen datos de texto sin estructura interna, los tipos complejos pueden incluir:
* __Subelementos__: elementos secundarios o hijos dentro del elemento complejo.
* __Atributos__:  valores adicionales asociados al elemento que proporcionan información extra o propiedades.
* __Restricciones__: limitaciones sobre los valores y la estructura del tipo complejo, como la cantidad mínima o máxima de ocurrencias de los subelementos.

Ejemplo de tipo complejo:

```xml
<xs:complexType name="LibroType">
  <xs:sequence>
    <xs:element name="titulo" type="xs:string"/>
    <xs:element name="autor" type="xs:string"/>
  </xs:sequence>
  <xs:attribute name="publicado" type="xs:date"/>
</xs:complexType>

<xs:element name="libro" type="LibroType"/>
```

XML válido para el esquema XSD anterior:

```xml
<libro publicado="1605-01-16">
  <titulo>Don Quijote de la Mancha</titulo>
  <autor>Miguel de Cervantes</autor>
</libro>
```

En este fragmento de XSD define un tipo complejo llamado LibroType, que modela la estructura de un libro en un documento XML. Dentro del tipo LibroType, hay dos elementos obligatorios en secuencia (titulo y autor), ambos de tipo xs:string, para capturar el nombre del libro y el autor, respectivamente. Además, el tipo incluye un atributo publicado de tipo xs:date, que permite especificar la fecha de publicación del libro en el formato AAAA-MM-DD. El elemento libro, definido como instancia de LibroType, utiliza esta estructura en el XML, lo que permite que los documentos XML validados con este esquema contengan información completa sobre un libro, incluyendo su título, autor y fecha de publicación.

## Grupo de Elementos XSD

Un grupo de elementos encapsula un conjunto de elementos que pueden reutilizarse en varios tipos complejos.

Ejemplo de grupo de elementos:

```xml
<xs:group name="InformacionContacto">
  <xs:sequence>
    <xs:element name="telefono" type="xs:string"/>
    <xs:element name="email" type="xs:string"/>
  </xs:sequence>
</xs:group>

<xs:complexType name="PersonaType">
  <xs:sequence>
    <xs:element name="nombre" type="xs:string"/>
    <xs:group ref="InformacionContacto"/>
  </xs:sequence>
</xs:complexType>

<xs:element name="persona" type="PersonaType"/>
```

XML válido para el esquema XSD anterior:

```xml
<persona>
  <nombre>Luisa Gómez</nombre>
  <telefono>555-1234</telefono>
  <email>luisa.gomez@example.com</email>
</persona>
```

Este ejemplo de XSD utiliza un grupo de elementos llamado InformacionContacto para definir un conjunto reutilizable de datos de contacto, en este caso, telefono y email, ambos de tipo xs:string. Este grupo es referenciado dentro del tipo complejo PersonaType, que también incluye el elemento nombre. Al definir el grupo de elementos, se facilita la reutilización de la misma estructura de contacto en otros tipos complejos, mejorando la claridad y modularidad del esquema. Finalmente, el elemento persona se basa en el tipo PersonaType, permitiendo que un documento XML estructurado según este esquema contenga un nombre y la información de contacto correspondiente.

## Restricciones en los elementos

En XSD el elemento `xs:restriction` se usa para restringir los valores permitidos de un tipo de dato:

### Restricción en xs:string

Limitar la longitud de un string a 9 caracteres:

```xml
<xs:element name="exampleString">
  <xs:simpleType>
    <xs:restriction base="xs:string">
      <xs:maxLength value="9"/>
    </xs:restriction>
  </xs:simpleType>
</xs:element>
```

### Restricción en xs:date

Limitar una fecha dentro de un rango:

```xml
<xs:element name="startDate">
  <xs:simpleType>
    <xs:restriction base="xs:date">
      <xs:minInclusive value="2023-01-01"/>
      <xs:maxInclusive value="2024-01-01"/>
    </xs:restriction>
  </xs:simpleType>
</xs:element>
```

### Restricción en xs:integer

Limitar un entero a valores entre 1 y 100:

```xml
<xs:element name="quantity">
  <xs:simpleType>
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
</xs:element>
```

Cada ejemplo utiliza xs:restriction para imponer límites en tipos específicos de datos, asegurando que los valores cumplan ciertos criterios antes de ser aceptados.

### Otras restricciones

El elemento teléfono será un entero y dicho elemento podrá aparecer entre 0 y 5 veces:

```xml
<xs:element name="telefono" minOccurs="0" maxOccurs="5">
  <xs:simpleType>
    <xs:restriction base="xs:integer"/>
  </xs:simpleType>
</xs:element>
```

El atributo dni será una plantilla de 8 números y una letra mayúscula:

```xml
<xs:attribute name="dni" type="xs:string" use="required">
  <xs:simpleType>
    <xs:restriction base="xs:string">
      <xs:pattern value="\d{8}[A-Z]"/>
    </xs:restriction>
  </xs:simpleType>
</xs:attribute>
```

`\d{8}[A-Z]`:
* `\d{8}`: un conjunto de 8 números
* `[A-Z]`: una letra entre la A y la Z mayúscula


## Grupo de Atributos XSD

Un grupo de atributos encapsula un conjunto de atributos reutilizables que pueden ser usados en varios elementos y tipos complejos.

Ejemplo de grupo de atributos:

```xml
<xs:attributeGroup name="Ubicacion">
  <xs:attribute name="ciudad" type="xs:string"/>
  <xs:attribute name="pais" type="xs:string"/>
</xs:attributeGroup>

<xs:complexType name="EmpresaType">
  <xs:attributeGroup ref="Ubicacion"/>
  <xs:attribute name="nombre" type="xs:string"/>
</xs:complexType>

<xs:element name="empresa" type="EmpresaType"/>
```

XML válido para el esquema XSD anterior:

```xml
<empresa nombre="Tech Solutions" ciudad="Madrid" pais="España"/>
```

Este ejemplo de XSD define un grupo de atributos llamado Ubicacion, que encapsula los atributos ciudad y pais, ambos de tipo xs:string. Este grupo se reutiliza dentro del tipo complejo EmpresaType, que también incluye un atributo adicional nombre, representando el nombre de la empresa. Al referenciar el grupo de atributos Ubicacion, EmpresaType puede incluir de forma modular la información de ubicación, permitiendo que el elemento empresa en el XML resultante contenga atributos detallados de nombre, ciudad y país. Esta estructura facilita la reutilización de atributos en otros tipos que también necesiten información de ubicación.

## Tipos de datos integrados

En XSD existen varios tipos de datos integrados además de `xs:string`. Estos tipos permiten definir y validar los valores que pueden tener los elementos y atributos de un documento XML. A continuación, se muestran algunos de los tipos más comunes, organizados en categorías:

### Tipos numéricos

* `xs:int`: número entero (equivalente a un integer de 32 bits).
* `xs:integer`: entero sin límite de tamaño específico.
* `xs:short`: entero corto (equivalente a un integer de 16 bits).
* `xs:long`: entero largo (equivalente a un integer de 64 bits).
* `xs:decimal`: número decimal con punto flotante, ideal para representar números fraccionarios.
* `xs:float`: número en coma flotante simple (32 bits).
* `xs:double`: número en coma flotante doble (64 bits).
* `xs:nonNegativeInteger`: entero que no puede ser negativo.
* `xs:positiveInteger`: entero que debe ser mayor a 0.
* `xs:nonPositiveInteger`: entero que no puede ser positivo (puede ser negativo o 0).
* `xs:negativeInteger`: entero que debe ser menor a 0.
* `xs:unsignedInt`, `xs:unsignedShort`, `xs:unsignedLong`: enteros sin signo (positivos).

Ejemplo de `xs:int`:

```xml
<xs:element name="edad" type="xs:int"/>
```

### Tipos de fecha y hora

* `xs:date`: fecha en el formato AAAA-MM-DD (por ejemplo, 2024-10-25).
* `xs:time`: hora en el formato HH:MM:SS (por ejemplo, 14:30:00).
* `xs:dateTime`: fecha y hora combinadas en el formato AAAA-MM-DDTHH:MM:SS (por ejemplo, 2024-10-25T14:30:00).
* `xs:duration`: duración de tiempo en el formato PnYnMnDTnHnMnS (por ejemplo, P1Y2M3DT10H30M para 1 año, 2 meses, 3 días, 10 horas y 30 minutos).
* `xs:gYear`, `xs:gMonth`, `xs:gDay`: año (YYYY), mes (--MM--) o día (---DD), usados para fechas parciales.
* `xs:gYearMonth, xs:gMonthDay: combinaciones de año y mes, o mes y día.

Ejemplo de `xs:date`:

```xml
<xs:element name="fechaNacimiento" type="xs:date"/>
```

### Tipos booleanos

* `xs:boolean`: valores booleanos true/false o 1/0.

Ejemplo de xs:boolean:

```xml
<xs:element name="activo" type="xs:boolean"/>
```

### Tipos de texto y cadenas de caracteres

* `xs:string`: cadena de texto (caracteres alfanuméricos y especiales).
* `xs:normalizedString`: cadena de texto donde se eliminan saltos de línea y tabulaciones.
* `xs:token`: similar a normalizedString, pero además elimina espacios adicionales al principio y al final.
* `xs:language`: representa un código de idioma en el formato ISO (es, en, fr, etc.).
* `xs:Name`, `xs:NCName`, `xs:QName`: representan nombres válidos en XML, como nombres de elementos o atributos.
* `xs:ID`: identificador único dentro del documento XML.
* `xs:IDREF` y `xs:IDREFS`: referencias a identificadores ID de otros elementos.
* `xs:NMTOKEN` y `xs:NMTOKENS`: cadenas que solo pueden contener caracteres válidos en nombres XML.

Ejemplo de `xs:token`:

```xml
<xs:element name="nombre" type="xs:token"/>
```

### Tipos binarios

* `xs:base64Binary`: datos en formato base64, útil para incluir contenido binario como imágenes o archivos codificados en XML.
* `xs:hexBinary`: datos en formato hexadecimal.

Ejemplo de `xs:base64Binary`:

```xml
<xs:element name="imagen" type="xs:base64Binary"/>
```

### Tipos derivados de xs:string

* `xs:anyURI`: representa una URI o URL (por ejemplo, https://example.com).
* `xs:language`: código de idioma ISO (por ejemplo, en para inglés).
* `xs:ID`: identificador único dentro del documento XML.
* `xs:IDREF` y `xs:IDREFS`: referencias a identificadores ID de otros elementos.
* `xs:NMTOKEN` y `xs:NMTOKENS`: cadenas de texto que solo contienen caracteres válidos en nombres XML.

Ejemplo de xs:anyURI:

```xml
<xs:element name="paginaWeb" type="xs:anyURI"/>
```

### Listas y uniones

* `xs:list`: permite definir una lista de valores separados por espacios.
* `xs:union`: permite combinar diferentes tipos en uno solo.

Ejemplo de xs:list:

```xml
<xs:simpleType name="ListaColores">
  <xs:list itemType="xs:string"/>
</xs:simpleType>
```

Este tipo ListaColores acepta valores como "rojo verde azul".

Ejemplo completo de diferentes tipos de datos en XSD:

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="persona">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="nombre" type="xs:string"/>
        <xs:element name="edad" type="xs:int"/>
        <xs:element name="activo" type="xs:boolean"/>
        <xs:element name="fechaNacimiento" type="xs:date"/>
        <xs:element name="paginaWeb" type="xs:anyURI"/>
        <xs:element name="coloresFavoritos" type="ListaColores"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>

  <xs:simpleType name="ListaColores">
    <xs:list itemType="xs:string"/>
  </xs:simpleType>
</xs:schema>
```

XML válido para el esquema XSD anterior:

```xml
<persona>
  <nombre>Ana García</nombre>
  <edad>30</edad>
  <activo>true</activo>
  <fechaNacimiento>1993-05-12</fechaNacimiento>
  <paginaWeb>https://anagarcia.com</paginaWeb>
  <coloresFavoritos>rojo azul verde</coloresFavoritos>
</persona>
```

## Namespaces

Un __namespace__ o espacio de nombres es un mecanismo que permite agrupar y distinguir elementos y atributos para evitar conflictos de nombres en un documento XML. Los namespaces son especialmente útiles cuando diferentes esquemas se combinan en un mismo documento XML, ya que permiten tener elementos con el mismo nombre provenientes de distintos esquemas sin generar confusión.

Un namespace se declara en el esquema utilizando el atributo targetNamespace dentro del elemento raíz <xs:schema>, y se asocia un prefijo mediante xmlns (XML Namespace). Este prefijo se usará en el documento XML para diferenciar los elementos y atributos de ese namespace.

Ejemplo de XSD con un Namespace:

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"
           targetNamespace="http://www.example.com/persona"
           xmlns="http://www.example.com/persona"
           elementFormDefault="qualified">
  
  <xs:element name="persona">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="nombre" type="xs:string"/>
        <xs:element name="edad" type="xs:int"/>
      </xs:sequence>
      <xs:attribute name="id" type="xs:int"/>
    </xs:complexType>
  </xs:element>

</xs:schema>
```

XML válido para el esquema con namespace anterior:

```xml
<persona xmlns="http://www.example.com/persona" id="1">
  <nombre>Juan Pérez</nombre>
  <edad>30</edad>
</persona>
```

En este ejemplo:
* El esquema XSD define un namespace http://www.example.com/persona.
* El documento XML usa el mismo namespace (xmlns="http://www.example.com/persona"), lo cual asegura que los elementos persona, nombre, y edad están asociados al namespace definido en el esquema.


Ejemplo de XSD con dos namespaces: en este ejemplo, vamos a definir dos esquemas, uno para persona y otro para empresa, cada uno en su propio namespace.

XSD para persona:

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"
           targetNamespace="http://www.example.com/persona"
           xmlns="http://www.example.com/persona"
           elementFormDefault="qualified">
  
  <xs:element name="persona">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="nombre" type="xs:string"/>
        <xs:element name="edad" type="xs:int"/>
      </xs:sequence>
      <xs:attribute name="id" type="xs:int"/>
    </xs:complexType>
  </xs:element>

</xs:schema>
```

XSD para empresa:

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"
           targetNamespace="http://www.example.com/empresa"
           xmlns="http://www.example.com/empresa"
           elementFormDefault="qualified">
  
  <xs:element name="empresa">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="nombre" type="xs:string"/>
        <xs:element name="ubicacion" type="xs:string"/>
      </xs:sequence>
      <xs:attribute name="id" type="xs:int"/>
    </xs:complexType>
  </xs:element>

</xs:schema>
```

XML válido para ambos namespaces:

```xml
<documento xmlns:per="http://www.example.com/persona"
           xmlns:emp="http://www.example.com/empresa">
  
  <per:persona id="1">
    <per:nombre>Ana López</per:nombre>
    <per:edad>28</per:edad>
  </per:persona>
  
  <emp:empresa id="101">
    <emp:nombre>Tech Solutions</emp:nombre>
    <emp:ubicacion>Madrid</emp:ubicacion>
  </emp:empresa>

</documento>
```

En este ejemplo:
* Se definen dos namespaces:
    * http://www.example.com/persona (prefijo per), que contiene el elemento persona.
    * http://www.example.com/empresa (prefijo emp), que contiene el elemento empresa.

En el documento XML, se utiliza el prefijo per para elementos de persona y emp para elementos de empresa, manteniéndolos claramente diferenciados y permitiendo que ambos namespaces coexistan sin conflicto en un solo documento.

> __Nota__; en un namespace de XSD se puede utilizar cualquier identificador único que cumpla con las reglas de URI (Identificador Uniforme de Recursos), y no es necesario que sea una URL accesible en la web. Esto significa que puedes usar una dirección local o cualquier cadena que actúe como un identificador único, incluso si no apunta a un recurso específico. en lugar de http://www.example.com/persona, podemos definir el namespace utilizando una dirección local o una cadena personalizada, como file:///C:/schemas/persona.

## Diferencia entre DTD y XSD: ejemplo comparativo

Ejemplo de esquema DTD:

```xml
<!ELEMENT libro (titulo, autor)>
<!ELEMENT titulo (#PCDATA)>
<!ELEMENT autor (#PCDATA)>
<!ATTLIST libro isbn CDATA #REQUIRED>
```

Ejemplo de esquema XSD:

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="libro">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="titulo" type="xs:string"/>
        <xs:element name="autor" type="xs:string"/>
      </xs:sequence>
      <xs:attribute name="isbn" type="xs:string" use="required"/>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

XML válido para los esquemas DTD y XSD anteriores:

```xml
<libro isbn="978-3-16-148410-0">
  <titulo>El Quijote</titulo>
  <autor>Miguel de Cervantes</autor>
</libro>
```

En DTD, los tipos de datos son básicos (#PCDATA y CDATA), mientras que en XSD se especifican tipos detallados (xs:string).
XSD permite tipos de datos avanzados, atributos con restricciones y validación compleja, mientras que DTD es más limitado y menos flexible.
