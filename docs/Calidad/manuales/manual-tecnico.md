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