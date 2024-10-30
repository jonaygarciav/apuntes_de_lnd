# Validación con XSD (Ejercicios)

# Ejercicio 1

Crear un fichero xml llamado `personas.xml` con los siguientes datos:

| Nombre      | Apellidos         | DNI         | Fecha de Nacimiento | Teléfono   |
|-------------|-------------------|-------------|----------------------|------------|
| Juan        | García Pérez      | 12345678A   | 1985-06-15          | 123456789  |
| María       | López Hernández   | 87654321B   | 1990-03-22          | 987654321  |
| Pedro       | Martínez Sánchez  | 23456789C   | 2000-12-10          | 567890123  |
| Lucía       | Fernández Ruiz    | 34567890D   | 1975-08-25          | 876543210  |
| Ana         | Gómez Torres      | 45678901E   | 1999-05-30          | 234567890  |


Generar un fichero XSD llamado `personas.xsd` que cumpla los siguientes requisitos:

* Máximo de 5 personas en el listado. Al menos debe de haber una.
* Cada persona debe contener los siguientes datos:
    * Nombre: tiene que tener como máximo 30 caracteres.
    * Apellidos: tiene que tener como máximo 50 caracteres.
    * DNI: exactamente 9 caracteres (8 números y una letra mayúscula al final).
    * Fecha de Nacimiento: formato YYYY-MM-DD, con un rango entre 1900-01-01 y 2010-01-01.
    * Teléfono: cadena de texto de exactamente 9 caracteres.

## Ejercicio 2

Crear un fichero xml llamado `estudiantes.xml` con los siguientes datos:

| Nombre      | Apellidos         | Matrícula | Fecha de Inscripción | Correo                   | Teléfono 1 | Teléfono 2 | Teléfono 3 | Vía     | Nombre de Vía      | Código Postal |
|-------------|-------------------|-----------|-----------------------|--------------------------|------------|------------|------------|---------|---------------------|---------------|
| Juan        | Pérez López       | 1234567   | 2020-09-01           | juan.perez@email.com     | 1234567890 | 9876543210 |            | calle   | Gran Vía           | 28001         |
| María       | García Morales    | 2345678   | 2021-06-15           | maria.garcia@email.com   | 1234509876 | 5432167890 | 6789012345 | avenida | Las Palmas         | 28015         |
| Pedro       | Fernández Ruiz    | 3456789   | 2019-11-20           | pedro.fernandez@email.com| 3456789012 |            |            | calle   | Los Olivos         | 28020         |
| Ana         | Sánchez Torres    | 4567890   | 2022-03-10           | ana.sanchez@email.com    | 4567890123 | 7890123456 |            | avenida | El Prado           | 28025         |
| Luis        | Martínez Gómez    | 5678901   | 2023-01-05           | luis.martinez@email.com  | 8901234567 | 2345678901 | 6789012345 | calle   | La Castellana      | 28030         |

Crea un esquema XSD llamado `estudiantes.xsd` para un listado de estudiantes, con un máximo de 10 estudiantes, donde cada estudiante debe incluir:

* Nombre: texto de hasta 30 caracteres.
* Apellidos: texto de hasta 50 caracteres.
* Matrícula: un número de 7 dígitos, obligatorio.
* Fecha de inscripción: fecha en formato YYYY-MM-DD, desde 2000-01-01 hasta 2023-12-31.
* Correo electrónico: en formato email@dominio.com, obligatorio.
* Teléfonos: de 1 a 3 números de teléfono de 10 dígitos cada uno.
* Dirección:
    * Vía: solo puede tener los valores "calle" o "avenida".
    * Nombre: texto de hasta 100 caracteres.
    * Código Postal: exactamente 5 dígitos.
