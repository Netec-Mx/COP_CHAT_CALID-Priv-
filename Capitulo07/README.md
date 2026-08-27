# Práctica: Creación integral de una lista de verificación (checklist) para una auditoría interna de calidad.

## Metadatos

| Elemento | Valor |
|---|---|
| Duración | 60 minutos |
| Complejidad | Media |
| Nivel de Bloom | Crear |

## Descripción general

En este laboratorio transformarás el hallazgo crítico de torque documentado en el Laboratorio 06-00-01 en una lista de verificación reutilizable para una auditoría interna del proceso de liberación de producto. Analizarás el criterio incumplido, la condición observada, la evidencia faltante y los riesgos del caso para convertirlos en controles preventivos, detectivos y documentales.

Usarás Microsoft Word y Microsoft 365 Copilot para revisar el hallazgo, y Microsoft Excel con Copilot para proponer y organizar preguntas de auditoría. Toda propuesta generada por IA deberá ser validada contra el documento fuente y los criterios internos autorizados antes de incorporarse a la checklist.

## Objetivos de aprendizaje

Al finalizar el laboratorio, podrás:

- [ ] Convertir un hallazgo crítico de calidad en controles de auditoría verificables y trazables.
- [ ] Diseñar una checklist de auditoría interna para el proceso de liberación de producto.
- [ ] Formular preguntas abiertas de auditoría vinculadas con requisitos, evidencia objetiva y riesgos reales del caso de torque.
- [ ] Utilizar Microsoft 365 Copilot para proponer preguntas y revisar consistencia sin aceptar contenido no validado.
- [ ] Preparar preguntas de entrevista para responsables de liberación de producto, registros de calidad y acciones correctivas.

## Requisitos previos

### Conocimientos requeridos

Antes de comenzar, debes conocer los siguientes conceptos:

- Diferencia entre conformidad, no conformidad y oportunidad de mejora.
- Uso básico de evidencia objetiva, trazabilidad documental y muestreo de registros.
- Principios básicos de auditoría interna: criterio, condición, evidencia, hallazgo y acción de seguimiento.
- Uso básico de tablas en Microsoft Excel.
- Principio de validación humana: una salida de Copilot es un borrador de apoyo, no evidencia de auditoría ni decisión de calidad.

### Archivos y accesos requeridos

Confirma que dispones de lo siguiente:

- Archivo `L06_Hallazgo_Critico_v1.docx` en la carpeta compartida de trabajo.
- Correo ejecutivo generado en el Laboratorio 06-00-01, disponible en Outlook o guardado en la ubicación autorizada.
- Acceso activo a Microsoft Word, Excel, OneDrive for Business, SharePoint Online y Microsoft 365 Copilot.
- Permisos de edición en la biblioteca de SharePoint del curso.
- Acceso con la misma cuenta corporativa de Microsoft Entra ID utilizada en los laboratorios previos.

> **Importante:** No cargues documentos, capturas, datos de calidad, registros de producción ni información corporativa en herramientas externas de IA. Utiliza únicamente Microsoft 365 Copilot dentro del tenant corporativo autorizado.

## Entorno de laboratorio

### Hardware recomendado

| Componente | Requisito mínimo |
|---|---|
| Conectividad | Internet corporativo estable de al menos 10 Mbps de descarga y 5 Mbps de carga |
| Equipo | Intel Core i5 de 10.ª generación, AMD Ryzen 5 4000 Series o equivalente |
| Memoria | 8 GB de RAM como mínimo |
| Almacenamiento | 20 GB de espacio libre |
| Pantalla | Resolución mínima de 1920 x 1080 píxeles |

### Software y servicios

| Componente | Uso en el laboratorio |
|---|---|
| Microsoft Word con Copilot | Revisar y resumir el hallazgo crítico |
| Microsoft Excel con Copilot | Crear la checklist y proponer preguntas |
| OneDrive for Business | Sincronización de archivos corporativos |
| SharePoint Online | Ubicación oficial de almacenamiento |
| Microsoft Outlook | Consulta del correo ejecutivo del laboratorio anterior |
| Microsoft 365 Copilot | Apoyo controlado para análisis, redacción y revisión de consistencia |

### Ubicación de trabajo autorizada

Trabaja exclusivamente en la biblioteca sincronizada:

```text
/sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/
```

