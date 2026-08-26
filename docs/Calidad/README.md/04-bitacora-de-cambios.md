# Bitácora de cambios y control de hallazgos – SIMU
---

## 1. Propósito

Esta bitácora registra los cambios realizados desde la Fase II hasta la consolidación de la Fase III, así como los hallazgos que todavía deben resolverse antes de la entrega definitiva.

La bitácora permite responder tres preguntas:

1. ¿Qué se cambió?
2. ¿Por qué se cambió?
3. ¿Qué queda pendiente?

---

## 2. Línea base de la Fase II

En la Fase II el proyecto ya contaba con una base documental orientada a la arquitectura y al diseño. Se encontraban definidos el repositorio, la documentación en Markdown, la organización de carpetas, los diagramas UML, el Modelo C4 y las decisiones arquitectónicas ADR, utilizando Git/GitHub como mecanismo de control de versiones.

La Fase II también estableció el nombre del proyecto, los cuatro integrantes y el enfoque general de documentación del SIMU.

---

## 3. Cambios realizados en la Fase III

| ID | Cambio realizado | Motivo | Responsable | Estado |
|---|---|---|---|---|
| CH-01 | Consolidación de un README único para el expediente final | Evitar dos README con información parcial o duplicada entre fases | Integrante 1 | Completado |
| CH-02 | Creación del índice consolidado del expediente | Definir una navegación única y responsabilidades por integrante | Integrante 1 | Completado |
| CH-03 | Consolidación de la descripción del proyecto | Integrar problema, solución, justificación, alcance, audiencias y actores | Integrante 1 | Completado |
| CH-04 | Consolidación del catálogo de requisitos | Reunir RF, RNF, HU y CP en un documento oficial | Integrante 1 |  Completado |
| CH-05 | Corrección de la relación RF06 → HU02 | Agregar/eliminar cursos es una operación de matrícula y no una consulta de horario | Integrante 1 |  Completado |
| CH-06 | Estandarización de identificadores HU01–HU05 y CP01–CP09 | Mantener referencias consistentes entre documentos | Integrante 1 |  Completado |
| CH-07 | Incorporación de criterios de verificación para RNF | Permitir que cada RNF indique cómo comprobarse | Integrante 1 |  Completado |
| CH-08 | Incorporación de reglas de negocio RN01–RN07 | Hacer explícitas reglas que antes estaban distribuidas entre RF y criterios de aceptación | Integrante 1 | Completado |
| CH-09 | Ampliación de la matriz de trazabilidad | Relacionar RF, HU, CP, UML, C4, ADR, documentación y API | Integrante 1 |  Completado |
| CH-10 | Creación de matriz inversa HU → RF → CP | Verificar que ninguna HU quede sin cobertura | Integrante 1 |  Completado |
| CH-11 | Incorporación de trazabilidad de RNF y ADR | Mejorar el control entre calidad y decisiones arquitectónicas | Integrante 1 / Integrante 2 | Documentado |
| CH-12 | Preparación de CP01–CP09 para la Fase III | Definir las pruebas y sus resultados esperados | Integrante 4 |  Documentado |
| CH-13 | Revisión y actualización del Manual de Usuario | Adaptar el manual a las funciones y validaciones documentadas en Fase III | Integrante 4 | Revisado |
| CH-14 | Incorporación de reflexión sobre uso responsable de IA | Cumplir la responsabilidad de calidad y presentación | Integrante 4 | Elaborado |
| CH-15 | Creación del checklist de revisión final | Controlar ortografía, enlaces, consistencia y presentación | Integrante 1 / Integrante 4 | Elaborado |

---

## 4. Cambios de organización documental

La estructura final del expediente se normaliza a:

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

```
---

## 5. Hallazgos y estado

Estados:

- **Resuelto:** corregido y verificado.
- **Parcial:** existe una solución documental, pero falta completar un artefacto o prueba.
- **Abierto:** requiere una corrección antes del cierre.

| ID | Hallazgo | Responsable | Estado | Acción de cierre |
|---|---|---|---|---|
| **H-01** | RF06 estaba relacionado con HU04 en la línea base anterior | Integrante 1 |  Resuelto | RF06 ahora se trazó a HU02 y la justificación quedó registrada |
| **H-02** | Historias de usuario con numeración inconsistente | Integrante 1 |  Resuelto | Se normalizó a HU01–HU05 |
| **H-03** | Seguridad no representada explícitamente en C4/componentes pese a RNF04 y ADR-006 | Integrante 2 | Parcial | Agregar o identificar componentes de seguridad en el modelo C4/UML |
| **H-04** | Grupo y período/carrera no están modelados de forma consistente en el diagrama de clases | Integrante 2 |  Resuelto | Revisar modelo de datos y alinear clases, requisitos y ADR-004 |
| **H-05** | Falta justificación cuantitativa para RNF01–RNF03 | Integrantes 2 y 3 | Parcial | Documentar dimensionamiento, estrategia de concurrencia y disponibilidad |
| **H-06** | Docente aparece como audiencia/rol en arquitectura pero no tiene casos de uso modelados | Integrante 2 | Abierto | Agregar sus casos de uso o retirar el actor de la arquitectura si no forma parte del alcance |
| **H-07** | UML de componentes y C4 de componentes presentan contenido redundante con nombres distintos | Integrante 2 | Resuelto | Unificar responsabilidades o justificar la existencia de ambos niveles |
| **H-08** | El diagrama de despliegue indicaba varias bases de datos antes de existir una decisión única | Integrante 2 |  Corregido | como hallazgo; trasladado a H-10 para cierre definitivo | Alinear todo con la decisión final de ADR-004 |
| **H-09** | Estructuras de carpetas y nombres no seguían una única convención | Integrante 1 |  Resuelto documentalmente | Mantener una sola estructura oficial y aplicar la guía de convenciones |
| **H-10** | ADR-004 define PostgreSQL, mientras la documentación técnica menciona MySQL y el despliegue menciona SQL Server/MySQL | Integrantes 2 y 3 |  Resuelto | Elegir una única base de datos y actualizar README, ADR, documentación técnica y despliegue |
| **H-11** | ADR-007 está incompleto y no describe correctamente el uso de VS Code/Markdown | Integrante 2 |Resuelto | Completar la tabla y normalizar la descripción de herramientas |
---

## 6. Criterio de cierre de la bitácora

La bitácora se considera cerrada cuando todos los hallazgos críticos estén resueltos, la documentación técnica coincida con las decisiones arquitectónicas finales y la matriz de trazabilidad refleje el estado definitivo del expediente.

---