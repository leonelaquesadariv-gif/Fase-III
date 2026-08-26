## ADR-003: Framework del backend

**Estado:** Aceptado 
**Decisión:** Utilizar Spring Boot, Spring Security y Maven.

### Contexto

El SIMU necesita manejar formularios, usuarios, permisos, conexión con la base de datos y validaciones académicas.

### Decisión tomada

Se utilizará:

- **Spring Boot:** para construir la aplicación web.
- **Spring Security:** para controlar inicio de sesión, roles y permisos.
- **Maven:** para administrar las dependencias del proyecto.

### Justificación

Estas herramientas permiten mantener una estructura ordenada y evitan tener que configurar manualmente muchos componentes. Además, Spring Security puede diferenciar los permisos de estudiantes, docentes y administradores.

### Alternativas consideradas

Se consideraron Django y Express.js, pero Spring Boot se adapta mejor a la selección de Java como lenguaje principal.

### Consecuencias

El sistema tendrá una base tecnológica organizada, aunque al inicio será necesario estudiar la estructura y las anotaciones utilizadas por Spring.

---