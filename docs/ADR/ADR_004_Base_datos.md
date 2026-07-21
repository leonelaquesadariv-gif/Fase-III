## ADR-004: Base de datos

**Estado:** Propuesto  
**Decisión:** Utilizar PostgreSQL.

### Contexto

El sistema manejará información relacionada entre sí, por ejemplo:

- Un estudiante puede matricular varios cursos.
- Un curso puede tener diferentes grupos.
- Cada grupo posee horario, docente y cantidad de cupos.
- Una matrícula pertenece a un estudiante y a un período académico.

### Decisión tomada

PostgreSQL será la base de datos relacional del sistema.

### Justificación

El modelo relacional se adapta a la información académica del SIMU. También se podrán establecer claves primarias, claves foráneas y restricciones para evitar registros incompletos o duplicados.

Para la matrícula se utilizarán transacciones, de manera que la inscripción y la reducción del cupo se completen juntas. Esto ayudará a evitar que dos estudiantes ocupen el último cupo al mismo tiempo.

### Alternativas consideradas

- **MySQL:** también podría funcionar, pero se seleccionó una sola tecnología para evitar duplicar configuraciones.
- **MongoDB:** se descartó porque la información del sistema posee muchas relaciones claramente definidas.

### Consecuencias

Será necesario diseñar correctamente las tablas, relaciones, índices y scripts de migración.

---