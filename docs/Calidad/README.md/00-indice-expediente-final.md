# Índice del expediente final y orden de exposición

**Proyecto:** SIMU – Sistema Integral de Matrícula Universitaria  
**Fase:** III – Consolidación del expediente final  
**Versión:** 2.0 · **Fecha:** 25/08/2026

---

## 1. Propósito del expediente

Este índice organiza todos los entregables del proyecto SIMU y define el orden recomendado para revisar y presentar el trabajo. La estructura se basa en la documentación de la Fase II y en la consolidación realizada durante la Fase III.

El expediente se organiza para que exista una secuencia lógica:

```text
Problema y alcance
        ↓
Requisitos
        ↓
Trazabilidad
        ↓
Diseño y arquitectura
        ↓
Documentación técnica
        ↓
Manuales
        ↓
Pruebas y calidad
        ↓
Presentación y defensa
```

---

## 2. Equipo y responsabilidades

| Integrante | Rol | Entregables principales |
|---|---|---|
| **Jeferson Castro Chavarría** | Integrante 1 – Gestión del proyecto | README, índice, descripción, requisitos, matriz de trazabilidad y bitácora |
| **José David Zeledón Martínez** | Integrante 2 – Diseño y arquitectura | 7 UML, arquitectura en capas, 5 vistas C4 y 7 ADR |
| **Steven Canales Obando** | Integrante 3 – Documentación técnica | Documentación técnica, API, estructura, instalación, configuración y mantenimiento |
| **Leonela Quesada Rivera** | Integrante 4 – Calidad y presentación | CP01–CP09, evidencias, manual de usuario, reflexión sobre IA, revisión final y presentación |

> La carpeta `docs/complementaria/` contiene documentos transversales. La carpeta `docs/fase-1/` conserva la Fase I como referencia de origen.

---

## 3. Índice de documentos

### 3.1 Gestión del proyecto – Integrante 1

| Documento | Contenido | Responsable |
|---|---|---|
| [`README.md`](../README.md) | Descripción general, objetivos, alcance, tecnologías, estructura y navegación | Integrante 1 |
| [`01-descripcion-del-proyecto.md`](01-descripcion-del-proyecto.md) | Problema, solución, justificación, alcance, audiencias y actores | Integrante 1 |
| [`02-requisitos.md`](02-requisitos.md) | RF01–RF09, RNF01–RNF06, HU01–HU05, CP01–CP09 y reglas de negocio | Integrante 1 |
| [`03-matriz-trazabilidad.md`](03-matriz-trazabilidad.md) | Trazabilidad RF ↔ HU ↔ CP ↔ artefactos | Integrante 1 |
| [`04-bitacora-de-cambios.md`](04-bitacora-de-cambios.md) | Historial de cambios, correcciones y hallazgos | Integrante 1 |

### 3.2 Diseño y arquitectura – Integrante 2

| Carpeta | Contenido | Responsable |
|---|---|---|
| [`diagramas/`](diagramas/) | 7 diagramas UML en PlantUML | Integrante 2 |
| [`arquitectura/`](arquitectura/) | Arquitectura en capas y 5 vistas C4 | Integrante 2 |
| [`adr/`](adr/) | 7 decisiones arquitectónicas ADR-001 a ADR-007 | Integrante 2 |

### 3.3 Documentación técnica – Integrante 3

| Documento | Contenido | Responsable |
|---|---|---|
| [`tecnica/documentacion-tecnica.md`](tecnica/documentacion-tecnica.md) | Arquitectura técnica, configuración, API, mantenimiento y pruebas técnicas | Integrante 3 |
| [`manuales/manual-tecnico.md`](manuales/manual-tecnico.md) | Instalación, configuración, uso técnico y mantenimiento | Integrante 3 |
| `Documentacion_Tecnica.md` | Versión ubicada en la raíz para consulta rápida; debe mantenerse alineada con la documentación técnica oficial | Integrante 3 |

### 3.4 Calidad y presentación – Integrante 4

| Documento | Contenido | Responsable |
|---|---|---|
| [`manuales/manual-de-usuario.md`](manuales/manual-de-usuario.md) | Uso para estudiantes y administradores | Integrante 4 |
| [`calidad/pruebas/pruebas.md`](calidad/pruebas/pruebas.md) | CP01–CP09, pasos, resultados esperados y evidencias | Integrante 4 |
| [`calidad/ia/reflexion-uso-ia.md`](calidad/ia/reflexion-uso-ia.md) | Uso responsable de IA | Integrante 4 |
| [`calidad/revision-final.md`](calidad/revision-final.md) | Checklist de consistencia y calidad | Integrante 4 |
| `calidad/presentacion/` | Diapositivas, guion y material de defensa | Integrante 4 |

### 3.5 Documentación complementaria

