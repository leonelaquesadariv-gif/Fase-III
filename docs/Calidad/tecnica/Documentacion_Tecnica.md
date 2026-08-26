
# Documentación Técnica — SIMU (Sistema Integral de Matrícula Universitaria)



El desarrollo de SIMU se sustenta en el siguiente stack tecnológico:

- **Lenguaje de programación:** Java (versión 17 LTS). Es la base de la lógica de negocio del backend.
- **Framework backend:** Spring Boot. Expone los servicios REST, gestiona la inyección de dependencias y administra la seguridad de la aplicación.
- **Base de datos:** MySQL. Encargada de la persistencia permanente de la información académica.
- **Gestor de dependencias:** Maven. Administra la compilación y el ciclo de vida del proyecto.
- **Control de versiones:** Git y GitHub. Utilizados para el versionado y el trabajo colaborativo del equipo.

---

## 2. Arquitectura técnica del sistema

SIMU se estructura mediante una arquitectura en capas, patrón estándar en aplicaciones construidas sobre Spring Boot, que separa responsabilidades de forma clara y facilita el mantenimiento y las pruebas del sistema.

La capa **Controller** recibe las peticiones HTTP provenientes del cliente, valida el formato de la información recibida y delega su procesamiento a la capa de servicio. Sus componentes principales son `CursoController` y `MatriculaController`.

La capa **Service** concentra la lógica de negocio del sistema, incluyendo la validación de prerrequisitos, el control de cupos disponibles y la detección de conflictos de horario. Sus componentes principales son `MatriculaService` y `HorarioService`.

La capa **Repository** gestiona el acceso a los datos mediante Spring Data JPA. Sus componentes principales son `CursoRepository` y `EstudianteRepository`.

Las **Entidades o Modelos** representan las tablas de la base de datos: `Curso`, `Estudiante`, `Matricula` y `Docente`.

El sistema utiliza **DTO** (Data Transfer Objects), como `CursoDTO` y `MatriculaRequestDTO`, para transferir información entre el cliente y la API sin exponer directamente las entidades del dominio.

La capa de **Configuración y Seguridad** administra la autenticación y las políticas de CORS del sistema.

### Flujo de una petición

1. El cliente (frontend o herramienta de prueba como Postman) envía una solicitud HTTP al controlador correspondiente.
2. El controlador valida el formato de la solicitud y la transforma en un DTO.
3. La capa de servicio aplica las reglas de negocio: verifica la disponibilidad de cupos y el cumplimiento de prerrequisitos antes de autorizar una matrícula.
4. El servicio utiliza el repositorio correspondiente para consultar o modificar los datos almacenados en MySQL.
5. El resultado se transforma nuevamente en un DTO y se devuelve al cliente como una respuesta en formato JSON.

---

## 3. Estructura del código fuente

El backend de SIMU se organiza bajo el paquete raíz `com.simu`, distribuyendo el código en subpaquetes según su responsabilidad dentro de la arquitectura:

- `com.simu.controller` — Contiene los controladores REST que exponen los endpoints de la API.
- `com.simu.service` — Agrupa las interfaces e implementaciones de la lógica de negocio.
- `com.simu.repository` — Contiene las interfaces de tipo `JpaRepository` para el acceso a los datos.
- `com.simu.model` — Reúne las entidades JPA mapeadas a las tablas de la base de datos.
- `com.simu.dto` — Agrupa los objetos de transferencia de datos utilizados en la comunicación de la API.
- `com.simu.config` — Centraliza la configuración de seguridad, CORS y otros componentes generales del sistema.
- `com.simu.exception` — Gestiona el manejo centralizado de excepciones mediante un `ControllerAdvice`.
- `com.simu.util` — Contiene las clases utilitarias para validaciones y conversiones de datos.

Esta organización se traduce en la siguiente estructura de carpetas a nivel de proyecto:

```
SIMU-backend/
├── src/main/java/com/simu/
│   ├── controller/
│   ├── service/
│   ├── repository/
│   ├── model/
│   ├── dto/
│   ├── config/
│   ├── exception/
│   └── util/
├── src/main/resources/application.properties
├── src/test/java/com/simu/...
```

---

## 4. Documentación de la API

### 4.1 Módulo de Autenticación

- `POST /api/auth/registro` — Registra un nuevo estudiante en el sistema.
- `POST /api/auth/login` — Autentica al usuario e emite un token de acceso.

### 4.2 Módulo de Cursos (administración académica)