En equipos Windows, la ruta local esperada es:

```text
C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
```

### Preparación inicial

1. Abre el Explorador de archivos.
2. Navega a la carpeta sincronizada del lote `Batch_01_Calidad_Mejora_Continua`.
3. Verifica que el icono de OneDrive indique sincronización completada o que los archivos estén disponibles localmente.
4. Localiza el archivo `L06_Hallazgo_Critico_v1.docx`.
5. Localiza el correo ejecutivo creado o enviado durante el Laboratorio 06-00-01.
6. Crea un nuevo libro de Excel en la carpeta autorizada.
7. Guarda el archivo con el siguiente nombre:

```text
07_Checklist_Auditoria_Interna_Torque.xlsx
```

> **Nota de control documental:** No sobrescribas archivos fuente proporcionados por el instructor ni documentos creados en laboratorios previos.

## Procedimiento paso a paso

### Paso 1. Revisar el hallazgo crítico y definir el contexto de auditoría

**Objetivo:** Identificar los elementos verificables del hallazgo crítico de torque que serán transformados en controles de auditoría.

**Instrucciones:**

1. Abre `L06_Hallazgo_Critico_v1.docx` en Microsoft Word.
2. Lee el documento completo antes de utilizar Copilot.
3. Identifica y registra, en una nota temporal o en una hoja de trabajo de Excel, los siguientes elementos del hallazgo:
   - Proceso afectado.
   - Producto o línea afectada.
   - Condición observada.
   - Requisito o criterio incumplido.
   - Evidencia disponible.
   - Evidencia faltante.
   - Riesgo para la calidad, el cliente, la seguridad o la trazabilidad.
   - Acción inmediata o contención aplicada, si existe.
   - Acción correctiva, responsable y estado, si están documentados.
4. Consulta el correo ejecutivo del Laboratorio 06-00-01.
5. Verifica si el correo incluye riesgos, prioridades, responsables, fechas compromiso o decisiones que deban considerarse durante la auditoría.
6. En Word, abre Copilot y utiliza el siguiente prompt:

```text
Analiza el documento abierto sobre el hallazgo crítico de torque. Extrae únicamente la información presente en el documento y organízala en una tabla con estas columnas: criterio o requisito citado, condición observada, evidencia disponible, evidencia faltante, riesgo identificado, proceso afectado y acción documentada.

No inventes requisitos, normas, procedimientos, fechas, responsables ni datos. Si un campo no aparece de forma explícita, escribe “información no localizada en el documento”.
```

7. Revisa la respuesta de Copilot comparándola con el documento original.
8. Corrige manualmente cualquier interpretación incorrecta, omisión o afirmación no sustentada.
9. Define el contexto de auditoría que se utilizará en la checklist:
   - **Objetivo de auditoría:** verificar que la liberación de producto controla el riesgo de torque no conforme y conserva evidencia trazable de la decisión de liberación.
   - **Alcance:** proceso de liberación de producto relacionado con la línea de ensamble y el caso de torque.
   - **Criterios:** únicamente los requisitos internos, instrucciones, registros o criterios expresamente identificados en el hallazgo crítico y en documentos corporativos autorizados.
   - **Periodo de muestreo:** el periodo definido en el hallazgo o, si no está indicado, un periodo que será definido por el auditor durante la ejecución real.

**Resultado esperado:**

Dispones de una síntesis validada del hallazgo crítico que distingue claramente entre hechos documentados, evidencia faltante y riesgos asociados al torque.

**Verificación:**

Confirma que puedes responder con evidencia documental a las siguientes preguntas:

- ¿Qué condición de torque fue observada?
- ¿Qué requisito interno o criterio fue incumplido?
- ¿Qué evidencia existe y cuál falta?
- ¿Cuál es el riesgo de liberar producto sin la verificación requerida?
- ¿Qué proceso o responsable deberá ser entrevistado durante una auditoría?

---

### Paso 2. Derivar controles preventivos, detectivos y documentales

**Objetivo:** Convertir el hallazgo de torque en controles auditables que ayuden a prevenir su repetición.

**Instrucciones:**

1. En el archivo `07_Checklist_Auditoria_Interna_Torque.xlsx`, cambia el nombre de la primera hoja a:

```text
Análisis del hallazgo
```

2. Crea una tabla con las siguientes columnas:

