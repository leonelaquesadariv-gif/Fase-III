# Requisitos del sistema

## 1. Requisitos funcionales

Los requisitos funcionales describen **qué debe hacer el sistema**: las funciones, servicios y comportamientos concretos que debe permitir, calcular, generar o validar.

| ID | Nombre | Descripción | Actor | Prioridad |
|---|---|---|---|---|
| **RF01** | Inicio de sesión | El sistema debe permitir al estudiante autenticarse con su credencial correspondiente y contraseña. | Estudiante | Alta |
| **RF02** | Oferta de cursos | El sistema debe mostrar la oferta de cursos disponibles por carrera y período. | Estudiante | Alta |
| **RF03** | Validación de prerrequisitos | El sistema debe validar que el estudiante cumpla los prerrequisitos antes de matricular un curso. | Sistema | Alta |
| **RF04** | Disponibilidad de cupos | El sistema debe verificar la disponibilidad de cupos en tiempo real y rechazar la matrícula si el grupo está lleno. | Sistema | Alta |
| **RF05** | Inconvenientes de horario | El sistema debe detectar choques de horario entre los cursos seleccionados. | Sistema | Alta |
| **RF06** | Agregar o eliminar cursos | El sistema debe permitir al estudiante eliminar o agregar cursos durante el período de inclusiones. | Estudiante | Media |
| **RF07** | Gestión de cursos | El sistema debe permitir al administrador gestionar cursos mediante la creación, modificación y eliminación de registros académicos. | Administrador académico | Alta |
| **RF08** | Consulta y descarga de horario | El sistema debe permitir al estudiante consultar y descargar su horario matriculado en formato imprimible. | Estudiante | Media |
| **RF09** | Reportes de matrícula | El sistema debe permitir al administrador generar reportes de matrícula y exportarlos en formato PDF o Excel. | Administrador académico | Media |

## 2. Requisitos no funcionales

Los requisitos no funcionales describen **cómo debe comportarse el sistema**: atributos de calidad y restricciones. No agregan funciones nuevas, sino que definen la calidad con la que se ejecutan.

| ID | Categoría | Descripción | Criterio de verificación |
|---|---|---|---|
| **RNF01** | Rendimiento / eficiencia | El sistema debe responder a una solicitud de matrícula en menos de 3 segundos. | Medición del tiempo de respuesta del endpoint de matrícula bajo carga normal. |
| **RNF02** | Escalabilidad / capacidad | El sistema debe soportar al menos 2 000 usuarios concurrentes durante el primer día de matrícula sin degradarse. | Prueba de carga con 2 000 sesiones simultáneas verificando que se mantenga RNF01. |
| **RNF03** | Disponibilidad / fiabilidad | El sistema debe tener una disponibilidad del 99,5 % durante el período de matrícula. | Registro de tiempo fuera de servicio durante el período; máximo admisible aproximado de 3,6 horas al mes. |
| **RNF04** | Seguridad | Las contraseñas deben almacenarse cifradas mediante *hash* y los datos personales deben viajar bajo HTTPS/TLS. | Inspección de la base de datos (ninguna contraseña en texto plano) y verificación del certificado TLS. |
| **RNF05** | Usabilidad | Un estudiante nuevo debe poder completar su matrícula sin capacitación previa. | Prueba con usuarios sin entrenamiento previo que completen la matrícula sin asistencia. |
| **RNF06** | Mantenibilidad y portabilidad | El sistema debe operar en los navegadores Chrome, Edge y Firefox en sus dos últimas versiones. | Prueba funcional de la matrícula en las seis combinaciones de navegador y versión. |

## 3. Historias de usuario

### HU01 – Registro de estudiantes

> Como **estudiante**, quiero registrarme en el sistema de matrícula ingresando mis datos personales para poder acceder a los servicios de matrícula en línea.

**Criterios de aceptación**

- El sistema debe permitir ingresar nombre, identificación, correo electrónico y contraseña.
- Todos los campos obligatorios deben ser validados antes de guardar la información.
- El sistema debe verificar que el correo electrónico no esté registrado previamente.
- Una vez completado el registro, el sistema debe mostrar un mensaje de confirmación.
- El estudiante debe poder iniciar sesión con las credenciales registradas.

**Requisitos relacionados:** RF01 · **Caso de prueba:** CP01

---

### HU02 – Matrícula de cursos

> Como **estudiante**, quiero seleccionar y matricular los cursos disponibles para el período académico correspondiente, con el fin de inscribirme en las materias que necesito cursar.

**Criterios de aceptación**

- El sistema debe mostrar la lista de cursos disponibles.
- El estudiante debe poder seleccionar uno o varios cursos.
- El sistema debe verificar que existan cupos disponibles antes de realizar la matrícula.
- El sistema debe validar que no existan conflictos de horario entre los cursos seleccionados.
- Al finalizar la matrícula, el sistema debe generar una confirmación de los cursos inscritos.

