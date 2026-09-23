# Historias de usuario

Las historias corresponden a la propuesta TO-BE. Cada una identifica las actividades, cambios del proceso, requisitos y criterios de aceptación asociados.

## HU-01

Como **estudiante que aporta material**, quiero **adjuntar y clasificar mi apunte**, para **que la comunidad lo reciba con la información necesaria**.

**Actividades TO-BE:** P01–P04, P07.  
**Cambios AS-IS → TO-BE:** C01, C02.  
**Requisitos:** RP-01, RP-02, RP-16.

**Criterios de aceptación:**

- **HU-01-CA1:** Dado un archivo y todos los datos obligatorios válidos, al enviar se registra un aporte y pasa a validación.
- **HU-01-CA2:** Si falta un campo obligatorio o el archivo incumple una regla configurada, se identifica el problema y no se remite a revisión hasta corregirlo.
- **HU-01-CA3:** La coincidencia con un archivo idéntico se comunica para resolver el duplicado; no se presenta como aprobación académica.

## HU-02

Como **coordinador de la comunidad**, quiero **que cada aporte tenga un ayudante competente asignado**, para **evitar solicitudes sin responsable**.

**Actividades TO-BE:** P05.  
**Cambios AS-IS → TO-BE:** C02.  
**Requisitos:** RP-03.

**Criterios de aceptación:**

- **HU-02-CA1:** Si existe un ayudante habilitado para el ramo y disponible, el aporte queda asignado a uno de ellos.
- **HU-02-CA2:** Si no existe uno disponible, el aporte permanece pendiente de asignación y visible a coordinación.
- **HU-02-CA3:** La falta de ayudante no publica ni aprueba el material.

## HU-03

Como **ayudante habilitado**, quiero **registrar una decisión fundamentada sobre una versión del apunte**, para **publicar material con evidencia de revisión**.

**Actividades TO-BE:** P06, P09, P10.  
**Cambios AS-IS → TO-BE:** C03, C05.  
**Requisitos:** RP-04, RP-06, RP-18.

**Criterios de aceptación:**

- **HU-03-CA1:** La decisión registra responsable, fecha, versión, alcance y observaciones.
- **HU-03-CA2:** Solo una decisión de aprobación permite publicar esa versión; corrección o rechazo mantienen el aporte fuera del catálogo publicado.
- **HU-03-CA3:** Un estudiante sin rol habilitado no puede registrar una decisión de revisión ni cambiar el estado de publicación.

## HU-04

Como **autor de un aporte**, quiero **recibir observaciones y enviar una versión corregida**, para **resolver problemas sin perder el historial**.

**Actividades TO-BE:** P07, P08, P13, P14.  
**Cambios AS-IS → TO-BE:** C04.  
**Requisitos:** RP-05, RP-14.

**Criterios de aceptación:**

- **HU-04-CA1:** Una solicitud de corrección entrega observaciones específicas al autor.
- **HU-04-CA2:** El reenvío conserva el identificador del aporte y crea una versión distinguible de la anterior.
- **HU-04-CA3:** La nueva versión vuelve a validación y revisión y no hereda una aprobación anterior.

## HU-05

Como **autor de un aporte**, quiero **conocer la resolución de mi envío**, para **saber si se publicó o por qué fue rechazado**.

**Actividades TO-BE:** P11.  
**Cambios AS-IS → TO-BE:** C05.  
**Requisitos:** RP-07.

**Criterios de aceptación:**

- **HU-05-CA1:** La aprobación informa el resultado y un enlace al apunte publicado.
- **HU-05-CA2:** El rechazo informa el motivo registrado.
- **HU-05-CA3:** La notificación corresponde al mismo aporte y versión de la decisión.

## HU-06

Como **estudiante que busca material**, quiero **filtrar los apuntes publicados por ramo, período y tema**, para **encontrar material pertinente**.

**Actividades TO-BE:** B01–B04, B10.  
**Cambios AS-IS → TO-BE:** C06.  
**Requisitos:** RP-08, RP-15, RP-16, RP-17.

**Criterios de aceptación:**