| Tipo de control | Riesgo que controla | Control esperado | Fuente o criterio real | Evidencia posible | Validado por |
|---|---|---|---|---|---|

3. Registra al menos un control de cada tipo:
   - Preventivo.
   - Detectivo.
   - Documental.

4. Utiliza la siguiente guía para derivar controles, adaptándola exclusivamente a los hechos del caso:

| Tipo de control | Propósito | Ejemplo orientativo |
|---|---|---|
| Preventivo | Evitar que se ensamble o libere producto sin cumplir el torque requerido | Verificar que el parámetro, programa o instrucción vigente esté disponible antes del inicio de producción |
| Detectivo | Detectar desviaciones antes de la liberación del producto | Revisar resultados de verificación de torque o registros de inspección definidos por el proceso |
| Documental | Mantener evidencia trazable de la ejecución y liberación | Conservar registros aprobados de inspección, liberación, desviación o retrabajo |

5. En la columna **Fuente o criterio real**, no escribas nombres de normas, cláusulas o procedimientos que no aparezcan en el hallazgo o en una fuente corporativa autorizada.
6. Si el documento menciona un procedimiento, un formato, una instrucción de trabajo, una especificación o un plan de control, registra el nombre exacto y, si está disponible, la sección, versión o referencia.
7. Si no existe una referencia documental confirmada, escribe:

```text
Criterio interno por confirmar durante la planificación de auditoría
```

8. Utiliza Copilot en Excel o Word para generar propuestas preliminares con el siguiente prompt:

```text
A partir del hallazgo crítico de torque resumido en esta hoja, propone controles preventivos, detectivos y documentales para una auditoría interna del proceso de liberación de producto.

Para cada control, indica el riesgo que busca controlar, la evidencia que podría verificarse y una pregunta de auditoría sugerida. No cites normas, cláusulas, procedimientos ni requisitos que no estén presentes en la información proporcionada. Marca como “por confirmar” cualquier referencia no disponible.
```

9. Revisa las propuestas de Copilot una por una.
10. Conserva solamente los controles que:
    - Estén relacionados con el hallazgo real.
    - Puedan verificarse mediante evidencia objetiva.
    - No introduzcan requisitos inexistentes.
    - Puedan ser auditados mediante entrevista, revisión documental, observación o muestreo.
11. Elimina o reformula controles ambiguos como “asegurar la calidad” o “revisar todo adecuadamente”, porque no permiten una verificación objetiva.

**Resultado esperado:**

La hoja `Análisis del hallazgo` contiene una matriz validada de controles preventivos, detectivos y documentales vinculados al riesgo de torque no conforme.

**Verificación:**

Valida que cada control cumpla las siguientes condiciones:

- Tiene un riesgo específico asociado.
- Define una actividad o condición verificable.
- Identifica evidencia posible.
- Está vinculado a un criterio real o marcado explícitamente como “por confirmar”.
- No depende de una afirmación generada por Copilot como única fuente de evidencia.

---

### Paso 3. Crear la estructura de la checklist de auditoría

**Objetivo:** Construir una tabla de auditoría interna con campos suficientes para registrar criterios, evidencia, resultados y seguimiento.

**Instrucciones:**

1. Crea una segunda hoja de Excel y asígnale el nombre:

```text
Checklist de auditoría
```

2. En la fila 1, crea las siguientes columnas obligatorias, en este orden:

| Columna | Encabezado |
|---|---|
| A | ID de control |
| B | Proceso o subproceso |
| C | Objetivo de auditoría |
| D | Requisito o criterio |
| E | Pregunta de verificación |
| F | Evidencia esperada |
| G | Método de muestreo |
| H | Entrevistado o responsable |
| I | Resultado conforme/no conforme/no aplicable |
| J | Referencia de evidencia |
| K | Severidad |
| L | Observaciones |
| M | Acción de seguimiento |

3. Selecciona el rango de encabezados y usa **Insertar > Tabla**.
4. Activa la opción **La tabla tiene encabezados**.
5. Asigna a la tabla el nombre:

```text
tblChecklistAuditoria
```

6. Ajusta el ancho de las columnas para facilitar la lectura. Se recomienda activar **Ajustar texto** en las columnas D a M.
7. Aplica inmovilización de paneles para mantener visibles los encabezados:
   - Selecciona la celda A2.
   - Ve a **Vista > Inmovilizar paneles > Inmovilizar fila superior**.
