# Matriz de consistencia con la Fase I

---

## 1. Elementos de la Fase I que deben respetarse

### 1.1 Requisitos funcionales

| ID | Resumen | Artefactos del avance #2 que deben cubrirlo |
|---|---|---|
| RF01 | Autenticación con credencial y contraseña | Caso de uso “Iniciar sesión”; diagrama de secuencia de autenticación; componente de seguridad en C4 |
| RF02 | Mostrar oferta de cursos por carrera y período | Caso de uso “Consultar oferta”; diagrama de clases (Curso, Grupo, Período) |
| RF03 | Validar prerrequisitos antes de matricular | Diagrama de secuencia/actividades de matrícula; reglas de negocio en arquitectura |
| RF04 | Verificar cupos en tiempo real y rechazar si el grupo está lleno | Diagrama de secuencia de matrícula; decisión sobre base de datos (ADR) que soporte concurrencia |
| RF05 | Detectar choques de horario | Diagrama de actividades de matrícula |
| RF06 | Agregar/eliminar cursos en inclusiones | Caso de uso “Modificar matrícula” |
| RF07 | Gestión de cursos por administrador (crear, modificar, eliminar) | Caso de uso administrativo; diagrama de clases |
| RF08 | Consultar y descargar horario imprimible | Caso de uso “Consultar horario” |
| RF09 | Reportes de matrícula exportables a PDF/Excel | Caso de uso “Generar reportes”; componente de reportes en C4 |

### 1.2 Requisitos no funcionales

| ID | Resumen | Dónde debe reflejarse |
|---|---|---|
| RNF01 | Respuesta de matrícula < 3 segundos | Decisiones de arquitectura y ADR (framework, base de datos) |
| RNF02 | 2 000 usuarios concurrentes sin degradarse | Modelo C4 (escalabilidad de contenedores), ADR de base de datos |
| RNF03 | Disponibilidad 99,5 % en período de matrícula | Arquitectura (redundancia, despliegue) |
| RNF04 | Contraseñas con hash; datos bajo HTTPS/TLS | Componente de seguridad en C4; ADR de herramientas |
| RNF05 | Matrícula sin capacitación previa (usabilidad) | Decisiones de interfaz; documentación de usuario (FAQ) |
| RNF06 | Compatibilidad con Chrome, Edge y Firefox (2 últimas versiones) | ADR de framework frontend |

### 1.3 Historias de usuario y actores

| ID | Historia | Actor | Casos de uso esperados en UML |
|---|---|---|---|
| HU01 | Registro de estudiantes | Estudiante | Registrarse, iniciar sesión |
| HU02 | Matrícula de cursos | Estudiante | Consultar oferta, seleccionar cursos, confirmar matrícula |
| HU03 | Gestión de cursos | Administrador académico | Crear/modificar/eliminar curso |
| HU04 | Consulta del horario matriculado | Estudiante | Consultar horario, descargar/imprimir horario |
| HU05 | Generación de reportes | Administrador académico | Generar reporte, exportar PDF/Excel |


## 2. Verificación por artefacto

Estado: ⬜ pendiente de entrega · 🔍 en revisión · ✅ consistente · ⚠️ con observaciones

### 2.1 README y estructura del repositorio

| Verificación | Estado |
|---|---|
| El READMa de carpetas cE describe el proyecto con el mismo nombre y alcance de la Fase I | ✅ |
| La estructuroincide con el índice del expediente | ✅ |


### 2.2 Diagramas UML 

| Verificación | Estado |
|---|---|
| Cada caso de uso se mapea a una HU (HU01 – HU05) sin inventar funcionalidades fuera de alcance |✅ |
| El diagrama de clases incluye las entidades del dominio: Estudiante, Curso, Grupo, Matrícula, Período, Horario, Reporte | ✅ |
| El diagrama de secuencia de matrícula refleja las validaciones RF03 → RF04 → RF05 | ✅ |
| El diagrama de actividades cubre el flujo completo de matrícula, incluidos los caminos de rechazo | ✅ |
| Los diagramas están en PlantUML o Mermaid, versionables en Git | ✅ |

### 2.3 Arquitectura y Modelo C4 

| Verificación | Estado |
|---|---|
| El diagrama de contexto incluye a los actores de la Fase I (estudiante, administrador; opcionalmente docente/coordinador) | ✅ |
| Los contenedores permiten cumplir RNF01, RNF02 y RNF03 (rendimiento, concurrencia, disponibilidad) | ✅ |
| Existe un componente o mecanismo explícito de seguridad (RNF04) | ✅ |
| La arquitectura elegida está explicada y justificada en prosa | ✅ |

### 2.4 ADR 

| Verificación | Estado |
|---|---|
| Cada ADR sigue el formato: contexto, decisión, alternativas, consecuencias | ✅ |
| El ADR de lenguaje/framework justifica la decisión frente a RNF01 y RNF06 | ✅ |
| El ADR de base de datos considera la concurrencia de RNF02 y la validación de cupos de RF04 | ✅ |
| Las decisiones no contradicen la arquitectura del Modelo C4 | ✅ |

### 2.5 Documentación complementaria 

| Verificación | Estado |
|---|---|
| El glosario cubre los términos usados en la Fase I y en el avance #2 | ✅ |
| El FAQ responde solo con funcionalidades definidas en RF/HU (sin inventar alcance) | ✅ |
| Las convenciones fijan la numeración heredada de la Fase I (RF, RNF, HU, CP) | ✅ |
| El índice del expediente refleja los entregables de los cinco integrantes | ✅ |

## 3. Inconsistencias detectadas

| # | Documento | Descripción de la inconsistencia | Gravedad | Estado |
|---|---|---|---|---|
| 1 | Fase I – Matriz de trazabilidad | RF06 (agregar/eliminar cursos en inclusiones) aparece relacionado con HU04 (consulta de horario); conceptualmente corresponde a HU02 (matrícula de cursos) | Media | ✅ Resuelto|
| 2 | Fase I – Historias de usuario | La numeración de las HU aparece como lista (1 – 5) en el texto, pero la matriz de trazabilidad usa HU01 – HU05. En el avance #2 se estandariza el formato HUxx. | Baja | ✅ Resuelta con las convenciones |


---
