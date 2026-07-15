# Glosario

**Proyecto:** SIMU – Sistema Integral de Matrícula Universitaria
**Documento:** Documentación complementaria – Glosario
**Versión:** 1.0 · **Fecha:** 14/07/2026

Este glosario define los términos del dominio académico y de la documentación técnica utilizados en el expediente del proyecto. Está dirigido a todas las audiencias identificadas en la Fase I, en especial a quienes no poseen formación técnica.

---

## 1. Términos del dominio (proceso de matrícula)

| Término | Definición |
|---|---|
| **Matrícula** | Proceso mediante el cual un estudiante se inscribe formalmente en uno o varios cursos de un período académico. |
| **Período académico** | Lapso en el que se imparten los cursos (en este proyecto, cuatrimestre). |
| **Oferta académica** | Conjunto de cursos, grupos y horarios disponibles para matrícula en un período determinado. |
| **Curso** | Asignatura o materia que forma parte de un plan de estudios, identificada con un código, nombre, horario y cantidad de cupos. |
| **Grupo** | Sección específica de un curso, con horario, aula y docente asignados. |
| **Cupo** | Cantidad máxima de estudiantes que pueden matricularse en un grupo. |
| **Sobrecupo** | Situación en la que un grupo supera la cantidad máxima de estudiantes permitida. |
| **Prerrequisito** | Curso o condición académica que el estudiante debe haber aprobado o cumplido antes de matricular otro curso. |
| **Choque de horario** | Conflicto que ocurre cuando dos cursos seleccionados se imparten total o parcialmente a la misma hora. |
| **Período de inclusiones** | Lapso posterior a la matrícula ordinaria en el que el estudiante puede agregar o eliminar cursos (ver RF06). |
| **Plan de estudios** | Conjunto ordenado de cursos y requisitos que conforman una carrera universitaria. |
| **Registro académico** | Unidad administrativa encargada de gestionar la matrícula, las actas y los expedientes de los estudiantes. |
| **Reporte de matrícula** | Documento generado por el sistema con información sobre estudiantes inscritos, cursos y demanda (ver RF09). |

## 2. Términos del sistema SIMU

| Término | Definición |
|---|---|
| **SIMU** | Sistema Integral de Matrícula Universitaria; nombre del sistema desarrollado en este proyecto. |
| **Autenticación** | Verificación de la identidad de un usuario mediante credencial y contraseña (ver RF01). |
| **Credencial** | Identificador único con el que el usuario accede al sistema (por ejemplo, carné o correo institucional). |
| **Rol** | Perfil de acceso que determina qué funciones puede usar cada usuario (estudiante, administrador, docente, etc.). |
| **Administrador académico** | Usuario con permisos para gestionar cursos, cupos, horarios y reportes (ver HU03 y HU05). |
| **Confirmación de matrícula** | Comprobante que genera el sistema al finalizar exitosamente la inscripción de cursos (ver HU02). |
| **Disponibilidad** | Porcentaje de tiempo en que el sistema se mantiene operativo; el SIMU exige 99,5 % durante el período de matrícula (ver RNF03). |
| **Usuarios concurrentes** | Cantidad de personas que utilizan el sistema al mismo tiempo; el SIMU debe soportar al menos 2 000 (ver RNF02). |
| **Hash** | Técnica criptográfica que transforma una contraseña en un valor irreversible para almacenarla de forma segura (ver RNF04). |
| **HTTPS/TLS** | Protocolos que cifran la comunicación entre el navegador del usuario y el sistema para proteger los datos personales (ver RNF04). |

## 3. Términos de documentación y análisis de software

| Término | Definición |
|---|---|
| **Requisito funcional (RF)** | Descripción de una función o comportamiento concreto que el sistema debe realizar. En este proyecto: RF01 – RF09. |
| **Requisito no funcional (RNF)** | Atributo de calidad o restricción sobre cómo debe comportarse el sistema. En este proyecto: RNF01 – RNF06. |
| **Historia de usuario (HU)** | Descripción breve de una necesidad desde la perspectiva del usuario, con el formato “Como… quiero… para…”. En este proyecto: HU01 – HU05. |
| **Criterio de aceptación** | Condición verificable que debe cumplirse para considerar completada una historia de usuario. |
| **Caso de prueba (CP)** | Escenario definido para verificar que un requisito se cumple. En este proyecto: CP01 – CP09. |
| **Matriz de trazabilidad** | Tabla que relaciona requisitos, historias de usuario y casos de prueba para asegurar cobertura completa. |
| **UML** | Unified Modeling Language; lenguaje estándar de modelado para representar el sistema mediante diagramas (casos de uso, clases, secuencia, actividades). |
| **Diagrama de casos de uso** | Diagrama UML que muestra las interacciones entre los actores y las funciones del sistema. |
| **Diagrama de clases** | Diagrama UML que representa la estructura estática del sistema: clases, atributos, métodos y relaciones. |
| **Diagrama de secuencia** | Diagrama UML que muestra el intercambio de mensajes entre objetos a lo largo del tiempo. |
| **Diagrama de actividades** | Diagrama UML que representa el flujo de un proceso, con decisiones y acciones. |
| **PlantUML / Mermaid** | Herramientas que generan diagramas a partir de texto, lo que facilita versionarlos junto con la documentación. |
| **Modelo C4** | Enfoque de documentación de arquitectura en cuatro niveles: Contexto, Contenedores, Componentes y Código. |
| **ADR** | Architecture Decision Record; documento breve que registra una decisión arquitectónica, su contexto, alternativas y consecuencias. |
| **Markdown** | Lenguaje de marcado ligero utilizado para escribir la documentación del proyecto en texto plano. |
| **Repositorio (Git)** | Espacio versionado donde se almacena y controla el historial de la documentación y del código del proyecto. |
| **README.md** | Documento inicial de un repositorio que describe el proyecto, su estructura y cómo utilizarlo. |
| **Expediente final** | Conjunto consolidado de todos los documentos del proyecto (Fase I, diagramas, arquitectura, ADR y documentación complementaria). |

---

*Documento elaborado por el Integrante 5 (Documentación técnica y revisión). Los términos marcados con referencias (RFxx, RNFxx, HUxx, CPxx) remiten a la Fase I del proyecto.*
