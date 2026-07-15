# ADR__003: Arquitectura del Sistema 
## Estado 
Aceptado 
## Contexto 
El Sistema Integral de Matrícula Universitaria (SIMU) requiere una arquitectura que facilite el mantenimiento, la escalabilidad y la organización del código. El sistema debe permitir administrar estudiantes, profesores, cursos y matrículas de manera eficiente. 
## Desición 
Se adopta una arquitectura de tres capas (Three-Tier Architecture):
- Capa de Presentación 
- Capa de Lógica de Negocio 
- Capa de Acceso a Datos 
## Justificación 
Esta arquitectura permite separar las responsabilidades de cada componente, facilitando el desarrollo colaborativo, el mantenimeinto y futuras ampliaciones del sistema. 
## Consecuencias
### Positivas
- Mayor organización del proyecto. 
- Código más fácil de mantener.
- Escalabilidad. 
- Reutilización de componentes. 
### Negativas 
- Mayor cantidad de archivos. 
- Requiere una buena organización del proyecto. 