- `GET /api/cursos` — Lista los cursos disponibles, con filtros por carrera y período académico.
- `POST /api/cursos` — Crea un curso (rol administrador).
- `PUT /api/cursos/{id}` — Modifica un curso existente.
- `DELETE /api/cursos/{id}` — Elimina un curso.
- `GET /api/cursos/{id}/cupos` — Consulta los cupos disponibles en tiempo real.

### 4.3 Módulo de Matrícula (estudiantes)

- `POST /api/matricula` — Matricula uno o varios cursos, validando prerrequisitos, cupos y choques de horario.
- `DELETE /api/matricula/{cursoId}` — Elimina un curso matriculado dentro del período autorizado.
- `GET /api/matricula/horario` — Consulta el horario matriculado del estudiante.
- `GET /api/matricula/horario/pdf` — Descarga el horario en formato PDF.

### 4.4 Módulo de Reportes (administración)

- `GET /api/reportes/matricula` — Genera el reporte de matrícula por período académico.
- `GET /api/reportes/matricula/exportar` — Exporta el reporte en formato PDF o Excel.

La documentación completa de cada endpoint (parámetros, cuerpo de la solicitud, códigos de respuesta HTTP y ejemplos en formato JSON) se genera mediante `springdoc-openapi`, herramienta integrada al proyecto que produce la documentación interactiva de la API a través de una interfaz Swagger.

---

## 5. Manual técnico de instalación

### 5.1 Requisitos previos

- JDK 17 o superior, instalado y configurado mediante la variable de entorno `JAVA_HOME`.
- Apache Maven (o el wrapper `mvnw` incluido en el proyecto).
- Servidor MySQL en su versión 8.x en ejecución, con un usuario y una base de datos creados para SIMU.
- Git, para clonar el repositorio.
- Un entorno de desarrollo integrado compatible con Spring Boot, como IntelliJ IDEA o Visual Studio Code con extensiones de Java.

### 5.2 Pasos de instalación

1. Clonar el repositorio del proyecto mediante `git clone <https://github.com/leonelaquesadariv-gif/Sistema-Integral-de-Matr-cula-Universitaria-.git>`.
2. Ingresar a la carpeta del backend con `cd SIMU/SIMU-backend`.
3. Crear la base de datos correspondiente en MySQL mediante `CREATE DATABASE simu_db;`.
4. Configurar las credenciales de conexión dentro del archivo `application.properties`, ubicado en `src/main/resources/`.
5. Compilar el proyecto mediante `mvn clean install`.
6. Ejecutar la aplicación con `mvn spring-boot:run`.
7. Verificar que el servicio responde correctamente accediendo a `http://localhost:8080`.

### 5.3 Configuración (application.properties)

Las credenciales de conexión a la base de datos se gestionan mediante variables de entorno, evitando así que contraseñas o datos sensibles queden expuestos en el repositorio del proyecto. El archivo `.env.example` incluido en el repositorio sirve como referencia para configurar dichas variables. La configuración del sistema es la siguiente:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/simu_db
spring.datasource.username=${DB_USER}
spring.datasource.password=${DB_PASSWORD}
spring.jpa.hibernate.ddl-auto=update
server.port=8080
```

---

## 6. Mantenimiento del sistema

La **gestión de dependencias** del proyecto se realiza a través de Maven mediante el archivo `pom.xml`. Las versiones de las dependencias se revisan periódicamente mediante el comando `mvn versions:display-dependency-updates`, con el fin de mantener el proyecto actualizado y libre de vulnerabilidades conocidas.

Los **cambios en la base de datos** se gestionan mediante Flyway, herramienta de migraciones versionadas que mantiene la trazabilidad completa de los cambios realizados en el esquema de la base de datos. Cada cambio estructural relevante queda registrado como un Registro de Decisión Arquitectónica (ADR) dentro de la carpeta `docs/ADR/`, siguiendo la convención establecida en el proyecto.

El **registro y monitoreo** del sistema se realiza mediante Logback, el sistema de logging integrado en Spring Boot, que registra accesos, errores y operaciones críticas como la matrícula de cursos y los cambios en la disponibilidad de cupos. Los niveles de log están definidos según el ambiente de ejecución: DEBUG en desarrollo e INFO/WARN en producción.

Las **pruebas** del sistema incluyen pruebas unitarias con JUnit 5 sobre la capa de servicio, donde se concentran las reglas de negocio relacionadas con prerrequisitos, cupos y conflictos de horario, así como pruebas de integración sobre los endpoints principales de la API.

El **control de versiones** del proyecto sigue un flujo de ramas de trabajo (`main`, `develop` y `feature-*`), y los cambios relevantes quedan registrados en el archivo `CHANGELOG`. Las decisiones arquitectónicas del sistema están documentadas mediante ADR en la carpeta `docs/ADR/`.

---