8. Crea listas desplegables mediante **Datos > Validación de datos** para la columna I:
   - Valores permitidos:

```text
Conforme,No conforme,No aplicable,Pendiente de verificar
```

9. Crea una lista desplegable para la columna K:
   - Valores permitidos:

```text
Crítica,Mayor,Menor,Observación,No aplica
```

10. Aplica formato condicional a la columna I:
    - `Conforme`: relleno verde claro.
    - `No conforme`: relleno rojo claro.
    - `No aplicable`: relleno gris.
    - `Pendiente de verificar`: relleno amarillo claro.
11. Aplica formato condicional a la columna K para resaltar `Crítica` y `Mayor`.
12. En una celda visible sobre la tabla, por ejemplo A1 si decides insertar filas adicionales, agrega el título:

```text
Checklist de auditoría interna — Liberación de producto y control de torque
```

13. Agrega, en una zona superior o en una hoja adicional llamada `Control documental`, los siguientes datos:
    - Fecha de creación.
    - Elaborado por.
    - Fuente principal: `L06_Hallazgo_Critico_v1.docx`.
    - Fuente complementaria: correo ejecutivo del Laboratorio 06-00-01.
    - Estado: Borrador para revisión humana.
    - Restricción: “Las preguntas deben validarse contra criterios y evidencia corporativa autorizada”.

**Resultado esperado:**

Existe una tabla denominada `tblChecklistAuditoria` con todas las columnas requeridas para planificar y ejecutar una auditoría interna.

**Verificación:**

Comprueba que:

- La tabla tiene las 13 columnas obligatorias.
- El campo de resultado permite seleccionar valores controlados.
- La severidad se clasifica mediante una lista controlada.
- La hoja identifica que el documento es un borrador sujeto a validación humana.
- No se ha utilizado una fuente externa de almacenamiento ni IA externa.

---

### Paso 4. Elaborar preguntas de auditoría trazables

**Objetivo:** Diseñar preguntas abiertas de auditoría que permitan verificar el control de liberación de producto y el tratamiento del riesgo de torque.

**Instrucciones:**

1. Regresa a la hoja `Análisis del hallazgo`.
2. Identifica los controles que deben convertirse en preguntas de auditoría.
3. En la hoja `Checklist de auditoría`, crea inicialmente entre 10 y 15 filas de control.
4. Utiliza identificadores consecutivos con el siguiente formato:

```text
AUD-TOR-001
AUD-TOR-002
AUD-TOR-003
```

5. Para cada fila, completa como mínimo:
   - Proceso o subproceso.
   - Objetivo de auditoría.
   - Requisito o criterio.
   - Pregunta de verificación.
   - Evidencia esperada.
   - Método de muestreo.
   - Entrevistado o responsable.
6. Formula preguntas abiertas, específicas y verificables. Evita preguntas que puedan responderse solamente con “sí” o “no”.
7. Usa este patrón de redacción:

```text
¿Cómo se asegura que [control o actividad] se realiza conforme a [criterio real] y qué evidencia demuestra su aplicación?
```

8. Usa Copilot en Excel para proponer preguntas mediante el siguiente prompt:

```text
Genera propuestas de preguntas abiertas para una checklist de auditoría interna del proceso de liberación de producto, enfocada en prevenir la repetición de un hallazgo de torque.

Organiza las propuestas en estas categorías:
1. Control preventivo antes de la producción o liberación.
2. Verificación detectiva de torque.
3. Gestión de registros de calidad.
4. Disposición de producto no conforme o retrabajado.
5. Acciones correctivas y verificación de eficacia.

Para cada propuesta, incluye: pregunta, evidencia esperada, método de muestreo sugerido y entrevistado probable.

No inventes referencias normativas, requisitos legales, procedimientos internos ni criterios no proporcionados. Usa “criterio interno por confirmar” cuando la fuente no esté disponible.
```

9. Revisa cada propuesta de Copilot antes de copiarla a la tabla.
10. Elimina preguntas que:
    - Asuman que el proceso cumple.
    - No tengan evidencia posible.
    - Se refieran a controles que no existen en el caso.
    - Citen cláusulas de ISO, IATF u otras normas no confirmadas.
    - Sean demasiado generales para permitir una conclusión de auditoría.
