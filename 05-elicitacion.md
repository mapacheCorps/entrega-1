# Elicitación de requisitos

## Objetivo

Conocer cómo estudiantes universitarios buscan, comparten y evalúan apuntes de ramos anteriores, recoger su opinión sobre una plataforma web que organice este material y analizar la estructura actual de los repositorios informales que utilizan.

## Técnica 1: Entrevista semiestructurada

Se entrevistó a dos estudiantes que han necesitado y compartido apuntes, resúmenes y pruebas de asignaturas cursadas anteriormente.

- **Participantes:**
  - Felipe (Estudiante de 2do año, Ingeniería Civil en Informática).
  - Catalina (Estudiante de 3er año, Ingeniería Civil en Informática).
- **Fecha:** 22 de septiembre de 2026.
- **Modalidad:** Entrevista presencial.
- **Evidencias:** [Entrevista a Felipe](./evidencias/entrevista-estudiante-1.jpg) · [Entrevista a Catalina](./evidencias/entrevista-estudiante-2.jpg)

### Preguntas y respuestas obtenidas

**Pregunta 1: ¿Cómo consigues actualmente apuntes de un ramo?**
- **Felipe:** Pregunta en grupos de WhatsApp o Discord y revisa si algún compañero tiene un archivo guardado de semestres anteriores.
- **Catalina:** Busca en conversaciones antiguas de WhatsApp, pero principalmente utiliza carpetas de Google Drive compartidas por estudiantes de cursos superiores donde guardan PPTs, PDFs, controles y pruebas de semestres pasados para estudiar.
- **Hallazgo (ENT-01):** El material se distribuye de manera informal a través de mensajería (WhatsApp/Discord) o repositorios en la nube (Drive) heredados entre generaciones.

**Pregunta 2: ¿Qué problemas tienes al buscar esos apuntes?**
- **Felipe:** Muchas veces encuentra archivos sueltos en WhatsApp sin nombre claro y debe abrir varios documentos para saber a qué unidad corresponden.
- **Catalina:** Aunque el Drive agrupa un poco la información, a veces los archivos están desordenados, hay versiones repetidas o no se especifica de qué año o profesor es el material.
- **Hallazgo (ENT-02):** Falta una clasificación uniforme por carrera, ramo, período y tema o unidad que evite la duplicidad y confusión.

**Pregunta 3: ¿Cómo sabes si un apunte es confiable?**
- **Felipe:** Pregunta quién lo hizo o si alguien del curso lo usó y le fue bien.
- **Catalina:** Compara el contenido con las clases actuales, ya que en el Drive nadie certifica si una pauta de un control antiguo está 100% correcta.
- **Hallazgo (ENT-03):** Los estudiantes necesitan conocer la procedencia del archivo y tener un indicador de revisión/confiabilidad.

**Pregunta 4: ¿Qué te parecería una plataforma web para buscar y compartir apuntes?**
- **Felipe:** Le sería muy útil si puede filtrar por carrera, ramo y tema, y descargar sin pedir permiso a un administrador.
- **Catalina:** La usaría bastante si muestra una descripción del apunte, fecha, versión y, sobre todo, si centraliza lo que hoy está esparcido en distintos enlaces de Drive.
- **Hallazgo (ENT-04):** La plataforma debe centralizar el material ofreciendo búsqueda estructurada, ficha descriptiva y descarga directa.

**Pregunta 5: ¿Qué debería ocurrir cuando alguien sube un apunte?**
- **Felipe:** Se deberían solicitar los datos básicos del ramo y período antes de publicarlo.
- **Catalina:** El archivo debería ser revisado y, si tiene errores, pedir una corrección antes de liberarlo para evitar estudiar con información mala.
- **Hallazgo (ENT-05):** El flujo de publicación debe incluir clasificación obligatoria y una revisión académica previa.

**Pregunta 6: ¿Qué harías si encuentras un error en un apunte publicado?**
- **Felipe:** Avisaría del error indicando la página.
- **Catalina:** Esperaría que un administrador baje el archivo malo, lo corrija o notifique que hay una versión actualizada.
- **Hallazgo (ENT-06):** Es necesario un mecanismo de reportes y control de versiones transparente.

## Técnica 2: Revisión documental

Para complementar las entrevistas y entender cómo los estudiantes organizan sus repositorios informales actuales, se analizó una carpeta de Google Drive utilizada por estudiantes de la carrera.

- **Responsable:** Equipo del proyecto.
- **Fecha de consulta:** 22 de septiembre de 2026.
- **Fuente revisada:** Carpeta compartida de Google Drive genera por estudiantes.
- **Evidencia:** [Captura de estructura en Drive](./evidencias/revision-drive.png)

### Hallazgos de la revisión documental

- **DOC-01 (Estructura de carpetas):** Se observa que los estudiantes intentan clasificar el material dividiéndolo en carpetas por unidades (ej. "Unidad ... e redes", "Unidad ... e datos"). Sin embargo, esta nomenclatura es inconsistente y puede generar problemas si se mezcla material de distintos ramos o semestres en una misma raíz.
  *Consecuencia:* Confirma la necesidad de que la nueva plataforma aplique una taxonomía estricta (Carrera > Ramo > Período > Unidad).
- **DOC-02 (Falta de metadatos):** En las plataformas de almacenamiento en la nube estándar (como Drive), solo se ve el nombre del archivo o carpeta. No hay etiquetas de validación, año del apunte o autor explícito a simple vista.
  *Consecuencia:* Respalda fuertemente el requisito de una "Ficha del apunte" que muestre el estado de revisión, la versión y la procedencia.

## Acta de acuerdo

Al finalizar la sesión, se presentaron los hallazgos y las decisiones de diseño a los participantes para su confirmación.

- **Participantes:** Felipe y Catalina.
- **Fecha de confirmación:** 22 de septiembre de 2026.
- **Acuerdos confirmados por los participantes:**
  - Ambos concuerdan en que la estructura informal de WhatsApp y carpetas de Drive es insuficiente y apoyan la creación de un catálogo centralizado y filtrable.
  - Están de acuerdo con que la plataforma exija datos de clasificación (Ramo, Unidad, Período) al subir un archivo.
  - Validan la necesidad de que los apuntes pasen por una **revisión previa** antes de ser publicados, para asegurar la calidad de lo que estudian.
  - Concuerdan en que deben existir reportes y un control de versiones si se corrige un archivo.
- **Asuntos pendientes / Desacuerdos:** No se manifestaron desacuerdos con la propuesta TO-BE presentada.

## Relación con los modelos del proyecto (Efecto sobre el proyecto)

La elicitación mixta (entrevista + revisión documental) confirma los problemas del proceso [AS-IS](./01-proceso-as-is.md): dispersión en chats y nubes, nombres inconsistentes y falta de evaluación de calidad.

Asimismo, respalda las decisiones D01 a D08 integradas en el [TO-BE](./02-rediseno-to-be.md):
- **D01, D02, D04:** El formulario de subida estructurado y la validación/revisión previa antes de publicar.
- **D03:** La clasificación estricta (Carrera, Ramo, Período, Tema) supera el uso de carpetas sueltas.
- **D06, D07:** La gestión de reportes y la necesidad de versiones para actualizar apuntes erróneos.

Estos hallazgos se reflejan directamente en los [requisitos de producto](./03-requisitos.md) y en las [historias de usuario](./04-historias-usuario.md).
