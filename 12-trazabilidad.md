# Trazabilidad

Una fila por cada requisito de producto `RP-01` a `RP-18` de la [Entrega 1](./03-requisitos.md). Las historias y los identificadores CU/DSS/EST son los mismos en los documentos de la Entrega 2. El símbolo `-` significa que ese artefacto no se elaboró para el requisito, con justificación en Observaciones.

## Matriz de trazabilidad

| Requisito | Historia | Caso de uso | Secuencia | Estado | Clases del dominio |
|---|---|---|---|---|---|
| [RP-01](./03-requisitos.md) | HU-01 | CU-01 | DSS-01 | EST-01 | Aporte, VersionApunte, Estudiante |
| [RP-02](./03-requisitos.md) | HU-01 | CU-01 | DSS-01 | EST-01 | Aporte, VersionApunte |
| [RP-03](./03-requisitos.md) | HU-02 | CU-02 | - | EST-01 | Aporte, AsignacionRevision, Estudiante, ComunidadEstudiantil |
| [RP-04](./03-requisitos.md) | HU-03 | CU-03 | DSS-02 | EST-01 | RevisionAcademica, VersionApunte, Estudiante |
| [RP-05](./03-requisitos.md) | HU-04 | CU-04 | - | EST-01 | Aporte, VersionApunte, RevisionAcademica |
| [RP-06](./03-requisitos.md) | HU-03 | CU-03 | DSS-02 | EST-01 | VersionApunte, RevisionAcademica |
| [RP-07](./03-requisitos.md) | HU-05 | CU-05 | DSS-02 | EST-02 | Aporte, VersionApunte, Notificacion |
| [RP-08](./03-requisitos.md) | HU-06 | CU-06 | - | - | Aporte, VersionApunte, Carrera, Ramo, PeriodoAcademico, TemaUnidad |
| [RP-09](./03-requisitos.md) | HU-07 | CU-07 | - | EST-01 | VersionApunte, RevisionAcademica, Aporte |
| [RP-10](./03-requisitos.md) | HU-08 | CU-08 | - | EST-01 | VersionApunte |
| [RP-11](./03-requisitos.md) | HU-10 | CU-10 | - | - | AsignacionRevision, Estudiante, ComunidadEstudiantil |
| [RP-12](./03-requisitos.md) | HU-09 | CU-09 | - | - | ReporteError, VersionApunte, Estudiante |
| [RP-13](./03-requisitos.md) | HU-09, HU-11 | CU-09, CU-11 | - | EST-01 | ReporteError, VersionApunte, RevisionAcademica |
| [RP-14](./03-requisitos.md) | HU-04, HU-07, HU-11 | CU-04, CU-07, CU-11 | - | EST-01 | Aporte, VersionApunte, RevisionAcademica |
| [RP-15](./03-requisitos.md) | HU-06 | CU-06 | - | - | Aporte, VersionApunte, Ramo, TemaUnidad |
| [RP-16](./03-requisitos.md) | HU-01, HU-06, HU-08 | CU-01, CU-06, CU-08 | DSS-01 | EST-01 | Aporte, VersionApunte, Ramo |
| [RP-17](./03-requisitos.md) | HU-06 | CU-06 | - | - | Aporte, VersionApunte |
| [RP-18](./03-requisitos.md) | HU-03, HU-11 | CU-03, CU-11 | DSS-02 | EST-01 | Estudiante, RevisionAcademica, VersionApunte |

## Observaciones

| Requisito | Justificación / alcance |
|---|---|
| RP-03 | No hay DSS de asignación; EST-01 solo recoge entrada en revisión. |
| RP-04 | DSS-02 muestra únicamente decisiones finales, como disparador de notificación. |
| RP-05 | No hay DSS de reenvío; EST-01 finaliza versión reemplazada. |
| RP-06 | DSS-02 contiene publicación tras aprobación. |
| RP-08 | No hay DSS ni EST de consulta; los filtros se especifican en Gherkin. |
| RP-09 | No hay DSS de ficha; revisión vincula una versión en el dominio. |
| RP-10 | No hay DSS de descarga; EST-01 identifica publicada/retirada. |
| RP-11 | No hay DSS de vencimiento ni EST de recordatorios; se valida con Gherkin. |
| RP-12 | No hay DSS ni EST del reporte; está definido en Gherkin y dominio. |
| RP-13 | No hay DSS de mantenimiento; EST-01 modela retiro y sustitución. |
| RP-14 | No hay DSS específico de versionado; transición a nueva versión y composición en dominio. |
| RP-15 | Métrica de exactitud de búsqueda: se comprueba por pruebas, no por UML de estados. |
| RP-16 | Métrica de usabilidad: DSS-01 solo cubre aporte; resto por pruebas. |
| RP-17 | Métrica de tiempo: requiere medición de rendimiento. |
| RP-18 | Métrica de autorización: DSS-02 presupone a la comunidad estudiantil; el control requiere pruebas. |

## Coherencia con el TO-BE

- **C01-C02:** RP-01/RP-02 → HU-01 → CU-01 → DSS-01 → Aporte y VersionApunte (`P01`-`P04`).
- **C03/C05:** RP-04/RP-06/RP-07 → HU-03/HU-05 → CU-03/CU-05 → DSS-02 → RevisionAcademica, VersionApunte y Notificacion (`P06`, `P09`-`P11`).
- **C04:** RP-05/RP-14 → HU-04 → CU-04 → EST-01 (`P07`, `P08`, `P13`, `P14`).
- **C06-C08:** RP-08/RP-09/RP-10 → HU-06/HU-07/HU-08 → CU-06/CU-07/CU-08 → clases de clasificación y VersionApunte (`B01`-`B10`).
- **C09-C10:** RP-11/RP-12/RP-13 → HU-10/HU-09/HU-11 → CU-10/CU-09/CU-11 (`P12`, `E01`-`E11`).
- **Calidad:** RP-15/RP-16/RP-17/RP-18 son restricciones no funcionales que deben comprobarse con baterías de pruebas; los diagramas no demuestran por sí mismos su satisfacción.

## Notas de alcance

- `07-trazabilidad.md` corresponde a la **Entrega 1** y se mantiene intacto. Este documento `12-trazabilidad.md` complementa aquella matriz.
- `DSS-01` y `DSS-02` muestran almacenamiento y correo **propuestos**; son integraciones que el equipo debe confirmar.
- El apartado de proyecto `RY-xx` no se añade a esta matriz porque la plantilla pide una fila por requisito de producto `RP-xx`.
