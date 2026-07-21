## ADR-006: Seguridad y control de acceso

**Estado:** Propuesto  
**Decisión:** Implementar autenticación, roles y protección de datos.

### Contexto

El sistema necesita inicio de sesión, almacenamiento seguro de contraseñas, uso de HTTPS y acceso restringido a las funciones administrativas.

### Decisión tomada

Se aplicarán las siguientes medidas:

- Contraseñas almacenadas mediante hash BCrypt.
- Comunicación bajo HTTPS/TLS.
- Sesiones con tiempo de expiración.
- Validación de todos los formularios.
- Roles de estudiante, docente y administrador.
- Registro de operaciones importantes.
- Acceso a reportes y gestión de cursos únicamente para administradores.

### Justificación

No todos los usuarios deben realizar las mismas acciones. Por ejemplo, un estudiante puede matricular cursos, pero no debería modificar la oferta académica.

### Consecuencias

La configuración y las pruebas serán más amplias, pero se reducirá el riesgo de accesos no autorizados o cambios incorrectos.

---