# SIMU – Sistema Integral de Matrícula Universitaria

## 1. Descripción del proyecto

El **Sistema Integral de Matrícula Universitaria (SIMU)** es una solución web orientada a digitalizar y ordenar el proceso de matrícula universitaria. Su propósito es reducir problemas habituales del proceso manual o parcialmente digitalizado, como filas presenciales, errores de inscripción, sobrecupos, choques de horario y demoras en la validación de requisitos académicos.

El sistema contempla dos perfiles principales:

- **Estudiante:** registro, autenticación, consulta de oferta académica, selección y modificación de cursos, validación de prerrequisitos, cupos y horarios, y consulta/descarga del horario.
- **Administrador académico:** gestión de cursos y generación/exportación de reportes de matrícula.

El expediente de esta fase reúne la definición del proyecto, requisitos, trazabilidad, decisiones arquitectónicas, modelos UML y C4, documentación técnica, manuales, pruebas y material de presentación.

---

## 2. Antecedentes y continuidad entre fases

### Fase II

La Fase II estableció la base documental y arquitectónica del proyecto: organización del repositorio, documentación en Markdown, diagramas UML, Modelo C4, ADR y uso de Git/GitHub para trabajo colaborativo.

### Fase III

La Fase III consolida esa base en un expediente único y verificable. Se incorporan:

- descripción consolidada del proyecto;
- catálogo de requisitos funcionales y no funcionales;
- historias de usuario y criterios de aceptación;
- casos de prueba CP01–CP09;
- matriz de trazabilidad;
- bitácora de cambios y hallazgos;
- documentación técnica y manuales;
- revisión de calidad y preparación de la defensa.

---

## 3. Objetivo general

Consolidar y documentar el Sistema Integral de Matrícula Universitaria mediante un expediente organizado que permita comprender el problema, los requisitos, la arquitectura, las decisiones de diseño, la documentación técnica, las pruebas y el uso esperado del sistema.

## 4. Objetivos específicos

1. Mantener una definición coherente del problema, solución y alcance del SIMU.
2. Consolidar los requisitos funcionales y no funcionales sin alterar sus identificadores.
3. Mantener la trazabilidad entre requisitos, historias de usuario, casos de prueba y artefactos de diseño.
4. Documentar la arquitectura mediante UML, C4 y ADR.
5. Proporcionar documentación técnica y manuales adecuados para las distintas audiencias del proyecto.
6. Definir y documentar los casos de prueba de la Fase III.
7. Revisar la consistencia final del expediente y preparar la defensa técnica.

---

## 5. Alcance del sistema

### 5.1 Dentro del alcance

| Área | Funcionalidad | Requisitos |
|---|---|---|
| Acceso | Registro y autenticación de estudiantes | RF01 |
| Oferta académica | Consulta de cursos por carrera y período | RF02 |
| Matrícula | Validación de prerrequisitos, cupos y choques de horario | RF03, RF04, RF05 |
| Inclusiones | Agregar o eliminar cursos durante el período permitido | RF06 |
| Administración | Crear, modificar y eliminar cursos según las reglas del sistema | RF07 |
| Horario | Consultar y descargar el horario matriculado | RF08 |
| Reportes | Generar y exportar reportes de matrícula | RF09 |

### 5.2 Fuera del alcance

- Gestión de pagos, aranceles o becas.
- Expediente académico histórico, calificaciones y promedios.
- Integración con otros sistemas institucionales externos.
- Aplicación móvil nativa.
- Mensajería institucional o notificaciones push.

---

## 6. Requisitos principales

### Requisitos funcionales

- **RF01:** Inicio de sesión.
- **RF02:** Oferta de cursos.
- **RF03:** Validación de prerrequisitos.
- **RF04:** Disponibilidad de cupos.
- **RF05:** Conflictos de horario.
- **RF06:** Agregar o eliminar cursos.
- **RF07:** Gestión de cursos.
- **RF08:** Consulta y descarga de horario.
- **RF09:** Reportes de matrícula.

### Requisitos no funcionales

- **RNF01:** Respuesta de matrícula menor a 3 segundos.
- **RNF02:** Soporte de al menos 2 000 usuarios concurrentes.
- **RNF03:** Disponibilidad del 99,5 % durante el período de matrícula.
- **RNF04:** Protección de contraseñas mediante hash y uso de HTTPS/TLS.
- **RNF05:** Usabilidad suficiente para que un estudiante nuevo complete la matrícula sin capacitación previa.
- **RNF06:** Operación en las dos últimas versiones de Chrome, Edge y Firefox.

---

## 7. Arquitectura y decisiones técnicas

El expediente documenta una arquitectura de **monolito modular en capas** y mantiene decisiones arquitectónicas mediante ADR.

| Elemento | Decisión registrada |
|---|---|
| Arquitectura | Monolito modular en capas |
| Lenguaje | Java |
| Backend | Spring Boot / Spring Security / Maven |
| Base de datos | **MYSQL, según ADR-004** |
| Interfaz | Thymeleaf, HTML, CSS, JavaScript y Bootstrap, según ADR-005 |
| Seguridad | BCrypt, HTTPS/TLS, roles y expiración de sesión, según ADR-006 |

---

## 8. Estructura del expediente

```text
SIMU/
├── README.md
├── Documentacion_Tecnica.md
└── docs/
    ├── 00-indice-expediente-final.md
    ├── 01-descripcion-del-proyecto.md
    ├── 02-requisitos.md
    ├── 03-matriz-trazabilidad.md
    ├── 04-bitacora-de-cambios.md
    ├── adr/
    ├── arquitectura/
    ├── diagramas/
    ├── tecnica/
    ├── manuales/
    ├── calidad/
    ├── complementaria/
    └── fase-1/
```

### Distribución de responsabilidades – Fase III

| Integrante | Responsabilidad | Documentos principales |
|---|---|---|
| **Integrante 1** | Gestión del proyecto | README, índice, descripción, requisitos, trazabilidad y bitácora |
| **Integrante 2** | Diseño y arquitectura | UML, arquitectura/C4 y ADR |
| **Integrante 3** | Documentación técnica | Documentación técnica, API, estructura, instalación y mantenimiento |
| **Integrante 4** | Calidad y presentación | Pruebas, evidencias, manual de usuario, reflexión sobre IA, revisión y presentación |

---

## 9. Herramientas de documentación

- Git y GitHub para control de versiones.
- Visual Studio Code para edición.
- Markdown para documentación.
- PlantUML para diagramas UML y C4.
- Mermaid cuando corresponda a material de apoyo.
- Navegador web para revisión del expediente y visualización de documentación.

---

## 10. Requisitos para trabajar con el expediente

Para editar y revisar el expediente se recomienda:

- Git instalado.
- Visual Studio Code.
- Extensión de Markdown.
- Extensión de PlantUML para visualizar `.pu`.
- Navegador web actualizado.

La documentación técnica del sistema contiene los requisitos adicionales asociados al entorno de ejecución cuando corresponda.

---

## 11. Equipo

- Steven Canales Obando
- Leonela Quesada Rivera
- Jeferson Castro Chavarría
- José David Zeledón Martínez
