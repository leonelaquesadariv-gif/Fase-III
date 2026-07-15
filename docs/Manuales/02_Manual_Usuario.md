# Preguntas frecuentes (FAQ)

**Proyecto:** SIMU – Sistema Integral de Matrícula Universitaria
**Documento:** Documentación complementaria – Preguntas frecuentes
**Versión:** 1.0 · **Fecha:** 14/07/2026

Este documento responde las dudas más comunes de las audiencias definidas en la Fase I. Las respuestas se basan en los requisitos funcionales (RF), los requisitos no funcionales (RNF) y las historias de usuario (HU) del proyecto.

---

## 1. Para estudiantes

**¿Cómo ingreso al sistema?**
Con su credencial institucional y contraseña. El sistema valida la identidad antes de permitir cualquier operación (RF01, HU01).

**¿Qué necesito para registrarme?**
Nombre, identificación, correo electrónico y contraseña. El sistema verifica que el correo no esté registrado previamente y confirma el registro con un mensaje (HU01).

**¿Cómo sé qué cursos puedo matricular?**
El sistema muestra la oferta de cursos disponibles según su carrera y el período académico vigente (RF02).

**¿Por qué el sistema rechazó la matrícula de un curso?**
Las causas más comunes son tres: no cumple los prerrequisitos del curso (RF03), el grupo ya no tiene cupos disponibles (RF04) o el curso choca de horario con otro que ya seleccionó (RF05). El sistema indica el motivo en cada caso.

**¿Puedo cambiar mis cursos después de matricular?**
Sí, durante el período de inclusiones puede agregar o eliminar cursos (RF06). Su horario se actualiza automáticamente después de cada cambio (HU04).

**¿Dónde veo mi horario?**
Después de iniciar sesión, en la sección de consulta de horario. Se muestran únicamente sus cursos matriculados, con nombre del curso, horario, aula y docente. Puede descargarlo o imprimirlo (RF08, HU04).

**¿Es seguro ingresar mis datos personales?**
Sí. Las contraseñas se almacenan cifradas mediante hash y todos los datos viajan protegidos con HTTPS/TLS (RNF04).

**¿El sistema es difícil de usar?**
No. Uno de los requisitos del proyecto es que un estudiante nuevo pueda completar su matrícula sin capacitación previa (RNF05).

## 2. Para administradores académicos y personal de registro

**¿Cómo gestiono la oferta de cursos?**
El módulo de gestión de cursos permite crear, modificar y eliminar registros académicos, indicando nombre, código, horario y cantidad de cupos (RF07, HU03).

**¿Puedo eliminar cualquier curso?**
No. Solo pueden eliminarse cursos que no tengan estudiantes matriculados (HU03).

**¿Cómo genero reportes de matrícula?**
Seleccionando el período académico deseado; el sistema muestra la cantidad de estudiantes matriculados por curso y el total de matrículas del período. Los reportes se exportan en PDF o Excel (RF09, HU05).

**¿Quién puede acceder a las funciones administrativas?**
Únicamente los usuarios con rol de administrador (HU03, HU05).

## 3. Para docentes y coordinadores

**¿Qué información puedo consultar?**
Los docentes pueden consultar las listas de estudiantes matriculados, los horarios asignados y los grupos activos de sus cursos. Los coordinadores pueden revisar la oferta académica, los cupos disponibles y el avance de la matrícula de su carrera (ver la sección “Audiencias” de la Fase I).

## 4. Para el equipo técnico y soporte

**¿Qué rendimiento debe garantizar el sistema?**
Responder cualquier solicitud de matrícula en menos de 3 segundos (RNF01) y soportar al menos 2 000 usuarios concurrentes el primer día de matrícula sin degradarse (RNF02).

**¿Qué disponibilidad se exige?**
99,5 % durante el período de matrícula (RNF03).

**¿En qué navegadores funciona el sistema?**
En Chrome, Edge y Firefox, en sus dos últimas versiones (RNF06).

**¿Dónde encuentro la documentación técnica?**
La arquitectura del sistema se documenta con el Modelo C4 (carpeta `arquitectura/`), las decisiones técnicas en los ADR (carpeta `adr/`) y los diagramas UML en la carpeta `diagramas/`. Ver el [índice del expediente](00-indice-expediente-final.md).

## 5. Sobre el proyecto y su documentación

**¿Qué problema resuelve el SIMU?**
Automatiza el proceso de matrícula universitaria para eliminar filas, errores de inscripción, conflictos de horario, sobrecupos y demoras en la validación de requisitos académicos (ver justificación de la Fase I).

**¿Dónde se define qué debe hacer el sistema?**
En la Fase I: nueve requisitos funcionales (RF01 – RF09), seis requisitos no funcionales (RNF01 – RNF06) y cinco historias de usuario con criterios de aceptación (HU01 – HU05).

**¿Cómo se verifica que los requisitos estén cubiertos?**
Mediante la matriz de trazabilidad de la Fase I, que relaciona cada requisito con su historia de usuario y su caso de prueba (CP01 – CP09).

---

*Documento elaborado por el Integrante 5 (Documentación técnica y revisión).*
