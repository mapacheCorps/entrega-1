# Clasificación de requisitos

Los requisitos se clasifican en producto y proyecto. Los requisitos de producto se distinguen en funcionales y no funcionales, y se vinculan a las actividades y criterios de la [propuesta TO-BE](./02-rediseno-to-be.md).

## Requisitos de producto

| ID | Requisito | Tipo | Actividad TO-BE | Cambio | Criterio |
|---|---|---|---|---|---|
| RP-01 | El sistema debe permitir enviar un aporte con archivo, procedencia declarada, carrera, ramo, período académico y tema o unidad. | Funcional | P01, P02, P03 | C01 | D03 |
| RP-02 | Antes de enviar a revisión, el sistema debe comprobar los campos obligatorios, que el archivo no esté vacío y que cumpla el formato y tamaño configurados; si falla, debe identificar el problema y solicitar corrección. La detección de duplicados exactos debe informar la coincidencia para resolverla sin atribuirle validez académica. | Funcional | P04, P07 | C02 | D04 |
| RP-03 | El sistema debe asignar cada aporte a un ayudante habilitado para el ramo y disponible; si no existe, debe mantenerlo pendiente de asignación y mostrarlo a coordinación, sin aprobarlo automáticamente. | Funcional | P05 | C02 | D02 |
| RP-04 | El sistema debe permitir al ayudante autorizado registrar aprobación, solicitud de corrección o rechazo, indicando versión, fecha, responsable, alcance y observaciones. | Funcional | P06, P10 | C03 | D01, D02 |
| RP-05 | El sistema debe entregar al autor las observaciones y permitirle enviar una versión corregida vinculada al mismo aporte, conservando el historial y remitiéndola nuevamente a validación y revisión. | Funcional | P07, P08, P13, P14 | C04 | D06 |
| RP-06 | El sistema debe publicar en el catálogo únicamente la versión aprobada. Un aporte pendiente, rechazado o en corrección no debe ofrecerse como publicado. | Funcional | P09 | C05 | D01 |
| RP-07 | El sistema debe informar al autor el resultado final del aporte, con enlace a la publicación cuando se apruebe y con motivo cuando se rechace. | Funcional | P11 | C05 | D01 |
| RP-08 | El sistema debe permitir buscar material publicado por carrera, ramo, período académico y tema o unidad; debe indicar cuando no existan coincidencias y permitir reformular la búsqueda. | Funcional | B01, B03, B04, B10 | C06 | D03 |
| RP-09 | La ficha del apunte debe mostrar procedencia declarada, ramo, período, versión, fecha, responsable y alcance de la revisión, sin presentar una validación técnica como garantía de corrección académica. | Funcional | B05 | C07 | D01, D02 |
| RP-10 | Al solicitar una descarga, el sistema debe comprobar que la versión siga publicada y disponible; debe entregar el archivo correspondiente o avisar que no está disponible y permitir volver a buscar. | Funcional | B06, B07, B08, B09 | C08 | D03 |
| RP-11 | Si una revisión supera el plazo configurado, el sistema debe enviar un recordatorio al ayudante y una alerta a coordinación, sin interrumpir la revisión ni aprobar o rechazar automáticamente. | Funcional | P12 | C09 | D05 |
| RP-12 | El sistema debe permitir reportar un posible error indicando apunte, versión y descripción; debe registrar el caso y asignar un revisor competente. | Funcional | E01, E02, E03 | C10 | D07 |
| RP-13 | El sistema debe permitir investigar un reporte, registrar si se confirma el error y comunicar la resolución. Si se confirma, debe marcar la versión en revisión y publicar una nueva versión revisada o retirar la afectada cuando no pueda corregirse, conservando el historial. | Funcional | E04, E05, E06, E07, E08, E09, E10, E11 | C10 | D07 |
| RP-14 | Cada revisión debe quedar vinculada al identificador de una versión concreta. Una modificación del contenido debe crear una nueva versión cuya aprobación no se herede automáticamente de la anterior. | Funcional derivado | P06, P08, P09, B05, E07 | C03, C04, C05, C07, C10 | D01, D06 |
| RP-15 | La búsqueda debe devolver exactamente los identificadores esperados en el 100 % de una batería acordada de 30 consultas sobre un catálogo controlado, incluyendo filtros combinados, ausencia de resultados y exclusión de versiones no publicadas. | No funcional | B01, B03, B04 | C06 | D08 |
| RP-16 | En una prueba propuesta con 10 estudiantes nuevos y dos tareas por persona (enviar un aporte completo y obtener un apunte existente), al menos 16 de las 20 tareas deben completarse sin ayuda en un máximo de 120 segundos cada una. | No funcional | P01, P02, P03, B01, B05, B06, B09 | C01, C06, C07, C08 | D08 |
| RP-17 | Con un catálogo de 1000 fichas y 10 usuarios concurrentes, el percentil 95 del tiempo entre enviar una búsqueda y visualizar sus resultados debe ser como máximo 2 segundos, en una prueba de al menos 200 consultas y un entorno documentado. Se excluye la transferencia de archivos. | No funcional | B02, B03, B04, B10 | C06 | D08 |
| RP-18 | Los controles de autorización deben impedir el 100 % de los 20 intentos negativos de una batería propuesta en que un estudiante sin rol habilitado intenta aprobar, rechazar, publicar o retirar material, sin modificar su estado. | No funcional | P06, P09, P10, E07, E08 | C03, C05, C10 | D02, D08 |

## Requisitos de proyecto

| ID | Requisito | Tipo | Fuente y verificación |
|---|---|---|---|
| RY-01 | Publicar la documentación de la entrega antes del 24 de septiembre de 2026 a las 10:00 AM. | Proyecto: plazo. | Pauta de Entrega 1, sección 2; comprobar publicación y última revisión. |
| RY-02 | Mantener los documentos Markdown en el repositorio de una organización, con integrantes y Project asociado. | Proyecto: organización y entrega. | Pauta, secciones 3 y 4; comprobar membresías, Project y enlaces. |
| RY-03 | Adjuntar los diagramas PNG y sus fuentes BPMN 2.0, con marcadores de tarea correctos, e índice IngReq-Entrega 1.md. | Proyecto: formato del entregable. | Pauta, sección 4; revisar archivos e imágenes en GitHub. |
| RY-04 | Documentar al menos dos técnicas de elicitación realmente utilizadas, con participantes, hallazgos y evidencia. | Proyecto: actividad y evidencia. | Pauta, ítem 5; verificar registros y evidencia. |
| RY-05 | Declarar por escrito al menos un entregable responsable por integrante y reservar la reunión dentro del plazo de la evaluación. | Proyecto: preparación de evaluación. | Especificación de Evaluación 1, secciones 3 y 4. |

## Requisito derivado

**Requisitos origen:** RP-04 exige registrar la revisión del contenido y RP-09 exige mostrar esa revisión al consultar el apunte.

**Requisito derivado:** RP-14, vincular la revisión a una versión concreta y no heredar automáticamente la aprobación al cambiar el contenido.

**Justificación:** si se reemplaza un archivo manteniendo una aprobación anterior sin identificar versión, la ficha podría atribuir al nuevo contenido una revisión que nunca recibió. Distinguir versiones es necesario para que la información solicitada por RP-04 y RP-09 sea coherente. Este requisito se deriva del análisis de RP-04 y RP-09.

**Ejemplo de comprobación:** aprobar versión 1; cargar versión 2; comprobar que la evidencia de versión 1 continúa en su historial y que versión 2 requiere una decisión propia antes de publicarse.
