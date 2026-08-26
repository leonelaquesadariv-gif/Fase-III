## ADR-002: Lenguaje de programación

**Estado:** Aceptado  
**Decisión:** Utilizar Java como lenguaje principal.

### Contexto

El sistema contiene varias reglas de negocio, como verificar prerrequisitos, disponibilidad de cupos, permisos y choques de horario.

### Decisión tomada

El backend del SIMU será desarrollado en Java.

### Justificación

Java permite organizar el código mediante clases, objetos, interfaces y módulos. Esto facilitará representar elementos del sistema como estudiantes, cursos, matrículas, docentes y horarios.

También se selecciona porque trabaja directamente con Spring Boot, que será el framework principal del proyecto.

### Alternativas consideradas

- **Python:** posee una sintaxis más sencilla, pero el equipo tendría que utilizar otro framework.
- **JavaScript con Node.js:** permitiría utilizar el mismo lenguaje en frontend y backend, pero podría complicar el control de tipos y algunas reglas académicas.

### Consecuencias

El proyecto tendrá una estructura clara y organizada. Sin embargo, los integrantes deberán aprender conceptos como inyección de dependencias, anotaciones y manejo de excepciones.

---