11. Completa una checklist inicial utilizando como referencia el siguiente modelo. Ajusta el texto para que corresponda al hallazgo real y a los documentos autorizados:

| ID de control | Proceso o subproceso | Pregunta de verificación | Evidencia esperada | Método de muestreo | Entrevistado o responsable |
|---|---|---|---|---|---|
| AUD-TOR-001 | Preparación de liberación | ¿Cómo se confirma que el personal utiliza la instrucción, especificación o parámetro vigente para el control de torque antes de liberar producto? | Instrucción vigente, registro de revisión, parámetro aprobado o evidencia de disponibilidad en punto de uso | Revisar una muestra de documentos vigentes y observar un punto de uso, si aplica | Supervisor de producción o responsable de calidad |
| AUD-TOR-002 | Verificación de torque | ¿Qué método se utiliza para verificar el torque y cómo se demuestra que la verificación fue realizada para el lote o producto evaluado? | Registro de verificación, resultado de inspección, identificación de lote o registro electrónico autorizado | Seleccionar muestras de lotes liberados del periodo definido | Inspector de calidad o técnico de proceso |
| AUD-TOR-003 | Liberación de producto | ¿Quién autoriza la liberación del producto y qué evidencia demuestra que se completaron las verificaciones requeridas antes de la liberación? | Registro de liberación, firma o aprobación electrónica, checklist de inspección | Muestreo de registros de liberación | Responsable de liberación o calidad |
| AUD-TOR-004 | Control de producto no conforme | ¿Cómo se identifica, contiene y registra un producto cuando la verificación de torque resulta no conforme? | Etiqueta, registro de no conformidad, segregación, disposición o retrabajo documentado | Revisar casos de producto no conforme asociados al periodo de auditoría | Calidad, producción o responsable de producto no conforme |
| AUD-TOR-005 | Registros de calidad | ¿Cómo se asegura la trazabilidad entre el resultado de torque, el lote, el producto y la decisión de liberación? | Registro de torque, número de lote, orden de producción y referencia de liberación | Trazar una muestra desde el lote hasta el registro de liberación | Responsable de registros de calidad |
| AUD-TOR-006 | Gestión de acciones correctivas | ¿Cómo se documentó la causa, la acción correctiva, el responsable y la fecha compromiso del hallazgo de torque? | Registro CAPA, análisis de causa, plan de acción o evidencia equivalente autorizada | Revisar el expediente del hallazgo y una muestra de acciones relacionadas | Responsable CAPA o líder de calidad |
| AUD-TOR-007 | Verificación de eficacia | ¿Qué evidencia demuestra que las acciones implementadas redujeron o eliminaron la recurrencia del riesgo de torque no conforme? | Resultados posteriores, tendencias, auditoría de seguimiento, verificación de eficacia | Comparar registros antes y después de la acción, según disponibilidad | Responsable CAPA, calidad o ingeniería |
| AUD-TOR-008 | Competencia y comunicación | ¿Cómo se confirma que las personas que realizan o verifican actividades críticas de torque conocen la instrucción vigente y sus responsabilidades? | Registro de capacitación, matriz de competencia, comunicación controlada o evaluación | Seleccionar una muestra de personal y sus registros aplicables | Supervisor y personal operativo |

12. Para cada fila, registra en la columna **Requisito o criterio** una referencia real, por ejemplo:
    - Nombre exacto de un procedimiento interno citado en el hallazgo.
    - Identificación de una instrucción de trabajo vigente.
    - Referencia al formato o registro de liberación.
    - Texto “Criterio interno por confirmar durante la planificación de auditoría”, cuando no exista una fuente validada.

13. No registres “ISO 9001”, “IATF 16949” ni números de cláusula salvo que estén expresamente autorizados y disponibles como criterio de auditoría para el caso.

**Resultado esperado:**

La checklist contiene al menos 10 preguntas abiertas, organizadas y trazables a controles relacionados con el riesgo de torque y la liberación de producto.

**Verificación:**

Comprueba que cada pregunta pueda responderse con evidencia verificable, no solo con una explicación verbal. Para cada fila, pregunta:

