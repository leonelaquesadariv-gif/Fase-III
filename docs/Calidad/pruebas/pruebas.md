# Plan y evidencias de pruebas - SIMU
## 3. Casos de prueba 

### CP01 - Autenticación de usuario 

**Requisito relacionado:** RF01 - Inicio de sesión. 

### Objetivo
Verificar que el sistema permita el acceso a un estudiante utilizando credenciales válidas y que rechace credenciales inválidas. 

### Precondiciones
- Debe existir un usuario registrado.
- El usuario debe tener credenciales válidas.
- El sistema debe encontrarse disponible para realizar la prueba.

### Caso positivo
**Datos de entrada:**
- Usuario válido.
- Contraseña válida.

### Pasos:
1. Ingresar a la pantalla de inicio de sesión.
2. Escribir el usuario.
3. Escribir la contraseña.
4. Presionar el botón de inicio de sesión.
5. Verificar el acceso.

**Resultado esperado:** 
El sistema permite el ingreso del usuario y muestra las funciones correspondientes a su rol.

### Caso negativo
**Datos de entrada:**

- Usuario válido.
- Contraseña incorrecta.

**Pasos:**
1. Ingresar a la pantalla de inicio de sesión.
2. Escribir el usuario.
3. Escribir una contraseña incorrecta.
4. Presionar el botón de inicio de sesión.
5. Verificar el mensaje mostrado

**Resultado esperado:**
El sistema rechaza el acceso y muestra un mensaje de error.

**Resultado obtenido**
Aceptado 

### CP02 - Consulta de oferta académica 
### Requisito relacionado: RF02 – Oferta de cursos.
### Objetivo

Verificar que el sistema muestre los cursos correspondientes a la carrera y al período académico seleccionado.
### Precondiciones

- El usuario debe haber ingresado al sistema.
- Deben existir cursos registrados.
- Debe existir información de carreras y períodos académicos.

### Pasos

1. Ingresar al sistema.
2. Acceder a la sección de oferta académica.
3. Seleccionar una carrera.
4. Seleccionar un período académico.
5. Consultar la oferta disponible.
6. Revisar los cursos mostrados.

### Resultado esperado

El sistema muestra únicamente los cursos correspondientes a la carrera y al período seleccionados.

### Resultado obtenido
Aceptado

### CP03 - Validación de prerrequisitos 
### Requisito relacionado: RF03 – Validación de prerrequisitos.
### Objetivo

Verificar que el sistema impida matricular un curso cuando el estudiante no cumple los prerrequisitos establecidos.

### Precondiciones

- Debe existir un estudiante.
- Debe existir un curso con prerrequisitos.
- El estudiante no debe cumplir dichos prerrequisitos.

### Pasos

1. Ingresar como estudiante.
2. Consultar la oferta académica.
3. Seleccionar un curso que requiera prerrequisitos.
4. Intentar matricularlo.
5. Confirmar la operación.
### Resultado esperado

El sistema rechaza la matrícula y muestra un mensaje indicando que el estudiante no cumple los prerrequisitos.
### Resultado obtenido
Aceptado

### CP04 - Validación de cupos
### Requisito relacionado: RF04 – Control de cupos.
### Objetivo

Verificar que el sistema impida matricular un curso cuando no existen cupos disponibles.

### Precondiciones

- Debe existir un curso.
- El curso debe encontrarse sin cupos disponibles.

### Pasos

1. Ingresar al sistema.
2. Seleccionar un curso sin cupos.
3. Intentar realizar la matrícula.
4. Confirmar la operación.

### Resultado esperado

El sistema rechaza la solicitud y muestra que el curso no dispone de cupos.

### Resultado obtenido
Aceptado

### CP05 - Validación de choque de horario
### Requisito relacionado: RF05 – Control de conflictos de horario.
### Objetivo

Verificar que el sistema impida matricular simultáneamente dos cursos cuyos horarios se superponen.

### Precondiciones

* Deben existir al menos dos cursos.
* Los horarios de los cursos deben presentar un traslape.

### Pasos

1. Ingresar al sistema.
2. Seleccionar el primer curso.
3. Seleccionar un segundo curso con horario incompatible.
4. Intentar confirmar la matrícula.
5. Revisar el resultado.

### Resultado esperado

El sistema detecta el conflicto de horario e impide completar la matrícula incompatible.

### Resultado obtenido
Aceptado

### CP06 – Actualización del horario
### Requisito relacionado: F06 – Actualización del horario.
### Objetivo

Verificar que el horario del estudiante se actualice después de agregar o eliminar una matrícula.

### Precondiciones

* Debe existir un estudiante.
* Debe existir al menos un curso matriculado.

### Pasos
1. Consultar el horario actual.
2. Registrar una modificación en la matrícula.
3. Confirmar la operación.
4. Consultar nuevamente el horario.
5. Comparar la información anterior con la actual.

### Resultado esperado
El horario mostrado por el sistema refleja correctamente los cambios realizados en la matrícula.

### Resultado obtenido
Aceptado

### CP07 - Gestión de cursos 
### Requisito relacionado: RF07 – Administración de cursos.
### Objetivo

Verificar que el administrador pueda crear, modificar y eliminar cursos de acuerdo con las reglas establecidas.

### Precondiciones
* Debe existir un usuario con rol administrador.

### Crear
1. Ingresar como administrador.
2. Acceder a la gestión de cursos.
3. Seleccionar la opción para crear un curso.
4. Completar la información requerida.
5. Guardar.

### Resultado esperado:
El curso se crea correctamente.

### Modificar
1. Seleccionar un curso existente.
2. Modificar su información.
3. Guardar los cambios.

### Resultado esperado:
La información del curso se actualiza correctamente.

### Eliminar
1. Seleccionar un curso que pueda ser eliminado.
2. Ejecutar la opción de eliminación.
3. Confirmar la acción.

### Resultado esperado:
El curso se elimina de acuerdo con las reglas del sistema.

### Resultado obtenido
Aceptado

### CP08 – Descarga del horario
### Requisito relacionado: RF08 – Consulta y descarga de horario.
### Objetivo

Verificar que el estudiante pueda consultar y descargar su horario.

### Precondiciones
* Debe existir un estudiante.
* El estudiante debe tener cursos matriculados.

### Pasos
1. Ingresar como estudiante.
2. Acceder a la sección de horario.
3. Consultar el horario.
4. Seleccionar la opción de descarga.
5. Verificar el archivo generado.

### Resultado esperado
El sistema genera un horario descargable que contiene la información académica correspondiente al estudiante.

### Resultado obtenido
Aceptado

### CP09 – Exportación de reportes
### Requisito relacionado: RF09 – Generación y exportación de reportes.
### Objetivo

Verificar que el administrador pueda generar y exportar un reporte de matrícula para un período determinado.

### Precondiciones
* Debe existir un usuario administrador.
* Deben existir datos de matrícula.
* Debe existir un período académico consultable.

### Pasos
1. Ingresar como administrador.
2. Acceder a la sección de reportes.
3. Seleccionar el período académico.
4. Generar el reporte.
5. Exportar el reporte.
6. Verificar el archivo generado.

### Resultado esperado
El sistema genera correctamente el reporte correspondiente al período seleccionado y permite su exportación.

### Resultado obtenido
Aceptado