**Requisitos relacionados:** RF02, RF03, RF04, RF05, RF06 · **Casos de prueba:** CP02, CP03, CP04, CP05, CP06

---

### HU03 – Gestión de cursos por parte del administrador

> Como **administrador académico**, quiero registrar, modificar y eliminar cursos en el sistema para mantener actualizada la oferta académica de cada período.

**Criterios de aceptación**

- El administrador debe poder crear nuevos cursos indicando nombre, código, horario y cantidad de cupos.
- El administrador debe poder modificar la información de un curso existente.
- El administrador debe poder eliminar cursos que no tengan estudiantes matriculados.
- El sistema debe guardar los cambios realizados y mostrar un mensaje de confirmación.
- Solo los usuarios con rol de administrador pueden acceder a esta funcionalidad.

**Requisitos relacionados:** RF07 · **Caso de prueba:** CP07

---

### HU04 – Consulta del horario matriculado

> Como **estudiante**, quiero consultar mi horario de clases en el sistema para conocer los cursos matriculados, sus horarios y las aulas asignadas.

**Criterios de aceptación**

- El estudiante debe poder acceder a su horario después de iniciar sesión.
- El sistema debe mostrar únicamente los cursos en los que el estudiante está matriculado.
- La información debe incluir nombre del curso, horario, aula y docente asignado.
- El horario debe actualizarse automáticamente cuando se agregue o elimine una matrícula.
- El estudiante debe poder descargar o imprimir su horario.

**Requisitos relacionados:** RF08 · **Caso de prueba:** CP08

---

### HU05 – Generación de reportes de matrícula

> Como **administrador académico**, quiero generar reportes de matrícula para obtener información sobre la cantidad de estudiantes inscritos y los cursos con mayor demanda.

**Criterios de aceptación**

- El administrador debe poder seleccionar el período académico del reporte.
- El sistema debe mostrar la cantidad de estudiantes matriculados por curso.
- El sistema debe mostrar el total de matrículas realizadas durante el período.
- El reporte debe poder exportarse en formato PDF o Excel.
- Solo los usuarios con permisos de administrador podrán generar reportes.

**Requisitos relacionados:** RF09 · **Caso de prueba:** CP09

## 4. Casos de prueba

| ID | Descripción | Requisito | Resultado esperado |
|---|---|---|---|
| **CP01** | Verificar autenticación correcta. | RF01 | El estudiante con credenciales válidas accede al sistema; con credenciales inválidas recibe un mensaje de error sin ingresar. |
| **CP02** | Mostrar cursos según carrera y período. | RF02 | La lista muestra únicamente los cursos de la carrera y el período seleccionados. |
| **CP03** | Rechazar matrícula si no cumple requisitos. | RF03 | El sistema impide la matrícula e indica cuál prerrequisito no se cumple. |
| **CP04** | No permitir matrícula cuando el grupo esté lleno. | RF04 | El sistema rechaza la matrícula e informa que no hay cupos disponibles. |
| **CP05** | Impedir matrícula con choque de horarios. | RF05 | El sistema detecta el traslape e impide confirmar la matrícula. |
| **CP06** | Actualizar el horario después de modificar la matrícula. | RF06 | El horario refleja el curso agregado o eliminado inmediatamente después del cambio. |
| **CP07** | Crear, modificar y eliminar cursos correctamente. | RF07 | Las tres operaciones se completan y el sistema muestra confirmación; un curso con estudiantes matriculados no puede eliminarse. |
| **CP08** | Descargar el horario en formato imprimible. | RF08 | Se genera un archivo imprimible con los cursos matriculados, horario, aula y docente. |
| **CP09** | Exportar reporte en PDF o Excel. | RF09 | Se descarga el reporte en el formato seleccionado con los datos del período elegido. |

## 5. Reglas de negocio derivadas

Reglas que el sistema debe aplicar y que se desprenden de los requisitos anteriores. Se documentan aquí para que el equipo de desarrollo las implemente de forma uniforme.

| ID | Regla | Origen |
|---|---|---|
| **RN01** | Un curso solo puede matricularse si el estudiante aprobó todos sus prerrequisitos. | RF03 |
| **RN02** | El cupo de un grupo se descuenta en la misma transacción en que se registra la matrícula, de modo que dos estudiantes no puedan ocupar el último cupo simultáneamente. |
| **RN03** | Dos cursos matriculados no pueden traslaparse en día y franja horaria. |
| **RN04** | Agregar o eliminar cursos solo es posible mientras el período de inclusiones esté abierto. | 
| **RN05** | Un curso con estudiantes matriculados no puede eliminarse. | 
| **RN06** | Las funciones de gestión de cursos y generación de reportes están restringidas al rol de administrador. | 
| **RN07** | Un correo electrónico no puede estar asociado a más de una cuenta de estudiante.

---