- ¿Cuál es el criterio contra el que se evaluará?
- ¿Qué registro, documento, observación o entrevista sustentará la respuesta?
- ¿Qué resultado podría justificar una no conformidad?
- ¿La pregunta se relaciona con el hallazgo de torque o con un control necesario para evitar su repetición?

---

### Paso 5. Definir métodos de muestreo y criterios de evaluación

**Objetivo:** Asegurar que la checklist permita recolectar evidencia objetiva de forma consistente durante una auditoría.

**Instrucciones:**

1. Completa la columna **Método de muestreo** para cada pregunta.
2. Utiliza métodos de muestreo realistas y proporcionales al tipo de evidencia. Puedes utilizar las siguientes opciones:
   - Muestreo de registros por periodo.
   - Muestreo de lotes liberados.
   - Trazabilidad de un lote desde producción hasta liberación.
   - Revisión de un caso de no conformidad.
   - Observación en punto de uso.
   - Entrevista a responsable del proceso.
   - Comparación antes/después de una acción correctiva.
3. Evita escribir únicamente “revisar documentos”. Especifica qué documentos, qué periodo o qué tipo de caso se revisará.
4. Completa la columna **Entrevistado o responsable** con el rol, no necesariamente con el nombre de una persona. Ejemplos:
   - Responsable de calidad.
   - Inspector de calidad.
   - Supervisor de producción.
   - Técnico de mantenimiento.
   - Responsable de CAPA.
   - Operador autorizado.
5. Define el uso de la columna **Resultado conforme/no conforme/no aplicable**:
   - `Conforme`: existe evidencia suficiente, verificable y alineada con el criterio.
   - `No conforme`: se identifica incumplimiento de un requisito o criterio aplicable.
   - `No aplicable`: el criterio no corresponde al proceso, producto, periodo o muestra auditada.
   - `Pendiente de verificar`: aún no se ha revisado evidencia suficiente.
6. Define el uso de la columna **Severidad**:
   - `Crítica`: riesgo elevado para cliente, seguridad, cumplimiento, liberación de producto o trazabilidad esencial.
   - `Mayor`: incumplimiento significativo del sistema o ausencia de un control requerido.
   - `Menor`: incumplimiento aislado que no demuestra una falla sistémica.
   - `Observación`: situación que requiere seguimiento, pero sin incumplimiento demostrado.
   - `No aplica`: no se ha identificado desviación.
7. Agrega una nota en la hoja `Control documental`:

```text
La clasificación final de una desviación debe ser realizada por personal competente y autorizado conforme al método interno de auditoría. Copilot no clasifica hallazgos ni sustituye la decisión del auditor.
```

8. Solicita a Copilot una revisión de consistencia con este prompt:

```text
Revisa la consistencia de la tabla tblChecklistAuditoria. Identifica filas donde:
- la pregunta no esté vinculada a un criterio;
- la evidencia esperada no permita verificar la pregunta;
- el método de muestreo sea demasiado general;
- el entrevistado no corresponda al proceso;
- exista una referencia normativa o procedimental no confirmada.

No modifiques la tabla automáticamente. Devuelve una lista de observaciones por ID de control y propone una corrección breve.
```

9. Revisa las observaciones de Copilot contra la tabla y contra el hallazgo fuente.
10. Realiza únicamente las correcciones que puedas justificar con evidencia o criterio autorizado.

**Resultado esperado:**

Cada punto de la checklist tiene un método de verificación definido, una fuente de evidencia esperada y un responsable o entrevistado apropiado.

**Verificación:**

Selecciona tres filas al azar y comprueba que un auditor podría ejecutar cada una sin necesidad de interpretar instrucciones ambiguas. Debe ser posible identificar:

- Qué se va a verificar.
- Contra qué criterio.
- Con qué evidencia.
- Sobre qué muestra.
- A quién se entrevistará.
- Cómo se registrará el resultado.

---

### Paso 6. Preparar preguntas de entrevista y realizar una revisión final

**Objetivo:** Complementar la checklist con preguntas de entrevista que permitan confirmar la aplicación real de los controles.

**Instrucciones:**

1. Crea una tercera hoja denominada:

```text
Preguntas de entrevista
```

2. Crea una tabla con las siguientes columnas:

| Categoría | Pregunta de entrevista | Respuesta esperada basada en evidencia | Evidencia a solicitar | Rol entrevistado | Relación con ID de control |
|---|---|---|---|---|---|

