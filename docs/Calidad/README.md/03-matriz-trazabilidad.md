# Matriz de trazabilidad

---

## 1. Matriz principal: RF ↔ HU ↔ CP

| ID | Requisito | Historia de usuario | Caso de prueba | Estado |
|---|---|---|---|---|
| **RF01** | Inicio de sesión | HU01 – Registro de estudiantes | CP01 – Verificar autenticación correcta | Diseñado |
| **RF02** | Oferta de cursos | HU02 – Matrícula de cursos | CP02 – Mostrar cursos según carrera y período | Diseñado |
| **RF03** | Validación de prerrequisitos | HU02 – Matrícula de cursos | CP03 – Rechazar matrícula si no cumple requisitos | Diseñado |
| **RF04** | Disponibilidad de cupos | HU02 – Matrícula de cursos | CP04 – No permitir matrícula cuando el grupo esté lleno | Diseñado |
| **RF05** | Conflictos de horario | HU02 – Matrícula de cursos | CP05 – Impedir matrícula con choque de horarios | Diseñado |
| **RF06** | Agregar o eliminar cursos | HU02 – Matrícula de cursos | CP06 – Actualizar el horario después de modificar la matrícula | Diseñado |
| **RF07** | Gestión de cursos | HU03 – Gestión de cursos | CP07 – Crear, modificar y eliminar cursos correctamente | Diseñado |
| **RF08** | Consulta y descarga de horario | HU04 – Consulta de horario | CP08 – Descargar el horario en formato imprimible | Diseñado |
| **RF09** | Reportes de matrícula | HU05 – Reportes | CP09 – Exportar reporte en PDF o Excel | Diseñado |


## 2. Matriz inversa: historia de usuario ↔ requisitos

Permite verificar que ninguna historia quede sin requisitos y que ningún requisito quede huérfano.

| Historia | Actor | Requisitos que la implementan | Casos de prueba | Cobertura |
|---|---|---|---|---|
| **HU01** – Registro de estudiantes | Estudiante | RF01 | CP01 | Completa |
| **HU02** – Matrícula de cursos | Estudiante | RF02, RF03, RF04, RF05, RF06 | CP02, CP03, CP04, CP05, CP06 | Completa |
| **HU03** – Gestión de cursos | Administrador académico | RF07 | CP07 |  Completa |
| **HU04** – Consulta del horario | Estudiante | RF08 | CP08 |  Completa |
| **HU05** – Generación de reportes | Administrador académico | RF09 | CP09 | Completa |

**Verificación:** los 9 requisitos funcionales están asociados a alguna historia y los 9 casos de prueba están asociados a algún requisito. No existen requisitos huérfanos ni historias sin cobertura de prueba.

## 3. Trazabilidad de las decisiones arquitectónicas

| ADR | Decisión | Requisitos que atiende |
|---|---|---|
| [ADR-001](adr/adr-001-patron-arquitectura.md) | Monolito modular en capas | RNF01, RF03, RF04, RF05 |
| [ADR-002](adr/adr-002-lenguaje-programacion.md) | Java como lenguaje principal | RNF01, RNF06 |
| [ADR-003](adr/adr-003-framework-backend.md) | Spring Boot, Spring Security y Maven | RF01, RF07, RNF01, RNF04 |
| [ADR-004](adr/adr-004-base-de-datos.md) | MYSQL | RF02, RF04, RNF02 |
| [ADR-005](adr/adr-005-interfaz-de-usuario.md) | Thymeleaf, HTML, CSS, JavaScript y Bootstrap | RF08, RNF05, RNF06 |
| [ADR-006](adr/adr-006-seguridad.md) | Hash BCrypt, HTTPS/TLS, roles y expiración de sesión | RF01, RF07, RF09, RNF04 |
| [ADR-007](adr/adr-007-herramientas.md) | Git, GitHub, Visual Studio Code, Markdown, PlantUML | — (soporte al proceso; no atiende requisitos del producto) |

---