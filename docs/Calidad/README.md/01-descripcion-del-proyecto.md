
## 1. Planteamiento del problema

Las universidades administran cada cuatrimestre el proceso de matrícula de cientos de estudiantes. En muchas instituciones este proceso aún depende de procedimientos manuales o parcialmente digitalizados, lo que produce cinco problemas recurrentes:

| Problema | Efecto sobre el proceso |
|---|---|
| Largas filas presenciales | Congestión en los períodos de matrícula y pérdida de tiempo para el estudiante |
| Errores en la inscripción de cursos | Matrículas incorrectas que deben corregirse manualmente después |
| Conflictos de horario | Estudiantes matriculados en cursos que se traslapan |
| Sobrecupo en grupos | Grupos que superan su capacidad por falta de control en tiempo real |
| Demoras en la validación de requisitos | Revisión manual de prerrequisitos, lenta y propensa a error |

## 2. Solución propuesta

El **SIMU – Sistema Integral de Matrícula Universitaria** es una plataforma web que permite al estudiante realizar su matrícula de manera digital, rápida y segura, y al personal administrativo gestionar cursos, horarios, docentes y cupos disponibles.

El sistema interviene sobre cada uno de los problemas anteriores mediante validaciones automáticas que ocurren antes de confirmar una matrícula:

1. La matrícula se realiza en línea, lo que elimina la fila presencial.
2. El sistema valida los prerrequisitos del estudiante antes de permitir la inscripción de un curso.
3. El sistema verifica la disponibilidad de cupos en tiempo real y rechaza la matrícula si el grupo está lleno.
4. El sistema detecta choques de horario entre los cursos seleccionados.
5. La oferta académica y los reportes se mantienen centralizados y actualizados.

## 3. Justificación

**Automatiza el proceso de matrícula**, reduciendo la dependencia de procedimientos manuales que generan filas, demoras y errores en la inscripción de cursos.

**Disminuye los errores humanos**, ya que el sistema valida requisitos académicos, cupos disponibles y choques de horario antes de confirmar la matrícula. Esto mejora la confiabilidad del proceso y evita inconvenientes tanto para el estudiante como para el personal administrativo.

**Reduce el tiempo de inscripción**, porque el estudiante puede consultar la oferta académica, seleccionar cursos y confirmar su matrícula desde una plataforma digital, sin desplazarse ni depender de horarios de atención.

**Mantiene la información organizada y actualizada**, lo que facilita la gestión de cursos, horarios, docentes, cupos y reportes administrativos, y permite que las autoridades y el personal de registro tomen decisiones con información clara y disponible.

## 4. Audiencias de la documentación

La documentación del SIMU está dirigida a nueve audiencias, ya que no todos los usuarios necesitan la misma información. Algunas personas la usarán para aprender a utilizar el sistema, mientras que otras la necesitarán para administrar, mantener, evaluar o mejorar el software.

| # | Audiencia | Qué necesita de la documentación | Documentos del expediente |
|---|---|---|---|
| 1 | **Estudiantes** | Consultar cursos, revisar horarios, verificar requisitos, seleccionar materias y confirmar matrícula. Documentación clara, sencilla y práctica. |
| 2 | **Personal de registro o matrícula** | Apertura de períodos, validación de cupos, revisión de solicitudes, modificación de inscripciones y generación de reportes. |
| 3 | **Coordinadores de carrera** | Revisar la oferta académica, validar grupos, analizar cupos y dar seguimiento a la matrícula de su programa. |
| 4 | **Docentes** | Consultar listas de estudiantes matriculados, horarios asignados y grupos activos. |
| 5 | **Administradores del sistema (TI)** | Instalación, configuración, permisos, respaldo, recuperación ante fallos, seguridad y mantenimiento. |
| 6 | **Equipo de desarrollo** | Requisitos funcionales y no funcionales, arquitectura, reglas de negocio, historias de usuario, criterios de aceptación y trazabilidad. | 
| 7 | **Soporte técnico** | Guías de solución de problemas, errores frecuentes, mensajes del sistema y escalamiento de incidentes. |
| 8 | **Autoridades universitarias** | Información ejecutiva: objetivos, justificación, alcance, beneficios esperados y reportes disponibles. |
| 9 | **Auditoría, seguridad y cumplimiento** | Protección de datos, control de accesos, trazabilidad de operaciones, permisos y políticas internas. |

## 5. Actores del sistema

| Actor | Descripción | Historias asociadas |
|---|---|---|
| **Estudiante** | Usuario que se registra, consulta la oferta, matricula cursos, modifica su matrícula y descarga su horario. |
| **Administrador académico** | Usuario que gestiona la oferta de cursos y genera reportes de matrícula. | 
| **Docente** | Usuario con acceso de consulta a listas de estudiantes, horarios y grupos.

---
