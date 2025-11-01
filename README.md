# 📝 Sistema de Tareas (JavaFX + Spring Boot)

Aplicación de escritorio desarrollada con **JavaFX** y **Spring Boot**, que permite gestionar un listado de tareas almacenadas en una base de datos **MySQL**.  
Ofrece una interfaz moderna y simple con operaciones CRUD completas (crear, leer, actualizar y eliminar).

---

## 🖼️ Vista general

> Interfaz del sistema donde se pueden agregar, modificar, eliminar y limpiar tareas registradas en la base de datos.

<img width="649" height="457" alt="sistema tareas" src="https://github.com/user-attachments/assets/8c1d8d7e-e6e3-4a8b-9aea-0d4fe77de667" />

<img width="650" height="457" alt="sistema tareas modificar" src="https://github.com/user-attachments/assets/fd545f9d-0707-4c13-b9c0-92331682afe8" />

---

## ✨ Características principales

- 📋 **Gestión completa de tareas**: permite altas, modificaciones y bajas.  
- 💼 **Campos definidos**: *Tarea*, *Responsable* y *Estatus* con validaciones básicas.  
- 💾 **Persistencia con Spring Data JPA** y base MySQL.  
- ⚙️ **Arquitectura limpia (MVC)**: separación entre vista, servicio, repositorio y entidad.  
- 🔄 **Integración JavaFX + Spring Boot**: los controladores JavaFX reciben dependencias desde el contexto de Spring.  

---

## 🧱 Arquitectura del proyecto

```text
src/main/java/gm/tareas/
├── TareasApplication.java        # Punto de entrada (JavaFX + Spring Boot)
├── controlador/IndexControlador  # Lógica del formulario principal
├── modelo/Tarea.java             # Entidad JPA
├── repositorio/TareaRepositorio  # Repositorio Spring Data JPA
└── servicio/                     # Interfaces y clases de servicio
```
📁 La interfaz gráfica se define en:
src/main/resources/template/index.fxml
📄 Configuración y conexión a la base de datos:
src/main/resources/application.properties

## 🧰 Requisitos previos

JDK 21 o superior
Maven 3.9+
Servidor MySQL en ejecución

##⚙️ Configuración de la base de datos
Editá el archivo application.properties con tus credenciales:

spring.datasource.url=jdbc:mysql://localhost:3306/tareas_db?createDatabaseIfNotExist=true&useSSL=false&serverTimezone=UTC
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

✅ El esquema tareas_db y la tabla tarea se generan automáticamente al iniciar.

## 🚀 Ejecución
Desde la terminal: mvn clean spring-boot:run O desde tu IDE favorito (IntelliJ, Eclipse, VS Code): ejecutá la clase gm.tareas.TareasApplication.


## 💡 Uso de la aplicación

1. Al abrir el programa se listan automáticamente las tareas existentes.
2. Completá los campos y presioná Agregar para crear una nueva tarea.
3. Seleccioná una fila de la tabla para editar o eliminar.
4. Presioná Limpiar Form para resetear el formulario.
