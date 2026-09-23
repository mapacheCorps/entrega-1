# Atributos de calidad ISO 25010

## Modelo utilizado

Se utiliza **ISO/IEC 25010:2023**, cuyo modelo de calidad del producto tiene nueve características de primer nivel. Se conserva el nombre inglés para distinguir términos cuya traducción varía, especialmente Security y Safety. [Referencia oficial de ISO](https://www.iso.org/standard/78176.html).

La priorización y las metas corresponden al criterio D08 de la propuesta. La calidad del software se distingue de la corrección académica de los apuntes: el funcionamiento correcto del buscador no sustituye la revisión del contenido.

## Priorización de los nueve atributos

| Prioridad | Atributo | Justificación para Torpedos |
|---|---|---|
| 1 | Adecuación funcional — Functional suitability | La clasificación, búsqueda, revisión y publicación deben satisfacer las tareas del estudiante y la comunidad. |
| 2 | Capacidad de interacción — Interaction capability | Los estudiantes deben poder aportar y obtener material con instrucciones comprensibles y poca asistencia. |
| 3 | Eficiencia de desempeño — Performance efficiency | La rapidez al buscar responde directamente al objetivo de acceso oportuno al material. |
| 4 | Seguridad de la información — Security | Las decisiones de revisión y publicación deben estar protegidas frente a cambios no autorizados; RP-18 concreta una condición inicial. |
| 5 | Fiabilidad — Reliability | Deben conservarse aportes, revisiones e historial y mantenerse disponibles las operaciones esperadas. |
| 6 | Compatibilidad — Compatibility | El acceso desde entornos y navegadores utilizados por los estudiantes debe ser consistente. |
| 7 | Mantenibilidad — Maintainability | El equipo deberá corregir errores y adaptar reglas de clasificación y revisión. |
| 8 | Flexibilidad — Flexibility | La solución debería poder adaptarse a nuevos ramos, carreras y volumen de material. |
| 9 | Seguridad frente a daños — Safety | No se ha identificado un uso de control físico crítico en el alcance; esto no elimina la necesidad de evaluar posibles consecuencias del uso y aclarar el alcance de la revisión. |

## Métricas de los tres atributos principales

### M01 Adecuación funcional

- **Objetivo:** exactitud funcional de la búsqueda, no certificar el contenido de los apuntes.
- **Requisito y proceso:** RP-15; C06; B01, B03 y B04; HU-06.
- **Métrica:** consultas correctas / consultas ejecutadas × 100. Una consulta es correcta si el conjunto de identificadores devueltos coincide exactamente con el esperado.
- **Meta propuesta:** 100 % de 30 consultas controladas.
- **Método:** preparar un catálogo etiquetado y una lista esperada antes de ejecutar. Incluir coincidencias simples, filtros combinados, resultados vacíos y versiones pendientes, rechazadas o retiradas que no deben aparecer como publicadas.
- **Registro:** consulta, datos del catálogo, resultados esperados, resultados obtenidos y cumplimiento. Ejecutar sobre una versión identificada del sistema cuando exista.

### M02 Capacidad de interacción

- **Objetivo:** comprobar que usuarios nuevos completen las tareas principales sin ayuda.
- **Requisito y proceso:** RP-16; C01, C06, C07 y C08; HU-01, HU-06 y HU-08.
- **Métrica:** tareas completadas correctamente sin ayuda y en ≤120 segundos / 20 tareas × 100.
- **Meta propuesta:** al menos 80 % (16 de 20).
- **Método:** 10 estudiantes nuevos realizan dos tareas cada uno: enviar un aporte con un archivo ya preparado y obtener un apunte existente especificado en el guion. Empezar en la pantalla inicial de la tarea; detener al confirmar el envío o recibir el archivo. El tiempo no incluye crear el apunte ni aprender la materia. No orientar durante la ejecución; errores, abandonos y solicitudes de ayuda cuentan como no cumplimiento.
- **Condiciones:** documentar dispositivo, navegador, familiaridad de los participantes y catálogo de prueba; garantizar previamente que el apunte solicitado existe.
- **Registro:** participante codificado, tarea, duración, éxito, ayuda solicitada y problemas observados.

### M03 Eficiencia de desempeño

- **Objetivo:** rapidez de respuesta del buscador bajo una carga declarada.
- **Requisito y proceso:** RP-17; C06; B02, B03, B04 y B10; HU-06.
- **Métrica:** percentil 95 de la duración desde enviar una consulta hasta visualizar sus resultados, en segundos.
- **Meta propuesta:** p95 ≤2 segundos.
- **Método:** ejecutar al menos 200 consultas con 10 usuarios concurrentes sobre 1000 fichas. Usar un conjunto fijo de consultas simples y combinadas. Para el percentil ordenar tiempos y tomar la posición techo(0,95 × n).
- **Condiciones:** registrar versión, servidor, navegador, red y política de caché. No excluir consultas lentas; registrar fallos por separado y no declarar éxito de la prueba si se pierden consultas. Se excluye la descarga de archivos porque mide otra operación.