3. Crea preguntas de entrevista para las siguientes categorías:
   - Liberación de producto.
   - Verificación de torque.
   - Registros de calidad.
   - Producto no conforme.
   - Acciones correctivas.
   - Verificación de eficacia.
4. Formula al menos una pregunta por categoría.
5. Utiliza preguntas abiertas. Ejemplos:
   - “Descríbame cómo se decide que un lote puede ser liberado cuando existe una verificación crítica de torque.”
   - “Muéstreme el registro que relaciona el resultado de torque con el lote liberado.”
   - “¿Qué ocurre cuando un resultado de torque no cumple el criterio establecido?”
   - “¿Cómo se confirma que la acción correctiva aplicada al hallazgo de torque fue eficaz?”
6. En la columna **Respuesta esperada basada en evidencia**, no escribas una respuesta idealizada. Describe qué debe poder demostrar el entrevistado. Ejemplo:

```text
El entrevistado debe explicar el flujo y mostrar un registro de liberación trazable al lote y a la verificación aplicable.
```

7. En la columna **Relación con ID de control**, vincula cada pregunta con uno o más identificadores de la hoja `Checklist de auditoría`.
8. Revisa que las preguntas de entrevista no induzcan una respuesta esperada ni revelen anticipadamente la conclusión de auditoría.
9. Guarda el libro de Excel.
10. Espera a que OneDrive complete la sincronización.
11. Cierra y vuelve a abrir el archivo desde la carpeta sincronizada para confirmar que los datos se guardaron correctamente.

**Resultado esperado:**

El libro contiene una checklist ejecutable y una hoja de preguntas de entrevista vinculadas con los controles de auditoría.

**Verificación:**

Confirma que:

- La checklist incluye al menos 10 controles.
- Cada control tiene una pregunta, evidencia esperada y método de muestreo.
- Las preguntas de entrevista están relacionadas con identificadores de control.
- Los criterios no contienen referencias normativas inexistentes.
- El archivo está guardado en la ubicación corporativa autorizada.
- La sincronización de OneDrive se ha completado.

## Validación y pruebas

Realiza la siguiente validación final antes de considerar el laboratorio completado.

### Prueba 1. Trazabilidad desde el hallazgo hasta la checklist

1. Selecciona tres controles de la checklist.
2. Para cada uno, localiza en `L06_Hallazgo_Critico_v1.docx` o en una fuente corporativa autorizada el hecho, riesgo o criterio que justifica su existencia.
3. Registra la referencia en la columna **Referencia de evidencia** o en **Observaciones**.

**Criterio de aceptación:** Cada control seleccionado puede justificarse mediante el hallazgo, un riesgo identificado o un criterio interno validado.

### Prueba 2. Verificabilidad de las preguntas

1. Selecciona cinco preguntas de verificación.
2. Para cada pregunta, determina qué evidencia concreta permitiría responderla:
   - Registro.
   - Documento vigente.
   - Aprobación.
   - Resultado de inspección.
   - Observación.
   - Entrevista respaldada por evidencia.
3. Marca las preguntas que dependan solo de una respuesta verbal.
4. Reformula las preguntas marcadas para solicitar evidencia objetiva.

**Criterio de aceptación:** Ninguna pregunta crítica de liberación, torque, producto no conforme o CAPA depende únicamente de una afirmación verbal.

### Prueba 3. Control de contenido generado por IA

1. Revisa las columnas **Requisito o criterio** y **Observaciones**.
2. Busca referencias a normas, cláusulas, procedimientos, códigos documentales, fechas o responsables.
3. Verifica cada referencia contra el hallazgo o una fuente corporativa autorizada.
4. Elimina o marca como “por confirmar” cualquier referencia no verificable.

**Criterio de aceptación:** La checklist no contiene requisitos normativos, procedimientos o referencias inventadas por Copilot.

### Prueba 4. Simulación de ejecución

1. Selecciona la fila `AUD-TOR-003` o una pregunta equivalente sobre liberación de producto.
2. Simula una respuesta de auditoría:
   - El entrevistado indica quién autoriza la liberación.
   - El auditor solicita un registro de liberación.
   - El auditor busca trazabilidad entre lote, verificación de torque y aprobación.
