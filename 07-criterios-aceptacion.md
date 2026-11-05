# Criterios de aceptación (Gherkin)

Se especifican las once historias existentes en [Entrega 1](./04-historias-usuario.md). Los escenarios describen comportamientos del dominio; no prueban que el software esté implementado. Los servicios externos de almacenamiento/correo son propuestas de diseño.

## HU-01 - Enviar y clasificar un aporte
**Historia:** Como estudiante que aporta material, quiero adjuntar y clasificar mi apunte, para que la comunidad lo reciba con la información necesaria.

**Origen:** [HU-01 en Entrega 1](./04-historias-usuario.md#hu-01).

```gherkin
Característica: Recepción de aporte

  Escenario: Registro de aporte completo
    Dado existe un estudiante autor que aporta un archivo no vacío
    Y el archivo cumple el formato y tamaño configurados y se declara carrera, ramo, período académico, tema y procedencia
    Cuando el autor presenta el aporte
    Entonces el sistema registra el aporte y su primera versión
    Y la versión queda pendiente de asignación o revisión, sin publicarse

  Escenario: Datos de aporte inválidos
    Dado el autor presenta un aporte con datos obligatorios faltantes o archivo inválido
    Cuando el autor presenta el aporte
    Entonces se identifica la causa del incumplimiento
    Y no se remite la versión a revisión hasta corregirla

  Escenario: Archivo duplicado exacto
    Dado existe un archivo idéntico ya registrado
    Cuando el autor presenta el aporte
    Entonces se informa la coincidencia exacta
    Y la coincidencia no se interpreta como aprobación académica

```

## HU-02 - Asignar responsable de revisión
**Historia:** Como integrante de la comunidad estudiantil, quiero organizar las revisiones de aportes, para que ningún envío quede sin evaluación.

**Origen:** [HU-02 en Entrega 1](./04-historias-usuario.md#hu-02).

```gherkin
Característica: Asignación de revisiones

  Escenario: Estudiante de la comunidad disponible
    Dado existe un aporte pendiente de asignación
    Y existe un estudiante de la comunidad disponible para revisar el ramo
    Cuando la comunidad organiza su revisión
    Entonces el aporte queda asignado a un estudiante de la comunidad
    Y se conserva la identificación del responsable

  Escenario: Sin estudiantes revisores disponibles
    Dado existe un aporte pendiente de asignación
    Y no hay estudiantes de la comunidad disponibles para revisar el ramo
    Cuando la comunidad organiza su revisión
    Entonces el aporte permanece pendiente de asignación
    Y la comunidad puede conocer la falta de revisor sin aprobación automática

```

## HU-03: Registrar revisión comunitaria
**Historia:** Como integrante de la comunidad estudiantil, quiero registrar una decisión fundamentada sobre una versión, para aprobarla y publicarla o rechazarla con feedback.

**Origen:** [HU-03 en Entrega 1](./04-historias-usuario.md#hu-03).

```gherkin
Característica: Decisión de revisión académica

  Escenario: Aprobación de versión revisada
    Dado existe una versión pendiente de decisión con revisión realizada
    Y el estudiante designado representa a la comunidad en la revisión
    Cuando la comunidad registra la aprobación con observaciones
    Entonces queda asociada a la versión la fecha y la identidad del revisor
    Y esa versión aprobada se publica

  Escenario: Rechazo o solicitud de corrección
    Dado existe una versión en revisión
    Y el estudiante designado representa a la comunidad en la revisión
    Cuando la comunidad registra rechazo con retroalimentación concreta para el autor
    Entonces queda documentada la decisión sobre la versión
    Y la versión rechazada no se publica

  Escenario: Intento no autorizado
    Dado existe una versión pendiente de revisión
    Y el interesado no pertenece a la comunidad responsable de la revisión
    Cuando el interesado intenta registrar aprobación
    Entonces se rechaza la decisión por falta de autorización
    Y no cambia el estado de publicación

```

## HU-04 - Enviar una versión corregida
**Historia:** Como autor de un aporte, quiero recibir observaciones y enviar una versión corregida, para resolver problemas sin perder el historial.

**Origen:** [HU-04 en Entrega 1](./04-historias-usuario.md#hu-04).

```gherkin
Característica: Corrección del aporte

  Escenario: Nueva versión del mismo aporte
    Dado existe un aporte cuya versión fue rechazada con retroalimentación
    Y el autor puede consultar el motivo y las observaciones
    Cuando el autor envía una nueva versión corregida
    Entonces se crea una nueva versión ligada al identificador del aporte
    Y la nueva versión inicia validación y revisión sin heredar aprobaciones

  Escenario: Corrección inválida
    Dado existe un aporte con rechazo y retroalimentación
    Y el archivo corregido no cumple una regla de validación
    Cuando el autor presenta la nueva versión
    Entonces se informan los incumplimientos
    Y no se deriva a revisión el archivo inválido

```

## HU-05 - Conocer resolución del aporte
**Historia:** Como autor de un aporte, quiero conocer la resolución de mi envío, para saber si se publicó o por qué fue rechazado.

**Origen:** [HU-05 en Entrega 1](./04-historias-usuario.md#hu-05).

```gherkin
Característica: Comunicación de la resolución

  Escenario: Resolución aprobada
    Dado existe una decisión final aprobatoria de una versión concreta
    Y la versión aprobada fue publicada
    Cuando se registra la resolución final
    Entonces el autor puede conocer la aprobación y el enlace de publicación
    Y el aviso identifica el aporte y la versión

  Escenario: Resolución rechazada
    Dado existe una decisión final de rechazo con fundamento
    Cuando se registra la resolución final
    Entonces el autor puede conocer el rechazo y el feedback registrado por la comunidad
    Y el aviso identifica el aporte y la versión
    Y la versión rechazada permanece sin publicar

  Escenario: Servicio externo de avisos no disponible
    Dado existe una resolución final registrada
    Y el servicio externo de correo no puede aceptar el aviso
    Cuando se intenta comunicar la resolución
    Entonces la decisión final se conserva sin alteración
    Y el envío pendiente o fallido queda identificado para su seguimiento

```

## HU-06 - Buscar apuntes publicados
**Historia:** Como estudiante que busca material, quiero filtrar los apuntes publicados por ramo, período y tema, para encontrar material pertinente.

**Origen:** [HU-06 en Entrega 1](./04-historias-usuario.md#hu-06).

```gherkin
Característica: Búsqueda de material

  Escenario: Coincidencias pertinentes
    Dado existen versiones publicadas clasificadas por carrera, ramo, período y tema
    Cuando el estudiante solicita una búsqueda con filtros
    Entonces el sistema informa solo las versiones publicadas que cumplen los filtros
    Y los resultados permiten distinguir los apuntes

  Escenario: Búsqueda sin coincidencias
    Dado no existen versiones publicadas que cumplan los filtros solicitados
    Cuando el estudiante solicita una búsqueda con filtros
    Entonces el sistema informa que no hay coincidencias
    Y el estudiante puede reformular la búsqueda

```

## HU-07 - Consultar ficha de revisión
**Historia:** Como estudiante que consulta un apunte, quiero ver su procedencia y la revisión de la versión disponible, para valorar su pertinencia y confiabilidad.

**Origen:** [HU-07 en Entrega 1](./04-historias-usuario.md#hu-07).

```gherkin
Característica: Consulta de ficha de apunte

  Escenario: Información de revisión consistente
    Dado existe una versión publicada con revisión académica registrada
    Cuando el estudiante consulta la información del apunte
    Entonces se informa procedencia, período, número de versión, fecha, responsable y alcance de revisión
    Y la información corresponde a la versión ofrecida

  Escenario: Ausencia de certificación académica
    Dado existe un archivo que superó controles técnicos sin revisión académica
    Cuando el estudiante consulta la información del material
    Entonces el sistema no lo presenta como versión académicamente aprobada
    Y el control técnico no se afirma como garantía de corrección

```

## HU-08 - Obtener apunte
**Historia:** Como estudiante que consulta material, quiero obtener el archivo que seleccioné, para utilizarlo para estudiar.

**Origen:** [HU-08 en Entrega 1](./04-historias-usuario.md#hu-08).

```gherkin
Característica: Obtención de una versión

  Escenario: Versión publicada y disponible
    Dado existe una versión seleccionada que sigue publicada
    Y su archivo está disponible
    Cuando el estudiante solicita obtener esa versión
    Entonces se entrega el archivo que corresponde exactamente a la versión seleccionada
    Y no se sustituye silenciosamente por otra versión

  Escenario: Versión retirada o ausente
    Dado el estudiante seleccionó una versión no disponible o retirada
    Cuando el estudiante solicita obtener el archivo
    Entonces se informa la indisponibilidad de la versión
    Y el estudiante puede volver a buscar material

```

## HU-09 - Reportar posible error
**Historia:** Como estudiante que detecta un posible error, quiero reportarlo y conocer su resolución, para ayudar a mantener la calidad del material.

**Origen:** [HU-09 en Entrega 1](./04-historias-usuario.md#hu-09).

```gherkin
Característica: Reporte de errores

  Escenario: Registro de reporte completo
    Dado existe una versión de apunte identificable
    Y el estudiante describe un posible error de esa versión
    Cuando el estudiante presenta el reporte
    Entonces se registra el reporte vinculado a la versión
    Y el reporte queda disponible para revisión de la comunidad estudiantil sin considerar confirmado el error

  Escenario: Reporte incompleto
    Dado el estudiante omite identificar la versión o la descripción del error
    Cuando el estudiante presenta el reporte
    Entonces se informa qué dato imprescindible falta
    Y no se registra un reporte incompleto

  Escenario: Resolución de un reporte investigado
    Dado existe un reporte vinculado a una versión y con investigación concluida
    Y la comunidad estudiantil ha registrado si el error se confirmó o descartó
    Cuando se registra la resolución del reporte
    Entonces el estudiante que lo presentó puede conocer el resultado de la investigación
    Y se informa la acción tomada si el error fue confirmado

```

## HU-10 - Recibir alerta de demora
**Historia:** Como integrante de la comunidad estudiantil, quiero conocer revisiones demoradas, para organizar el trabajo pendiente.

**Origen:** [HU-10 en Entrega 1](./04-historias-usuario.md#hu-10).

```gherkin
Característica: Seguimiento de revisiones

  Escenario: Revisión supera el plazo
    Dado existe una revisión en curso cuyo tiempo supera 48 horas desde su inicio
    Cuando vence el plazo de seguimiento configurado
    Entonces se genera recordatorio para quien revisa y alerta a la comunidad estudiantil
    Y la revisión continúa en curso sin aprobación ni rechazo automáticos

  Escenario: Revisión aún dentro del plazo
    Dado existe una revisión en curso sin plazo excedido
    Cuando se evalúa el plazo de seguimiento
    Entonces no se genera una alerta de demora por ese evento
    Y el estado de revisión se conserva

```

## HU-11 - Corregir o retirar versión con error
**Historia:** Como integrante de la comunidad estudiantil, quiero coordinar la corrección o retirada de una versión con errores confirmados, para evitar distribuir material defectuoso.

**Origen:** [HU-11 en Entrega 1](./04-historias-usuario.md#hu-11).

```gherkin
Característica: Mantenimiento de versiones

  Escenario: Error confirmado corregible
    Dado existe una versión con error confirmado
    Y la comunidad estudiantil dispone de contenido corregido
    Cuando la comunidad gestiona la corrección
    Entonces se crea una versión distinta y se revisa antes de publicarse
    Y la versión afectada mantiene su historial

  Escenario: Error confirmado no corregible
    Dado existe una versión con error confirmado que no puede corregirse
    Cuando la comunidad estudiantil decide su retiro
    Entonces la versión queda retirada y se registra el motivo
    Y se informa la resolución sin seguir ofreciéndola como publicada

  Escenario: Intento de retiro no autorizado
    Dado existe una versión publicada
    Y una persona no pertenece a la comunidad responsable de retirarla
    Cuando la persona intenta retirar la versión
    Entonces el sistema rechaza la operación
    Y la versión conserva su estado

```

## Verificación pendiente de requisitos de calidad asociados

Los siguientes umbrales proceden de `03-requisitos.md` de la Entrega 1. Son **pruebas propuestas**, no resultados obtenidos ni evidencia de implementación. Los escenarios Gherkin anteriores cubren el comportamiento del negocio; estos criterios numéricos se verificarían por separado.

| Requisito | Historias vinculadas | Verificación exigida |
|---|---|---|
| RP-15 | HU-06 | Obtener exactamente los identificadores esperados en el **100 % de 30 consultas** sobre catálogo controlado, incluyendo filtros combinados, ausencia de resultados y exclusión de no publicados. |
| RP-16 | HU-01, HU-06, HU-08 | Con **10 estudiantes nuevos**, completar al menos **16 de 20 tareas** (enviar un aporte completo y obtener un apunte) sin ayuda en **120 segundos o menos por tarea**. |
| RP-17 | HU-06 | Con **1.000 apuntes**, **10 personas buscando simultáneamente** y al menos **200 búsquedas**, entregar resultados en **2 segundos o menos en al menos el 95 %**; documentar equipo y configuración, sin incluir descarga. |
| RP-18 | HU-03, HU-11 | Impedir el **100 % de 20 intentos no autorizados** de aprobar, rechazar, publicar o retirar material, conservando intacto el estado. |