| Documento | Propósito |
|---|---|
| [`complementaria/01-glosario.md`](complementaria/01-glosario.md) | Definición de términos relevantes del proyecto |
| [`complementaria/02-preguntas-frecuentes.md`](complementaria/02-preguntas-frecuentes.md) | Preguntas y respuestas frecuentes |
| [`complementaria/03-convenciones-y-estilo.md`](complementaria/03-convenciones-y-estilo.md) | Normas de organización, nombres y formato |
| [`complementaria/04-matriz-consistencia-fase1.md`](complementaria/04-matriz-consistencia-fase1.md) | Control de consistencia con Fase I |
| [`complementaria/05-checklist-revision.md`](complementaria/05-checklist-revision.md) | Lista de verificación general |
| [`complementaria/06-referencias.md`](complementaria/06-referencias.md) | Referencias bibliográficas y fuentes |

### 3.6 Fase I

| Documento | Propósito |
|---|---|
| [`fase-1/fase-1-simu.pdf`](fase-1/fase-1-simu.pdf) | Documento original de referencia para requisitos y alcance |

---

## 4. Estado general de los entregables

| Área | Estado | Observación |
|---|---|---|
| Gestión del proyecto | 🟢 Documentada | README, índice, descripción, requisitos, trazabilidad y bitácora preparados |
| UML y arquitectura | 🟡 En revisión | Existen los artefactos; deben cerrarse inconsistencias entre modelo y requisitos |
| ADR | 🟡 En revisión | Existe el conjunto ADR-001–ADR-007; debe cerrarse la contradicción tecnológica y completar ADR-007 |
| Documentación técnica | 🟡 En revisión | Existe documentación amplia; debe alinearse con las decisiones arquitectónicas finales |
| Manual de usuario | 🟢 Revisado | Manual actualizado para Fase III |
| Pruebas | 🟡 Documentadas | CP01–CP09 definidos; la ejecución y evidencias reales quedan pendientes hasta disponer del entorno de prueba |
| Reflexión sobre IA | 🟢 Elaborada | Lista para integrarse en el expediente |
| Presentación | 🟡 Pendiente | Se prepara después del cierre de inconsistencias principales |

---

## 5. Orden recomendado de revisión del expediente

1. Leer este índice.
2. Revisar `README.md`.
3. Revisar la descripción del proyecto.
4. Revisar requisitos y reglas de negocio.
5. Revisar la matriz de trazabilidad.
6. Revisar UML, C4 y ADR.
7. Revisar documentación técnica y manual técnico.
8. Revisar manual de usuario.
9. Revisar pruebas y evidencias.
10. Revisar bitácora y checklist final.
11. Confirmar que las decisiones tecnológicas sean coherentes en todo el expediente.

---

## 6. Orden de exposición para la defensa técnica

La exposición oral se recomienda en el siguiente orden:

### Diapositiva 1 – Portada

- Nombre del proyecto.
- Curso.
- Docente.
- Integrantes.

### Diapositiva 2 – Problema

Explicar los problemas que motivan SIMU: filas, errores de inscripción, choques de horario, sobrecupos y demoras en la validación de requisitos.

### Diapositiva 3 – Solución y objetivos

Explicar qué resuelve SIMU y cuáles son sus objetivos principales.

### Diapositiva 4 – Alcance

Mostrar qué funcionalidades están dentro y fuera del proyecto.

### Diapositiva 5 – Requisitos

Presentar RF01–RF09 y los principales RNF.

### Diapositiva 6 – Arquitectura

Explicar monolito modular en capas, Modelo C4 y principales decisiones ADR.

### Diapositiva 7 – UML y flujo de matrícula

Mostrar casos de uso, clases/secuencia y el flujo:

```text
Inicio de sesión
      ↓
Oferta académica
      ↓
Selección de cursos
      ↓
Validación de prerrequisitos
      ↓
Validación de cupos
      ↓
Validación de horario
      ↓
Confirmación de matrícula
      ↓
Consulta/descarga de horario
```

### Diapositiva 8 – Documentación técnica

Explicar tecnologías, estructura, API, instalación y mantenimiento.

### Diapositiva 9 – Calidad y pruebas

Presentar CP01–CP09 y las evidencias reales disponibles.

### Diapositiva 10 – Uso responsable de IA

Explicar cómo se utilizó IA como apoyo y cómo se verificó la información.

### Diapositiva 11 – Hallazgos y mejoras

Explicar qué inconsistencias fueron detectadas y cómo se resolvieron.

### Diapositiva 12 – Conclusión

Resumir los aportes del proyecto y los principales aprendizajes.

---

## 7. Criterio de cierre

El expediente se considera listo para entrega cuando:

- los cuatro integrantes hayan completado sus responsabilidades;
- los requisitos y artefactos mantengan los mismos identificadores;
- UML, C4 y ADR sean coherentes con los requisitos;
- la tecnología de base de datos e interfaz esté unificada en todos los documentos;
- la documentación técnica refleje las decisiones arquitectónicas finales;
- CP01–CP09 estén documentados y sus evidencias reales hayan sido incorporadas cuando corresponda;
- la bitácora refleje el estado final de los hallazgos;
- los enlaces internos y nombres de archivos funcionen correctamente;
- la presentación esté lista para la defensa.

---

*Documento de consolidación del expediente final y guía de presentación.*