3. Registra un ejemplo ficticio de ejecución en una copia temporal de la fila o en una nota:
   - Resultado.
   - Referencia de evidencia.
   - Severidad, si aplica.
   - Observación.
   - Acción de seguimiento, si aplica.
4. Elimina la simulación antes de entregar el archivo, o márcala claramente como:

```text
Ejemplo de entrenamiento — no corresponde a evidencia real de auditoría
```

**Criterio de aceptación:** La estructura de la checklist permite registrar una conclusión de auditoría sin perder trazabilidad de la evidencia.

## Solución de problemas

### Problema 1: Copilot propone cláusulas ISO, procedimientos o requisitos que no aparecen en el hallazgo

**Síntomas:** Copilot sugiere referencias como “ISO 9001 cláusula 8.6”, procedimientos con códigos no existentes o requisitos específicos que no se encuentran en los documentos disponibles.

**Causa:** El prompt no restringió suficientemente las fuentes permitidas, o Copilot completó información usando patrones generales de auditoría.

**Solución:**

1. No copies la referencia a la checklist.
2. Revisa `L06_Hallazgo_Critico_v1.docx`, el correo ejecutivo y los documentos corporativos autorizados.
3. Si la referencia no puede comprobarse, reemplázala por:

   ```text
   Criterio interno por confirmar durante la planificación de auditoría
   ```

4. Repite la solicitud a Copilot incluyendo la restricción:

   ```text
   Usa solamente referencias textuales presentes en el documento abierto. No cites normas ni procedimientos no visibles en el contenido proporcionado.
   ```

5. Mantén la validación humana como requisito previo a cualquier uso de la pregunta de auditoría.

### Problema 2: La lista desplegable de resultado o severidad no aparece en Excel

**Síntomas:** Las celdas de las columnas `Resultado conforme/no conforme/no aplicable` o `Severidad` permiten escribir texto libre, pero no muestran la flecha de selección.

**Causa:** La validación de datos se aplicó a una celda fuera de la tabla, a un rango incompleto o fue eliminada al insertar nuevas filas.

**Solución:**

1. Selecciona las celdas de datos de la columna afectada dentro de `tblChecklistAuditoria`.
2. Ve a **Datos > Validación de datos**.
3. Selecciona **Permitir: Lista**.
4. Para resultado, introduce:

   ```text
   Conforme,No conforme,No aplicable,Pendiente de verificar
   ```

5. Para severidad, introduce:

   ```text
   Crítica,Mayor,Menor,Observación,No aplica
   ```

6. Confirma que está activada la opción de lista desplegable en celda.
7. Agrega una fila nueva a la tabla y verifica que la validación se copie automáticamente.

## Limpieza

1. Guarda el archivo `07_Checklist_Auditoria_Interna_Torque.xlsx`.
2. Confirma que OneDrive haya sincronizado el archivo con SharePoint.
3. Cierra Microsoft Excel y Word.
4. No elimines `L06_Hallazgo_Critico_v1.docx`, el correo ejecutivo ni otros archivos fuente.
5. Elimina notas temporales locales que contengan información copiada del hallazgo, si fueron creadas fuera del archivo corporativo autorizado.
6. No copies el archivo a unidades USB, ubicaciones personales, almacenamiento no corporativo ni servicios externos.
7. Mantén el archivo como borrador de trabajo hasta que un responsable autorizado revise los criterios, preguntas y referencias documentales.

## Resumen

En este laboratorio convertiste un hallazgo crítico de torque en una checklist de auditoría interna para el proceso de liberación de producto. La lista resultante integra criterios, preguntas de verificación, evidencia esperada, muestreo, entrevistados, clasificación de resultados y acciones de seguimiento.

También utilizaste Microsoft 365 Copilot como apoyo para estructurar controles y proponer preguntas, manteniendo la validación humana como condición obligatoria. La checklist creada será un insumo para el Laboratorio 08-00-01, en el que se identificarán riesgos asociados al uso de Copilot durante la preparación, ejecución y documentación de auditorías.

### Recursos opcionales

- [ISO 19011 — Directrices para la auditoría de los sistemas de gestión](https://www.iso.org/standard/70017.html)
- [ISO 9001 — Sistemas de gestión de la calidad](https://www.iso.org/iso-9001-quality-management.html)
- [Microsoft Learn — Microsoft 365 Copilot](https://learn.microsoft.com/es-es/copilot/microsoft-365/)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