- **HU-06-CA1:** Las coincidencias corresponden a los filtros aplicados y a versiones publicadas.
- **HU-06-CA2:** Si no hay coincidencias, se informa de forma explícita y se permite cambiar los filtros o terminar.
- **HU-06-CA3:** La batería controlada de 30 consultas debe cumplir RP-15 y la prueba de rendimiento debe cumplir RP-17.

## HU-07

Como **estudiante que consulta un apunte**, quiero **ver su procedencia y la revisión de la versión disponible**, para **valorar su pertinencia y confiabilidad**.

**Actividades TO-BE:** B05.  
**Cambios AS-IS → TO-BE:** C07.  
**Requisitos:** RP-09, RP-14.

**Criterios de aceptación:**

- **HU-07-CA1:** La ficha muestra procedencia declarada, período, versión, fecha, responsable y alcance de revisión.
- **HU-07-CA2:** La evidencia mostrada corresponde a la misma versión que se ofrece para descargar.
- **HU-07-CA3:** Una comprobación técnica del archivo no se etiqueta como revisión académica ni como garantía absoluta de corrección.

## HU-08

Como **estudiante que consulta material**, quiero **obtener el archivo que seleccioné**, para **utilizarlo para estudiar**.

**Actividades TO-BE:** B06–B09.  
**Cambios AS-IS → TO-BE:** C08.  
**Requisitos:** RP-10, RP-16.

**Criterios de aceptación:**

- **HU-08-CA1:** Si la versión sigue publicada y disponible, se entrega el archivo correspondiente.
- **HU-08-CA2:** Si fue retirada o ya no está disponible, se informa y se permite volver a la búsqueda.
- **HU-08-CA3:** No se entrega silenciosamente una versión diferente a la seleccionada.

## HU-09

Como **estudiante que detecta un posible error**, quiero **reportarlo y conocer su resolución**, para **ayudar a mantener la calidad del material**.

**Actividades TO-BE:** E01–E04, E09, E10, E11.  
**Cambios AS-IS → TO-BE:** C10.  
**Requisitos:** RP-12, RP-13.

**Criterios de aceptación:**

- **HU-09-CA1:** Un reporte incluye apunte, versión y descripción y queda registrado como caso.
- **HU-09-CA2:** Si falta información imprescindible, se solicita completarla antes de registrar el envío.
- **HU-09-CA3:** La resolución informa si se confirmó el error y qué acción se tomó; un reporte por sí solo no prueba que el contenido sea incorrecto.

## HU-10

Como **coordinador de la comunidad**, quiero **recibir una alerta de revisiones demoradas**, para **poder gestionar la carga de trabajo**.

**Actividades TO-BE:** P12.  
**Cambios AS-IS → TO-BE:** C09.  
**Requisitos:** RP-11.

**Criterios de aceptación:**

- **HU-10-CA1:** Al superarse el plazo configurado en una revisión en curso, se genera recordatorio al ayudante y alerta a coordinación.
- **HU-10-CA2:** La alerta no interrumpe la revisión ni cambia el resultado a aprobado o rechazado.
- **HU-10-CA3:** Con el plazo de 48 horas representado en el modelo, una revisión que supera ese tiempo genera el recordatorio y la alerta.

## HU-11

Como **moderador habilitado**, quiero **corregir o retirar una versión con errores confirmados**, para **evitar que continúe distribuyéndose material defectuoso**.

**Actividades TO-BE:** E04–E09.  
**Cambios AS-IS → TO-BE:** C10.  
**Requisitos:** RP-13, RP-14, RP-18.

**Criterios de aceptación:**

- **HU-11-CA1:** Un error confirmado deja constancia y marca la versión afectada en revisión.
- **HU-11-CA2:** Si el equipo puede corregirlo, la nueva versión se revisa antes de publicarse y conserva el historial.
- **HU-11-CA3:** Si no puede corregirlo, se retira la versión afectada y se registra el motivo.
- **HU-11-CA4:** La resolución se notifica; una persona sin autorización no puede publicar ni retirar versiones.
