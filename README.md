1- Hacer un contador que muestra el recuento actual.
    - Botones para incrementar y decrementar el conteo.
    - Muestra la cantidad de clics para las acciones de incremento y disminución, restableciéndose después de alcanzar los 10 clics.

2- Crear una aplicación web sencilla donde los usuarios podrán introducir una palabra o frase para comprobar si es un palíndromo. La aplicación incluirá:
    - Un diseño limpio y responsivo.
    - Una entrada de texto para que el usuario ingrese texto.
    - Un botón para activar la comprobación del palíndromo.
    - Una sección de resultados que muestra si la entrada es un palíndromo.

3- Construir una aplicación que permita a los usuarios
    - Introducir una dirección de correo electrónico en un campo de entrada.
    - Validar el correo electrónico ingresado contra una expresión regular.
    - Muestra un mensaje de error si el formato del correo electrónico no es válido.
    - Proporciona retroalimentación visual cuando el correo electrónico es válido o no.

4- Desarrollar una aplicación interactiva de búsqueda de perfiles de GitHub. Esta aplicación
    - Incluye una barra de búsqueda donde los usuarios pueden introducir el nombre de usuario que desean ver.
    - Tras introducir el nombre de usuario, se activa una llamada a la API y se devuelven los datos del usuario introducido junto con los repositorios.

5- Crear una tabla ordenable y filtrable con JavaScript. 
    Esta tabla personalizada permite editar o eliminar elementos individuales, además de ordenarlos y filtrarlos según diferentes campos. Además, se incluye un formulario para que el usuario pueda editar y añadir fácilmente elementos a la tabla. Este formulario consta de tres elementos: el nombre del elemento, su categoría y el año de lanzamiento.

6- Construir un sistema de gestión de bases de datos de empleados utilizando JavaScript.
    - El sistema de gestión de bases de datos de empleados es la recopilación de datos de los empleados, como nombres, nombre y apellido, correo electrónico, números de contacto, salario y fecha de nacimiento, etc.
    - Proporciona una forma sencilla de acceder y administrar la lista de empleados en un solo lugar.
    - Se puede agregar un nuevo empleado con detalles válidos junto con una fuente de imagen opcional proporcionada en el formulario de adición, y también se puede eliminar de la base de datos.




////////// crear BD ////////////////////////

CREATE DATABASE IF NOT EXISTS tarea_rocio
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_unicode_ci;
 
USE tarea_rocio;
 
CREATE TABLE IF NOT EXISTS users (
    id            INT AUTO_INCREMENT PRIMARY KEY,
    nombre        VARCHAR(100)  NOT NULL,
    edad          INT           NOT NULL DEFAULT 0,
    ciudad        VARCHAR(100)  NOT NULL DEFAULT '',
    departamento  VARCHAR(100)  NOT NULL DEFAULT '',
    salario       DECIMAL(10,2) NOT NULL DEFAULT 0.00,
    estado        ENUM('Activo','Inactivo','Suspendido') NOT NULL DEFAULT 'Activo',
    created_at    TIMESTAMP DEFAULT CURRENT_TIMESTAMP
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
 
-- Datos de ejemplo
INSERT INTO users (nombre, edad, ciudad, departamento, salario, estado) VALUES
('Ana García',      28, 'Madrid',     'Marketing',    2800.00, 'Activo'),
('Carlos López',    35, 'Barcelona',  'Desarrollo',   3500.00, 'Activo'),
('María Rodríguez', 42, 'Sevilla',    'RRHH',         2200.00, 'Inactivo'),
('Pedro Martínez',  31, 'Valencia',   'Ventas',       2600.00, 'Activo'),
('Laura Sánchez',   26, 'Bilbao',     'Diseño',       2400.00, 'Activo'),
('Diego Fernández', 38, 'Zaragoza',   'Finanzas',     3100.00, 'Suspendido'),
('Sofía Jiménez',   29, 'Málaga',     'Desarrollo',   3200.00, 'Activo'),
('Andrés Torres',   45, 'Alicante',   'Dirección',    4500.00, 'Activo');

ALTER TABLE users
  ADD COLUMN email    VARCHAR(150) NOT NULL DEFAULT '',
  ADD COLUMN telefono VARCHAR(20)  NOT NULL DEFAULT '';

ALTER TABLE users 
ADD COLUMN fecha_nacimiento DATE NULL DEFAULT NULL ;

