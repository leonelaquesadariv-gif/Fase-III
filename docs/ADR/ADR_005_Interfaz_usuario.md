## ADR-005: Interfaz de usuario

**Estado:** Propuesto  
**Decisión:** Utilizar Thymeleaf, HTML, CSS, JavaScript y Bootstrap.

### Contexto

Los estudiantes necesitan una interfaz sencilla para consultar cursos, matricular materias y descargar su horario. Los administradores requieren formularios para gestionar cursos y generar reportes.

### Decisión tomada

Las páginas serán generadas con Thymeleaf y Spring Boot. Bootstrap será utilizado para crear formularios, botones, tablas, alertas y diseños adaptables.

### Justificación

Esta combinación reduce la cantidad de tecnologías que el equipo debe aprender. También permite desarrollar una interfaz funcional sin crear una aplicación frontend separada.

### Alternativa descartada

Se consideró React, pero para una primera versión aumentaría la complejidad, ya que sería necesario mantener por separado el frontend y el backend.

### Consecuencias

El desarrollo será más sencillo. Como limitación, algunas pantallas podrían ser menos dinámicas que las desarrolladas con una aplicación frontend independiente.

---