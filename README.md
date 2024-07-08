# Literalura 📚

Se trata de un Challenge sobre la gestión y consulta de libros, organizado por Alura Latam y en colaboración con Oracle en el programa ONE para la especialización en Back-End.

## Descripción

Este proyecto es un Gestor de Libros desarrollado en Java que te permite buscar libros por título, autores por nombre, listar libros y autores registrados, y obtener estadísticas generales sobre la base de datos de libros. La aplicación interactúa con una API externa para obtener información y utiliza una base de datos local para almacenar y gestionar los datos de libros y autores.

## Tecnologías Utilizadas

- **Lenguaje de Programación:** Java
- **API de Libros:** Se utilizó una API externa (gutendex.com) para obtener información sobre libros y autores.
- **Spring Framework:** Para la gestión de la inyección de dependencias y acceso a la base de datos.
- **Base de Datos:** Utilización de una base de datos (posiblemente H2, MySQL, etc.) para el almacenamiento de datos.
- **Control de Versiones:** Git/GitHub se usaron para el control de versiones del proyecto y la colaboración en equipo.
- **Entorno de Desarrollo Integrado (IDE):** IntelliJ IDEA fue el entorno de desarrollo utilizado para escribir, depurar y ejecutar el código Java.

## Funcionalidades

### Principal.java

El punto de entrada principal del programa. Aquí se maneja la interacción con el usuario a través de la consola, mostrando un menú de opciones y gestionando las consultas sobre libros y autores.

#### Funcionalidades principales:

- Buscar libro por título.
- Buscar autor por nombre.
- Listar libros registrados.
- Listar autores registrados.
- Listar autores vivos en un determinado año.
- Listar libros por idioma.
- Obtener estadísticas generales.
- Listar los 10 libros más descargados.
- Listar autores nacidos o fallecidos en algún año específico.

### ConsumoApi.java

Clase responsable de realizar consultas a una API externa para obtener información sobre libros y autores.

### ConvierteDatos.java

Esta clase se encarga de convertir los datos obtenidos de la API para su uso en la aplicación.

### AutorRepository.java

Interfaz que maneja las operaciones de la base de datos relacionadas con los autores.

## Clases Modelo y Mapeo de Entidades

En este proyecto, utilizamos varias clases modelo para representar las entidades del dominio, como autores y libros. Estas clases están mapeadas a tablas de la base de datos utilizando JPA (Java Persistence API).

### Autor.java

La clase `Autor` representa la entidad "Autor" en la base de datos. Esta clase incluye atributos como el nombre del autor, su fecha de nacimiento y fallecimiento, así como una lista de libros asociados. La relación entre autores y libros se gestiona mediante una asociación de uno a muchos.

#### Atributos principales:
- **id**: Identificador único del autor.
- **nombre**: Nombre del autor.
- **fechaDeNacimiento**: Año de nacimiento del autor.
- **fechaDeFallecimiento**: Año de fallecimiento del autor (puede ser nulo si el autor está vivo).
- **libros**: Lista de libros escritos por el autor.

### Datos.java

La clase `Datos` se utiliza para mapear la estructura JSON de la respuesta de la API. Esta clase contiene el total de resultados y una lista de libros obtenidos de la API.

#### Atributos principales:
- **total**: Número total de resultados.
- **libros**: Lista de objetos `DatosLibro` que representan los libros obtenidos de la API.

### DatosLibro.java

La clase `DatosLibro` representa la información de un libro obtenida de la API. Esta clase incluye atributos como el título del libro, una lista de autores, los idiomas en los que está disponible y el número de descargas.

#### Atributos principales:
- **titulo**: Título del libro.
- **autores**: Lista de objetos `DatosAutor` que representan los autores del libro.
- **idiomas**: Lista de idiomas en los que está disponible el libro.
- **numeroDeDescargas**: Número de descargas del libro.

## Desarrollado por
- Aliendro Renzo

## Instrucciones de Uso

1. Clona este repositorio en tu máquina local.
2. Abre el proyecto en IntelliJ IDEA u otro IDE de tu elección.
3. Configura la conexión a la base de datos en el archivo de propiedades correspondiente.
4. Ejecuta la clase `Principal.java` para iniciar el programa.
5. Sigue las instrucciones en pantalla para buscar libros, autores y obtener estadísticas.