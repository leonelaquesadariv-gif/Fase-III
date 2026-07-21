# Manual Técnico 
---

## Sistema Integral de Matricula Universitaria (SIMU)

---

# 1. Introducción
Este documento describe la arquitectura, herramientas y componentes técnicos utilizados en el desarrollo del Sistema Integral de Matricula Universitaria (SIMU). 

---

# 2. Objetivo
Proporcionar la información necesaria para que un desarrollador pueda comprender la estructura del proyecto y darle mantenimiento. 

--- 

# 3. Tecnologías utilizadas 
| Herramientas | Versión | Uso |
| -------------|---------|-------------|
| Git | 2.x | Control de versiones |
| GitHub | Web | Repositorio remoto |
| Visual Studio Code | Última | Editor de código |
| Markdown | 1.0 | Documentación |
| PlantUML | Última | Diagramas UML |

---

# 4. Arquitectura del sistema 
El sistema está organizado en tres capas principales:
- Capa de presentación: Interfaz gráfica donde interactúan estudiantes y administradores.
- Capa de lógica de negocios: Procesa las reglas del sistema, como validación de usuarios, prerrequisitos, cupos y horarios. 
- Capa de datos: Almacena la información de estudiantes, cursos, docentes, horarios y matrículas. 


---
# 5. Módulos del sistema 
El SIMU está compuesto por los siguientes módulos: 
### Autenticación
Permite el acceso seguro mediante usuarios y contraseñas. 
### Gestión de Matrícula 
- Consulta de cursos. 
- Validación de prerrequisitos.
- Verificación de cupos. 
- Detección de conflictos de horario. 
- Confirmación de matrícula. 
### Gestión Académica 
Permite el administrador crear, modificar y eliminar cursos, así como administrar horarios y cupos. 

---

# 6. Seguridad
El sistema implementa:
- Autenticación mediante usuario y contraseña. 
- Comunicación segura utilizando HTTPS.
- Control de acceso mediante roles (estudiante y administrador). 
- Validación de sesiones. 
- Protección de datos personales. 

# 7. Mantenimiento 
Se recomienda realizar las siguientes actividades de mantenimiento:
- Respaldo diario de las bases de datos. 
- Actualización periódica del servidor. 
- Revisar registros de errores para detectar incidencias.  
- Monitorear el rendimiento del sistema. 

# 8. Solución de problemas
| Problema | Posible solución |
| ---------|-------------------|
No es posible iniciar sesión | Verificar usuario y contraseña.
No aparecen cursos disponibles | Confirmar que el periodo de matrícula esté habilitado. 
Error al matrícular un curso | Revisar prerrequisitos, cupos y conflictos de horario. 
No se generan reportes | Verificar permisos del usuario administrador. 


---
# 9. Conclusión 
El Manual Técnico del Sistema Integral de Matrículas Universitarias (SIMU) proporciona una visión general de la estructura y funcionamiento del sistema, facilitando las labores de instalación, administración y mantenimeinto.