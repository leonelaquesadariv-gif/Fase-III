# Convenciones y guía de estilo de la documentación

**Proyecto:** SIMU – Sistema Integral de Matrícula Universitaria
**Documento:** Documentación complementaria – Convenciones y estilo
**Versión:** 1.0 · **Fecha:** 14/07/2026

Este documento establece las normas de formato, numeración, nomenclatura y referencias que todos los integrantes deben seguir al elaborar su parte del expediente. Su objetivo es que el conjunto final sea uniforme y consistente con la Fase I.

---

## 1. Idioma y redacción

- Toda la documentación se redacta en **español**, en tono formal e impersonal (evitar “yo hice”, preferir “se elaboró”).
- El nombre oficial del sistema es **“SIMU – Sistema Integral de Matrícula Universitaria”**. En la primera mención de cada documento se escribe completo; después puede usarse solo **SIMU**.
- Los términos técnicos en inglés (framework, hash, backend) se escriben en cursiva la primera vez y se definen en el [glosario](01-glosario.md).
- Revisar ortografía y acentuación antes de entregar (ver [checklist de revisión](05-checklist-revision.md)).

## 2. Formato de archivos

- Todos los documentos nuevos se escriben en **Markdown** (`.md`), codificación UTF-8.
- Nombres de archivo en **minúsculas, sin espacios ni tildes**, usando guiones: `modelo-c4.md`, `casos-de-uso.md`.
- Los documentos de la carpeta `docs/` llevan prefijo numérico de dos dígitos para mantener el orden: `01-glosario.md`, `02-preguntas-frecuentes.md`, etc.
- Los diagramas se elaboran con **PlantUML o Mermaid** y se incluyen como bloque de código dentro del `.md`, de manera que puedan versionarse en Git. Si se exporta una imagen, se guarda junto al documento con el mismo nombre base.

## 3. Estructura interna de cada documento

Todo documento del expediente debe iniciar con el siguiente encabezado:

```markdown
# Título del documento

**Proyecto:** SIMU – Sistema Integral de Matrícula Universitaria
**Documento:** <tipo de documento>
**Versión:** X.Y · **Fecha:** DD/MM/AAAA
```

- Un solo título de nivel 1 (`#`) por documento.
- Las secciones se numeran manualmente en el título de nivel 2: `## 1. Introducción`, `## 2. Alcance`…
- Las subsecciones usan nivel 3 sin numeración obligatoria.
- Las tablas deben tener fila de encabezado y una breve introducción en prosa antes de la tabla.

## 4. Identificadores y numeración (deben coincidir con la Fase I)

| Elemento | Formato | Rango definido en la Fase I |
|---|---|---|
| Requisito funcional | `RFxx` | RF01 – RF09 |
| Requisito no funcional | `RNFxx` | RNF01 – RNF06 |
| Historia de usuario | `HUxx` | HU01 – HU05 |
| Caso de prueba | `CPxx` | CP01 – CP09 |
| Decisión arquitectónica | `ADR-xxx` | ADR-001 en adelante |
| Caso de uso (diagramas) | `CUxx` | Por definir por el Integrante 2 |

Reglas:

- **No renumerar** los identificadores de la Fase I. Si un nuevo artefacto necesita más elementos, se agregan al final del rango.
- Toda referencia a un requisito o historia se hace por su identificador (por ejemplo, “el diagrama de secuencia cubre RF03, RF04 y RF05”), nunca solo por su nombre.
- Los casos de uso del diagrama UML deben mapearse a las HU de la Fase I (por ejemplo, `CU02 – Matricular cursos ↔ HU02`).

## 5. Nomenclatura de los ADR

Cada ADR sigue el formato `adr-NNN-tema.md` y contiene, como mínimo: **Título, Estado (propuesta/aceptada/reemplazada), Contexto, Decisión, Alternativas consideradas y Consecuencias**. Las decisiones deben ser coherentes con los RNF de la Fase I (por ejemplo, la base de datos elegida debe soportar 2 000 usuarios concurrentes, RNF02).

## 6. Referencias y citas

- Las referencias bibliográficas se listan en [06-referencias.md](06-referencias.md) en formato **APA 7.ª edición**.
- Dentro de los documentos, las citas se hacen con el formato autor-año: (Sommerville, 2016).
- Los enlaces entre documentos del expediente se hacen con rutas relativas de Markdown: `[Glosario](../docs/01-glosario.md)`.
- Toda figura o tabla tomada de una fuente externa debe citar su origen.

## 7. Control de versiones (Git)

- Mensajes de commit en español, en modo imperativo y con un prefijo del área: `docs: agrega glosario`, `diagramas: corrige diagrama de clases`.
- No se sube al repositorio material ajeno al expediente (archivos temporales, borradores personales).
- Cada integrante trabaja su carpeta asignada; los cambios sobre documentos de otro integrante se coordinan antes de aplicarse.

## 8. Proceso de consolidación

1. Cada integrante entrega su documento siguiendo estas convenciones.
2. El Integrante 5 aplica el [checklist de revisión](05-checklist-revision.md) y la [matriz de consistencia](04-matriz-consistencia-fase1.md).
3. Las observaciones se devuelven al autor para corrección o se corrigen de forma coordinada.
4. El documento corregido se marca como **consolidado** en el [índice del expediente](00-indice-expediente-final.md).

---

*Documento elaborado por el Integrante 5 (Documentación técnica y revisión).*
