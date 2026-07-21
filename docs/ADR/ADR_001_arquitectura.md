#  Decisiones arquitectónicas (ADR)

## 1. Introducción

Los siguientes registros de decisiones arquitectónicas se elaboraron para el **SIMU – Sistema Integral de Matrícula Universitaria**. Se tomaron en cuenta funciones como el inicio de sesión, consulta y matrícula de cursos, validación de prerrequisitos, control de cupos, detección de choques de horario y generación de reportes.

También se consideraron requisitos como responder en menos de tres segundos, soportar aproximadamente 2.000 usuarios concurrentes, proteger los datos personales y funcionar en navegadores modernos.

Estas decisiones son propuestas iniciales para el desarrollo del proyecto y podrían modificarse conforme se realicen pruebas.

---

## ADR-001: Patrón de arquitectura

**Estado:** Propuesto  
**Decisión:** Utilizar una arquitectura monolítica modular organizada por capas.

### Contexto

El SIMU necesita gestionar estudiantes, cursos, horarios, cupos, matrículas y reportes. Aunque existen diferentes módulos, todos forman parte del mismo proceso académico.

### Decisión tomada

El sistema se desarrollará como una sola aplicación, pero separada en los siguientes módulos:

- Usuarios y autenticación.
- Estudiantes.
- Cursos y grupos.
- Matrícula.
- Horarios.
- Reportes.
- Administración.

Cada módulo se organizará en capas:

1. **Presentación:** pantallas y formularios.
2. **Controladores:** reciben las solicitudes del usuario.
3. **Servicios:** aplican las reglas de negocio.
4. **Acceso a datos:** consulta y guarda información.
5. **Base de datos:** almacena los registros.

### Justificación

Se eligió esta arquitectura porque resulta más sencilla de comprender, desarrollar y documentar para un equipo de estudiantes. También permite mantener separadas las responsabilidades sin asumir desde el inicio la complejidad de una arquitectura de microservicios.

### Alternativa descartada

Se consideraron los microservicios, pero se descartaron para la primera versión porque requieren configurar comunicación entre servicios, despliegues separados, monitoreo y mayor infraestructura.

### Consecuencias

La primera versión será más fácil de desarrollar y desplegar. Como desventaja, si el sistema crece considerablemente, algunos módulos podrían necesitar separarse en el futuro.

---