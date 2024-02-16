# Proyecto Final ADA

Proyecto para la gestión de una Base de Datos llamada "proyecto" la cual cuenta con las tablas: departamento, empleado, empleado_proyecto y proyecto.

## Descripción del proyecto

Este proyecto ha sido creado con la finalidad de desarrollar un Sistema de Gestión de Empleados utilizando Java y aplicando los conceptos y técnicas aprendidas en el módulo de Acceso a Datos del ciclo de desarrollo de aplicaciones multiplataforma (DAM). Éste sistema nos permite gestionar información de los empleados de una empresa utilizando operaciones CRUD. 

### Script utilizado para crear las tablas

```
-- Eliminar tablas si existen
DROP TABLE IF EXISTS Empleado_Proyecto;
DROP TABLE IF EXISTS Empleado;
DROP TABLE IF EXISTS Proyecto;
DROP TABLE IF EXISTS Departamento;

-- Crear tabla Departamentos
CREATE TABLE Departamento (
    id_departamento INT AUTO_INCREMENT PRIMARY KEY,
    nombre_departamento VARCHAR(50) NOT NULL
);

-- Crear tabla Empleados
CREATE TABLE Empleado (
    id_empleado INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    apellido VARCHAR(50) NOT NULL,
    fecha_nacimiento DATE,
    id_departamento INT,
    puesto VARCHAR(50),
	email VARCHAR(100),
	telefono VARCHAR(20),
    FOREIGN KEY (id_departamento) REFERENCES Departamento(id_departamento)
);

-- Crear tabla Proyectos
CREATE TABLE Proyecto (
    id_proyecto INT AUTO_INCREMENT PRIMARY KEY,
    nombre_proyecto VARCHAR(100) NOT NULL,
    descripcion TEXT,
    fecha_inicio DATE,
    fecha_fin DATE
);

-- Crear tabla de relación entre Empleado y Proyecto
CREATE TABLE Empleado_Proyecto (
    id_empleado INT,
    id_proyecto INT,
    PRIMARY KEY (id_empleado, id_proyecto),
    FOREIGN KEY (id_empleado) REFERENCES Empleado(id_empleado),
    FOREIGN KEY (id_proyecto) REFERENCES Proyecto(id_proyecto)
);

-- Insertar Departamentos
INSERT INTO Departamento (nombre_departamento) VALUES
    ('Desarrollo de Productos'),
    ('Investigación de Mercado'),
    ('Servicio al Cliente'),
    ('Contabilidad'),
    ('Recursos Tecnológicos'),
    ('Desarrollo de Negocios'),
    ('Calidad y Control'),
    ('Administración');

-- Insertar Empleados
INSERT INTO Empleado (nombre, apellido, fecha_nacimiento, id_departamento, puesto, email, telefono) VALUES
    ('Gabriel', 'Ramírez', '1993-05-20', 1, 'Ingeniero de Software', 'gabriel.ramirez@gmail.com', '611 223 344'),
    ('Verónica', 'Díaz', '1985-08-15', 2, 'Analista de Mercado', 'veronica.diaz@outlook.com', '655 667 788'),
    ('Diego', 'Hernández', '1990-03-25', 3, 'Representante de Servicio al Cliente', 'diego.hernandez@hotmail.com', '622 334 455'),
    ('Marina', 'González', '1988-11-10', 4, 'Contador', 'marina.gonzalez@gmail.com', '644 445 566'),
    ('Ricardo', 'Fernández', '1995-01-12', 5, 'Técnico de Redes', 'ricardo.fernandez@outlook.com', '677 556 677'),
    ('Natalia', 'López', '1992-04-30', 6, 'Ejecutivo de Desarrollo de Negocios', 'natalia.lopez@hotmail.com', '688 667 788'),
    ('Laura', 'Alvarez', '1991-07-22', 7, 'Inspector de Calidad', 'laura.alvarez@gmail.com', '655 778 899'),
    ('Sergio', 'Martínez', '1987-09-18', 8, 'Gerente de Recursos Humanos', 'sergio.martinez@outlook.com', '677 889 900'),
    ('Roberto', 'Vargas', '1986-12-05', 1, 'Diseñador de Experiencia de Usuario', 'roberto.vargas@hotmail.com', '633 445 566'),
    ('Elena', 'Morales', '1994-02-28', 2, 'Investigador de Mercado', 'elena.morales@gmail.com', '655 667 788'),
    ('Andrés', 'Gómez', '1989-06-17', 3, 'Especialista en Soporte Técnico', 'andres.gomez@outlook.com', '622 334 455'),
    ('Marta', 'Dominguez', '1990-10-09', 4, 'Analista Financiero', 'marta.dominguez@gmail.com', '633 445 566'),
    ('Javier', 'Pérez', '1993-03-15', 5, 'Desarrollador Web', 'javier.perez@outlook.com', '655 556 677'),
    ('Carolina', 'Sánchez', '1988-07-08', 6, 'Gerente de Desarrollo de Negocios', 'carolina.sanchez@hotmail.com', '677 667 788'),
    ('Daniel', 'Suarez', '1991-11-27', 7, 'Inspector de Control de Calidad', 'daniel.suarez@gmail.com', '688 778 899'),
    ('Patricia', 'Ortiz', '1987-01-31', 8, 'Director Administrativo', 'patricia.ortiz@outlook.com', '699 889 900'),
    ('Alejandro', 'García', '1984-04-18', 1, 'Líder de Proyecto', 'alejandro.garcia@hotmail.com', '611 445 566'),
    ('Sofía', 'Rodríguez', '1995-06-24', 2, 'Analista de Datos', 'sofia.rodriguez@gmail.com', '622 667 788'),
    ('José', 'Fernández', '1992-09-11', 3, 'Representante de Atención al Cliente', 'jose.fernandez@outlook.com', '633 334 455'),
    ('Ana', 'Gutiérrez', '1986-12-30', 4, 'Contador Principal', 'ana.gutierrez@hotmail.com', '644 445 566'),
    ('Pedro', 'Martínez', '1989-02-14', 5, 'Especialista en Seguridad Informática', 'pedro.martinez@gmail.com', '655 556 677'),
    ('Luisa', 'López', '1994-07-05', 6, 'Ejecutivo de Desarrollo de Negocios', 'luisa.lopez@outlook.com', '677 667 788'),
    ('Marcos', 'Torres', '1993-11-20', 7, 'Inspector de Calidad Asociado', 'marcos.torres@hotmail.com', '688 778 899'),
    ('Lucía', 'Ruiz', '1988-01-25', 8, 'Especialista en Recursos Humanos', 'lucia.ruiz@gmail.com', '699 889 900'),
    ('Rosa', 'Hernández', '1990-04-08', 1, 'Desarrollador de Software', 'rosa.hernandez@outlook.com', '611 445 566'),
    ('Jorge', 'Sánchez', '1987-08-19', 2, 'Analista de Investigación de Mercado', 'jorge.sanchez@hotmail.com', '622 556 677'),
    ('Marcela', 'Gómez', '1992-10-12', 3, 'Especialista en Servicio al Cliente', 'marcela.gomez@gmail.com', '633 667 788'),
    ('Gustavo', 'Martín', '1985-02-03', 4, 'Contador Financiero', 'gustavo.martin@outlook.com', '644 778 899'),
    ('Camila', 'Pérez', '1996-06-16', 5, 'Técnico de Sistemas', 'camila.perez@hotmail.com', '655 889 900'),
    ('Fernando', 'Vega', '1989-09-28', 6, 'Ejecutivo de Desarrollo de Negocios', 'fernando.vega@gmail.com', '677 445 566');


-- Insertar datos en Proyectos
INSERT INTO Proyecto (nombre_proyecto, descripcion, fecha_inicio, fecha_fin) VALUES
    ('Implementación de CRM', 'Implementación de un sistema CRM para mejorar la gestión de relaciones con los clientes', '2023-10-15', '2024-03-31'),
    ('Lanzamiento de Producto XYZ', 'Planificación y ejecución del lanzamiento del producto XYZ en el mercado nacional', '2024-01-15', '2024-06-30'),
    ('Actualización de Infraestructura IT', 'Actualización de servidores y equipos informáticos para mejorar la eficiencia operativa', '2023-12-01', '2024-05-31'),
    ('Expansión de Mercado Internacional', 'Exploración y expansión de oportunidades de mercado en regiones internacionales', '2024-03-01', '2024-09-30'),
    ('Desarrollo de Plataforma E-Commerce', 'Desarrollo de una plataforma de comercio electrónico para mejorar las ventas en línea', '2024-02-15', '2024-08-15'),
    ('Optimización de Procesos de Producción', 'Identificación y optimización de procesos para aumentar la eficiencia en la planta de producción', '2024-04-01', '2024-10-31'),
    ('Reestructuración de Marca', 'Revisión y actualización de la identidad de marca de la empresa para mejorar la percepción del cliente', '2024-05-01', '2024-11-30'),
    ('Desarrollo de Aplicación Móvil Cliente', 'Creación de una aplicación móvil para mejorar la experiencia del cliente con nuestros productos y servicios', '2024-06-15', '2025-01-15'),
    ('Implementación de Sistema de Gestión', 'Implementación de un sistema de gestión integrado para mejorar la eficiencia operativa en todas las áreas de la empresa', '2024-07-01', '2025-02-28'),
    ('Estrategia de Marketing Digital', 'Desarrollo e implementación de una estrategia integral de marketing digital para aumentar la visibilidad de la marca en línea', '2024-08-15', '2025-03-15');

-- Insertar asignación de empleados-proyectos
INSERT INTO Empleado_Proyecto (id_empleado, id_proyecto) VALUES
    (1, 1),
    (2, 2),
    (3, 1),
    (4, 3),
    (5, 2),
    (6, 4),
    (7, 3),
    (8, 5),
    (9, 4),
    (10, 6),
    (11, 5),
    (12, 7),
    (13, 6),
    (14, 8),
    (15, 7),
    (16, 9),
    (17, 8),
    (18, 10),
    (19, 9),
    (20, 1),
    (21, 10),
    (22, 2),
    (23, 3),
    (24, 4),
    (25, 5),
    (26, 6),
    (27, 7),
    (28, 8),
    (29, 9),
    (30, 10);
```

### Instalación

* Meterse en carpeta x y hacer noseque


A step by step guide that will tell you how to get the development environment up and running.

```
$ Primero ...
$ Another step
$ Final step
```

## Funcionamiento

A few examples of useful commands and/or tasks.

```
$ First example
$ Second example
$ And keep this in mind
```

## Additional Documentation and Acknowledgments

* Project folder on server:
* Confluence link:
* Asana board:
* etc...
