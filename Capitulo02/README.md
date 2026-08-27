# Práctica: Taller práctico de diseño de prompts aplicados al día a día del área de calidad.

## Metadatos

| Elemento | Valor |
|---|---|
| Duración | 90 minutos |
| Complejidad | Media |
| Nivel de Bloom | Crear |

## Descripción general

En este laboratorio diseñará, probará y documentará una biblioteca inicial de prompts para actividades del área de calidad. Usará como hilo conductor la no conformidad de torque en la línea de ensamble y los criterios priorizados en el archivo `01_Casos_Uso_Priorizados.docx`.

El resultado principal será el documento controlable `02_Biblioteca_Prompts_Calidad.docx`, que contendrá al menos cuatro prompts reutilizables, sus resultados de prueba, reglas explícitas de verificación humana y observaciones de mejora. La salida de Copilot se tratará como apoyo de trabajo y nunca como evidencia, aprobación o decisión de calidad sin revisión competente.

## Objetivos de aprendizaje

Al finalizar este laboratorio, podrá:

- [ ] Construir prompts estructurados con rol, contexto, fuente de datos, tarea, delimitaciones, formato de salida, tono y reglas de verificación.
- [ ] Transformar solicitudes ambiguas de calidad en instrucciones reproducibles, trazables y auditables.
- [ ] Crear cuatro prompts reutilizables para no conformidades, auditorías, 8D e hipótesis iniciales de causa.
- [ ] Aplicar restricciones explícitas para evitar datos inventados, conclusiones sin evidencia y sustitución de la aprobación humana.
- [ ] Documentar resultados de prueba y criterios de aceptación en una biblioteca de prompts de calidad.

## Prerrequisitos

### Conocimientos requeridos

- Haber completado el Laboratorio 01.
- Comprender los conceptos básicos de no conformidad, CAPA, auditoría interna, 8D y análisis preliminar de causa.
- Distinguir entre:
  - **Hecho:** información registrada, observable o verificable en una fuente autorizada.
  - **Hipótesis:** explicación posible que requiere validación adicional.
  - **Conclusión:** afirmación sustentada por evidencia suficiente y revisión competente.
- Conocer el principio de uso responsable: Copilot puede organizar, resumir y proponer alternativas, pero no sustituye al responsable de calidad, auditor o dueño del proceso.

### Acceso requerido

- Cuenta corporativa Microsoft Entra ID con licencia activa de Microsoft 365 Copilot.
- Acceso de edición a Word, OneDrive for Business y SharePoint corporativo.
- Acceso al sitio y biblioteca corporativos:

```text
/sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/
```

- Archivo fuente disponible:

```text
01_Casos_Uso_Priorizados.docx
```

> **Importante:** No sobrescriba ni modifique los archivos fuente suministrados por el instructor. No copie información corporativa en servicios externos de IA, cuentas personales, memorias USB o unidades no autorizadas.

## Entorno del laboratorio

### Hardware recomendado

| Recurso | Requisito mínimo recomendado |
|---|---|
| Equipo | Intel Core i5 de 10.ª generación o AMD Ryzen 5 4000 Series, o equivalente |
| Memoria | 8 GB de RAM |
| Almacenamiento libre | 20 GB |
| Pantalla | Resolución mínima de 1920 × 1080 |
| Red corporativa | 10 Mbps de descarga y 5 Mbps de carga, como mínimo |
| Audio | Auriculares y micrófono opcionales para Teams o dictado |

### Software y servicios

| Componente | Uso en el laboratorio |
|---|---|
| Windows 11 Enterprise | Sistema operativo corporativo |
| Microsoft Word para Microsoft 365 | Creación y edición de la biblioteca |
| Microsoft 365 Copilot en Word o Copilot Chat | Prueba controlada de los prompts |
| OneDrive for Business | Sincronización local de archivos corporativos |
| SharePoint Online | Repositorio oficial del laboratorio |
| Microsoft Edge | Acceso alternativo a SharePoint y Copilot Chat |

### Ubicación de trabajo

La ruta local esperada en Windows es:

```text
C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
```

Puede abrir esta ubicación desde el Explorador de archivos. Si necesita confirmar la ruta desde una ventana de PowerShell, ejecute:

```powershell
$env:USERPROFILE
```

Luego compruebe que la carpeta de OneDrive corporativo está disponible. No cree copias de trabajo en Escritorio, Descargas ni ubicaciones personales.

### Convenciones obligatorias

| Elemento | Regla |
|---|---|
| Archivo de salida | Debe llamarse exactamente `02_Biblioteca_Prompts_Calidad.docx`. |
| Caso trazable | Debe conservarse el caso de no conformidad de torque en línea de ensamble. |
| Fuente prioritaria | Debe utilizarse `01_Casos_Uso_Priorizados.docx`. |
| Datos | Solo use datos suministrados, documentos corporativos autorizados o información claramente identificada como faltante. |
| Validación | Toda salida debe ser revisada por una persona responsable antes de usarla como evidencia, decisión o documento controlado. |

## Procedimiento paso a paso

### Paso 1. Preparar la ubicación de trabajo y crear el documento de salida

**Objetivo:** Crear el archivo de trabajo en la ubicación corporativa autorizada, sin alterar los archivos fuente.

**Instrucciones:**

1. Abra el Explorador de archivos y navegue a la carpeta sincronizada:

   ```text
   C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
   ```

2. Confirme que el archivo `01_Casos_Uso_Priorizados.docx` está presente.

3. Abra `01_Casos_Uso_Priorizados.docx` en Word.

4. Revise el documento e identifique la información correspondiente al caso prioritario de torque. Registre, como mínimo, los siguientes elementos:
   - Proceso o línea afectada.
   - Descripción de la no conformidad.
   - Requisito, criterio o condición esperada, si está disponible.
   - Datos registrados o evidencia disponible.
   - Riesgos o impacto señalado.
   - Casos de uso priorizados relacionados con no conformidades, auditorías, CAPA, 8D o causa raíz.
   - Información faltante que deba solicitarse antes de emitir conclusiones.

5. No modifique el archivo fuente. En Word, cree un documento nuevo.

6. Guarde el documento nuevo en la carpeta corporativa con el nombre exacto:

   ```text
   02_Biblioteca_Prompts_Calidad.docx
   ```

7. Agregue al inicio del documento el siguiente encabezado:

   ```markdown
   Biblioteca inicial de prompts de calidad

   Caso trazable: No conformidad de torque en la línea de ensamble
   Fuente prioritaria: 01_Casos_Uso_Priorizados.docx
   Fecha de elaboración: [dd/mm/aaaa]
   Elaborado por: [nombre del participante]
   Estado: Borrador para validación humana
   ```

8. Inserte una sección titulada:

   ```markdown
   Registro de hechos disponibles y datos faltantes
   ```

9. Debajo de la sección, cree una tabla con cuatro columnas:

   | Categoría | Información registrada | Fuente | Estado |
   |---|---|---|---|
   | Hecho |  |  | Verificado / Pendiente |
   | Requisito aplicable |  |  | Verificado / Pendiente |
   | Evidencia disponible |  |  | Verificado / Pendiente |
   | Información faltante |  |  | Pendiente |

10. Complete la tabla únicamente con información confirmada en el archivo fuente. Cuando un dato no aparezca, escriba `No suministrado en la fuente revisada`.

**Resultado esperado:**

Existe un documento llamado `02_Biblioteca_Prompts_Calidad.docx` en la carpeta corporativa. El documento contiene el encabezado del laboratorio y una tabla inicial que distingue hechos confirmados de información faltante.

**Verificación:**

- El nombre del archivo coincide exactamente con la convención obligatoria.
- El archivo se encuentra en OneDrive corporativo sincronizado con SharePoint.
- `01_Casos_Uso_Priorizados.docx` permanece sin cambios.
- No se han agregado valores, fechas, cantidades, responsables o requisitos que no estén presentes en la fuente.

---

### Paso 2. Analizar una solicitud ambigua y definir la estructura estándar del prompt

**Objetivo:** Reconocer la ambigüedad de una solicitud débil y establecer una estructura reutilizable para prompts de calidad.

**Instrucciones:**

1. En `02_Biblioteca_Prompts_Calidad.docx`, cree la sección:

   ```markdown
   Principios de diseño y estructura estándar
   ```

2. Agregue la siguiente solicitud ambigua:

   > “Analiza el problema de torque y dime qué debemos hacer.”

3. Debajo, cree una tabla de análisis como la siguiente:

   | Elemento requerido | ¿Está presente? | Observación |
   |---|---|---|
   | Rol de Copilot | No | No se define el tipo de apoyo requerido. |
   | Contexto | Parcial | Solo menciona torque; no identifica fuente, período ni condición. |
   | Fuente de datos | No | No se delimita la información autorizada. |
   | Tarea | Parcial | “Analiza” y “dime qué hacer” son expresiones ambiguas. |
   | Delimitaciones | No | Podría inducir conclusiones no sustentadas. |
   | Formato de salida | No | No especifica tabla, resumen, preguntas o estructura. |
   | Tono | No | No indica audiencia ni nivel de formalidad. |
   | Reglas de verificación | No | No exige separar hechos, hipótesis ni datos faltantes. |

4. Añada la siguiente estructura estándar como plantilla para los cuatro prompts del laboratorio:

   ```markdown
   Rol:
   [Indique el papel de apoyo de Copilot. Ejemplo: asistente de analista de calidad.]

   Contexto:
   [Describa el proceso, caso, requisito, período y propósito.]

   Fuente de datos autorizada:
   [Identifique documentos, datos pegados en el prompt o archivos autorizados.]

   Tarea:
   [Indique con verbos concretos qué debe producir Copilot.]

   Delimitaciones:
   [Indique alcance, exclusiones, extensión y restricciones.]

   Formato de salida:
   [Defina tabla, viñetas, secciones, número de preguntas o longitud.]

   Tono:
   [Especifique tono profesional, técnico, objetivo o ejecutivo.]

   Reglas de verificación:
   - No inventes datos.
   - Indica supuestos.
   - Separa hechos de hipótesis.
   - Usa únicamente la información suministrada.
   - Solicita información faltante.
   - No confirmes causas raíz, conformidad, eficacia de CAPA ni cumplimiento de requisitos sin evidencia verificable.
   - Indica que la salida requiere validación del responsable de calidad.
   ```

5. Añada una nota de control:

   > Los prompts de esta biblioteca se diseñan para preparar análisis, preguntas, borradores y estructuras. No autorizan a Copilot a cerrar una no conformidad, aprobar una CAPA, certificar conformidad ni declarar una causa raíz confirmada.

**Resultado esperado:**

El documento contiene un análisis claro de una solicitud ambigua y una plantilla de ocho componentes que se usará en los cuatro prompts.

**Verificación:**

- La estructura incluye rol, contexto, fuente, tarea, delimitaciones, formato, tono y reglas de verificación.
- Las cinco expresiones obligatorias están presentes literalmente:
  - `no inventes datos`
  - `indica supuestos`
  - `separa hechos de hipótesis`
  - `usa únicamente la información suministrada`
  - `solicita información faltante`
- La plantilla establece explícitamente validación humana.

---

### Paso 3. Diseñar y probar el prompt para resumen de una no conformidad

**Objetivo:** Crear un prompt que produzca un resumen factual y auditable de la no conformidad de torque, sin inferir datos no disponibles.

**Instrucciones:**

1. Cree una nueva sección en el documento:

   ```markdown
   Prompt 1. Resumen estructurado de no conformidad
   ```

2. Complete la siguiente plantilla. Sustituya los campos entre corchetes solo con información confirmada en `01_Casos_Uso_Priorizados.docx`.

   ```text
   Rol:
   Actúa como asistente de un analista de calidad. Tu función es organizar información disponible; no sustituyes al responsable de calidad.

   Contexto:
   Se analiza una no conformidad relacionada con torque en la línea de ensamble.
   El propósito es preparar un resumen objetivo para la revisión inicial del caso.

   Fuente de datos autorizada:
   Usa únicamente la información suministrada a continuación y el contenido identificado en el archivo 01_Casos_Uso_Priorizados.docx.

   Datos suministrados:
   - Proceso o línea: [dato confirmado o "No suministrado"]
   - Descripción de la no conformidad: [dato confirmado]
   - Requisito o criterio aplicable: [dato confirmado o "No suministrado"]
   - Fecha o período: [dato confirmado o "No suministrado"]
   - Evidencia registrada: [dato confirmado o "No suministrado"]
   - Riesgo o impacto indicado: [dato confirmado o "No suministrado"]
   - Estado conocido de la acción o CAPA: [dato confirmado o "No suministrado"]

   Tarea:
   Redacta un resumen estructurado de la no conformidad y prepara preguntas de seguimiento para completar la revisión inicial.

   Delimitaciones:
   No inventes datos. Indica supuestos. Separa hechos de hipótesis.
   Usa únicamente la información suministrada. Solicita información faltante.
   No afirmes una causa raíz, incumplimiento normativo, impacto al cliente ni eficacia de una acción si no existe evidencia incluida.
   No propongas el cierre de la no conformidad.

   Formato de salida:
   Entrega las siguientes secciones:
   1. Hechos registrados.
   2. Requisito o condición esperada.
   3. Desviación descrita.
   4. Evidencia disponible.
   5. Información faltante.
   6. Cinco preguntas de seguimiento priorizadas.
   7. Advertencia de validación humana.

   Tono:
   Profesional, objetivo, técnico y apto para un registro preliminar de calidad.

   Reglas de verificación:
   Identifica explícitamente cada afirmación como hecho, hipótesis o dato faltante.
   Cierra con la frase: "Este resultado es un borrador de apoyo y debe ser validado por el responsable de calidad antes de utilizarse."
   ```

3. Revise que el bloque de datos no incluya ejemplos ficticios, valores inventados ni nombres de personas no presentes en la fuente.

4. Pruebe el prompt en Microsoft 365 Copilot Chat o en Copilot para Word:
   - Si usa Copilot Chat, pegue el prompt completo.
   - Si usa Copilot en Word, seleccione el bloque del prompt y solicite que genere la salida a continuación, sin reemplazar el texto original.

5. Copie la respuesta obtenida debajo del prompt, bajo el subtítulo:

   ```markdown
   Resultado de prueba 1
   ```

6. Agregue un bloque de revisión humana:

   | Criterio de revisión | Resultado | Comentario |
   |---|---|---|
   | No inventa datos | Cumple / No cumple |  |
   | Distingue hechos de hipótesis | Cumple / No cumple |  |
   | Declara datos faltantes | Cumple / No cumple |  |
   | No confirma causa raíz | Cumple / No cumple |  |
   | Incluye advertencia de validación humana | Cumple / No cumple |  |

7. Si la respuesta contiene una afirmación no sustentada, marque `No cumple`, identifique el texto y ajuste el prompt antes de continuar.

**Resultado esperado:**

Un prompt reutilizable para resumir la no conformidad de torque y un resultado de prueba que distingue hechos, hipótesis e información faltante.

**Verificación:**

- El resultado no presenta causas como confirmadas.
- La respuesta solicita información faltante cuando el documento fuente no proporciona evidencia suficiente.
- El prompt y la respuesta contienen referencia al caso de torque.
- La tabla de revisión humana está completada.

---

### Paso 4. Diseñar y probar el prompt para preparar preguntas de auditoría

**Objetivo:** Crear un prompt para generar preguntas de auditoría interna trazables a evidencia objetiva, evitando convertir sugerencias de Copilot en hallazgos de auditoría.

**Instrucciones:**

1. Cree la sección:

   ```markdown
   Prompt 2. Preparación de preguntas para auditoría interna
   ```

2. Añada el siguiente prompt y complete los campos de contexto con información validada:

   ```text
   Rol:
   Actúa como asistente de preparación para un auditor interno de calidad. No actúas como auditor que emite hallazgos ni como aprobador de cumplimiento.

   Contexto:
   Se preparará una auditoría interna relacionada con el proceso de ensamble y el manejo de la no conformidad de torque.
   El objetivo es definir preguntas que permitan recolectar evidencia objetiva sobre el control del torque, la identificación de producto no conforme y el tratamiento de acciones correctivas.

   Fuente de datos autorizada:
   Usa únicamente la información suministrada en este prompt y los criterios identificados en 01_Casos_Uso_Priorizados.docx.
   Criterios internos o requisitos disponibles:
   - [criterio confirmado o "No suministrado"]
   - [procedimiento, instrucción o registro confirmado o "No suministrado"]

   Tarea:
   Propón preguntas de auditoría y la evidencia objetiva que el auditor debería solicitar o revisar.

   Delimitaciones:
   No inventes datos. Indica supuestos. Separa hechos de hipótesis.
   Usa únicamente la información suministrada. Solicita información faltante.
   No declares incumplimientos, no conformidades de auditoría ni cumplimiento de ISO 9001 sin revisar evidencia objetiva.
   No cites cláusulas específicas de ISO 9001 si no fueron proporcionadas o si no puedes confirmar su aplicabilidad en el procedimiento interno.

   Formato de salida:
   Presenta una tabla con estas columnas:
   1. Tema de auditoría.
   2. Pregunta de auditoría.
   3. Evidencia objetiva esperada.
   4. Riesgo que ayuda a evaluar.
   5. Información o criterio faltante.
   Incluye entre 8 y 10 preguntas, agrupadas en:
   - Control del proceso de torque.
   - Competencia o instrucciones de trabajo.
   - Producto no conforme.
   - CAPA o seguimiento de acciones.

   Tono:
   Profesional, neutral, objetivo y adecuado para preparación de auditoría interna.

   Reglas de verificación:
   Diferencia entre "evidencia esperada" y "evidencia verificada".
   Finaliza indicando que las preguntas deben ser validadas por el auditor competente y alineadas con el programa de auditoría vigente.
   ```

3. Pruebe el prompt con Copilot.

4. Pegue la salida bajo el subtítulo:

   ```markdown
   Resultado de prueba 2
   ```

5. Revise que la salida use lenguaje de auditoría apropiado. Por ejemplo:
   - Adecuado: “Solicitar registro de verificación de torque.”
   - No adecuado: “La línea incumple el procedimiento de torque.”

6. Agregue una tabla de validación:

   | Criterio | Cumple / No cumple | Evidencia de la revisión |
   |---|---|---|
   | Las preguntas son auditables y observables |  |  |
   | La evidencia solicitada es objetiva |  |  |
   | No declara hallazgos sin evidencia |  |  |
   | No inventa requisitos o cláusulas |  |  |
   | Identifica criterios faltantes |  |  |
   | Exige validación del auditor competente |  |  |

7. Si la respuesta inventa una cláusula, un procedimiento o un requisito, modifique la restricción de fuente y vuelva a ejecutar la prueba.

**Resultado esperado:**

Una tabla de preguntas de auditoría relacionadas con el control de torque, evidencia objetiva esperada y vacíos de información identificados.

**Verificación:**

- Existen entre 8 y 10 preguntas.
- Las preguntas permiten pedir registros, observar prácticas, entrevistar roles o verificar documentación.
- No se afirma que exista un incumplimiento.
- La salida incluye una distinción entre evidencia esperada y evidencia verificada.

---

### Paso 5. Diseñar y probar el prompt para una estructura de reporte 8D

**Objetivo:** Crear un prompt que genere una estructura inicial de 8D para el caso de torque, preservando la diferencia entre información conocida, datos faltantes y acciones por validar.

**Instrucciones:**

1. Cree la sección:

   ```markdown
   Prompt 3. Propuesta de estructura para reporte 8D
   ```

2. Agregue el siguiente prompt:

   ```text
   Rol:
   Actúa como asistente de documentación para un equipo de calidad que prepara un borrador inicial de reporte 8D.

   Contexto:
   El caso trazable corresponde a una no conformidad de torque en la línea de ensamble.
   Se necesita una estructura inicial para organizar información disponible y definir qué debe validarse antes de emitir un reporte formal.

   Fuente de datos autorizada:
   Usa únicamente la información suministrada en este prompt y la información confirmada en 01_Casos_Uso_Priorizados.docx.

   Datos disponibles:
   - Descripción del problema: [dato confirmado]
   - Proceso afectado: [dato confirmado o "No suministrado"]
   - Producto afectado: [dato confirmado o "No suministrado"]
   - Fecha o período: [dato confirmado o "No suministrado"]
   - Contención existente: [dato confirmado o "No suministrado"]
   - Evidencia disponible: [dato confirmado o "No suministrado"]
   - Responsables identificados: [dato confirmado o "No suministrado"]

   Tarea:
   Propón un borrador de estructura 8D que organice los datos disponibles, identifique vacíos de información y sugiera preguntas de validación para cada disciplina.

   Delimitaciones:
   No inventes datos. Indica supuestos. Separa hechos de hipótesis.
   Usa únicamente la información suministrada. Solicita información faltante.
   No declares causa raíz confirmada, acción correctiva aprobada, eficacia demostrada ni cierre del caso.
   No asignes responsables, fechas compromiso o recursos si no se proporcionan expresamente.

   Formato de salida:
   Presenta una tabla con las disciplinas D0 a D8 y las columnas:
   1. Disciplina.
   2. Propósito.
   3. Información confirmada disponible.
   4. Información faltante.
   5. Preguntas o acciones de validación.
   Incluye una sección final titulada "Controles antes de emitir el 8D formal" con al menos cinco controles de revisión humana.

   Tono:
   Técnico, estructurado, objetivo y adecuado para un borrador interno.

   Reglas de verificación:
   Marca cualquier contenido no confirmado como "Pendiente de validación".
   No conviertas hipótesis en causas raíz.
   Finaliza indicando que el reporte 8D formal requiere aprobación conforme al procedimiento interno aplicable.
   ```

3. Pruebe el prompt con Copilot.

4. Inserte la respuesta bajo:

   ```markdown
   Resultado de prueba 3
   ```

5. Revise especialmente las disciplinas:
   - **D0:** planificación o respuesta inicial.
   - **D1:** equipo.
   - **D2:** descripción del problema.
   - **D3:** acciones de contención.
   - **D4:** análisis y verificación de causa raíz.
   - **D5:** acciones correctivas permanentes.
   - **D6:** implementación y validación de eficacia.
   - **D7:** prevención de recurrencia.
   - **D8:** reconocimiento y cierre.

6. Añada una tabla de revisión:

   | Criterio | Cumple / No cumple | Comentario |
   |---|---|---|
   | Incluye D0 a D8 |  |  |
   | Distingue datos confirmados de pendientes |  |  |
   | No asigna responsables o fechas inventadas |  |  |
   | No confirma causa raíz ni eficacia |  |  |
   | Incluye controles previos al 8D formal |  |  |
   | Indica aprobación según procedimiento interno |  |  |

**Resultado esperado:**

Una propuesta de estructura 8D completa, pero claramente identificada como borrador, con vacíos de información y preguntas de validación.

**Verificación:**

- La estructura contiene D0 a D8.
- Los campos sin fuente se señalan como pendientes.
- No se presentan acciones como aprobadas ni eficaces sin evidencia.
- El resultado puede reutilizarse en el Laboratorio 04 como base de documentación, previa validación.

---

### Paso 6. Diseñar y probar el prompt para hipótesis iniciales de causa

**Objetivo:** Crear un prompt que apoye la generación controlada de hipótesis para el análisis de la no conformidad de torque, sin sustituir una investigación de causa raíz.

**Instrucciones:**

1. Cree la sección:

   ```markdown
   Prompt 4. Hipótesis iniciales para análisis de causa
   ```

2. Inserte el siguiente prompt:

   ```text
   Rol:
   Actúa como asistente para un equipo multidisciplinario de análisis preliminar de causa en calidad.

   Contexto:
   Se investiga una no conformidad relacionada con torque en la línea de ensamble.
   El objetivo es generar hipótesis iniciales que orienten la recolección de evidencia, no determinar una causa raíz definitiva.

   Fuente de datos autorizada:
   Usa únicamente la información suministrada a continuación y la información confirmada en 01_Casos_Uso_Priorizados.docx.

   Hechos disponibles:
   - [hecho confirmado 1]
   - [hecho confirmado 2]
   - [hecho confirmado 3]
   - [si no existen suficientes hechos, escribir "Información insuficiente para formular hipótesis específicas"]

   Tarea:
   Genera hipótesis iniciales relacionadas con posibles categorías de análisis de causa y define la evidencia necesaria para validar o descartar cada hipótesis.

   Delimitaciones:
   No inventes datos. Indica supuestos. Separa hechos de hipótesis.
   Usa únicamente la información suministrada. Solicita información faltante.
   No declares una causa raíz confirmada.
   No atribuyas responsabilidad a personas, áreas o proveedores sin evidencia.
   No recomiendes implementar acciones correctivas permanentes como si ya estuvieran aprobadas.

   Formato de salida:
   Presenta una tabla con las columnas:
   1. Categoría de análisis.
   2. Hecho relacionado.
   3. Hipótesis inicial.
   4. Supuesto asociado.
   5. Evidencia necesaria para validar o descartar.
   6. Método sugerido de verificación.
   7. Estado.
   Considera, cuando sea aplicable, las categorías: método, máquina o herramienta, material, mano de obra o competencia, medición, entorno y gestión del cambio.
   Incluye de 5 a 7 hipótesis como máximo.

   Tono:
   Técnico, prudente, neutral y orientado a investigación.

   Reglas de verificación:
   Marca todas las hipótesis como "No verificadas".
   Si no existe evidencia suficiente, prioriza preguntas de recolección de datos en lugar de hipótesis específicas.
   Finaliza con una advertencia: "Las hipótesis no constituyen una causa raíz; requieren verificación mediante evidencia objetiva y revisión del equipo responsable."
   ```

3. Pruebe el prompt con Copilot.

4. Copie el resultado bajo:

   ```markdown
   Resultado de prueba 4
   ```

5. Revise cada hipótesis y confirme que:
   - Está asociada a al menos un hecho disponible o a una declaración explícita de falta de datos.
   - No culpa a un operador, proveedor o área sin evidencia.
   - Es verificable mediante registros, observación, entrevista, medición o revisión documental.
   - Está marcada como `No verificada`.

6. Agregue una tabla de revisión:

   | Criterio | Cumple / No cumple | Comentario |
   |---|---|---|
   | Las hipótesis se diferencian de los hechos |  |  |
   | Cada hipótesis solicita evidencia verificable |  |  |
   | No se atribuyen responsabilidades sin evidencia |  |  |
   | No se declara causa raíz |  |  |
   | Se identifican supuestos y datos faltantes |  |  |
   | Se incluye advertencia de validación humana |  |  |

**Resultado esperado:**

Una matriz de hipótesis iniciales para el caso de torque, cada una vinculada con evidencia requerida y marcada como no verificada.

**Verificación:**

- Se presentan como máximo siete hipótesis.
- Cada hipótesis incluye un método de verificación.
- La respuesta no utiliza expresiones concluyentes como “la causa raíz es” o “se confirma que”.
- La advertencia final está incluida.

---

### Paso 7. Consolidar la biblioteca y documentar reglas de uso responsable

**Objetivo:** Convertir los cuatro prompts y sus pruebas en una biblioteca reutilizable, trazable y preparada para los laboratorios posteriores.

**Instrucciones:**

1. Al final de `02_Biblioteca_Prompts_Calidad.docx`, cree la sección:

   ```markdown
   Matriz de reutilización de prompts
   ```

2. Inserte la siguiente tabla y complétela:

   | ID | Nombre del prompt | Caso de uso | Entrada mínima requerida | Salida esperada | Revisión humana obligatoria |
   |---|---|---|---|---|---|
   | P-01 | Resumen estructurado de no conformidad | Revisión inicial de NC | Hechos, requisito, evidencia, fecha o período | Resumen y preguntas de seguimiento | Responsable de calidad |
   | P-02 | Preparación de preguntas para auditoría interna | Planificación de auditoría | Criterios, proceso, registros disponibles | Preguntas y evidencia esperada | Auditor competente |
   | P-03 | Propuesta de estructura para reporte 8D | Borrador de investigación 8D | Problema, proceso, evidencia, contención conocida | Tabla D0-D8 y vacíos | Líder del equipo 8D / Calidad |
   | P-04 | Hipótesis iniciales para análisis de causa | Investigación preliminar | Hechos verificados y datos faltantes | Hipótesis y evidencia requerida | Equipo multidisciplinario |

3. Cree una sección titulada:

   ```markdown
   Lista de verificación previa al uso de una salida de Copilot
   ```

4. Agregue la siguiente lista de verificación:

   - [ ] Confirmé que el prompt identifica el proceso, caso o indicador.
   - [ ] Confirmé que los datos usados proceden de una fuente corporativa autorizada.
   - [ ] Verifiqué que no se inventaron cantidades, fechas, requisitos, responsables o evidencias.
   - [ ] Separé los hechos registrados de hipótesis, recomendaciones o interpretaciones.
   - [ ] Revisé la información faltante solicitada por Copilot.
   - [ ] Confirmé que no se declara una causa raíz sin evidencia verificable.
   - [ ] Confirmé que no se emite una aprobación, cierre, decisión CAPA o hallazgo de auditoría sin la autoridad correspondiente.
   - [ ] Revisé que el tono y formato sean adecuados para el uso previsto.
   - [ ] Registré los cambios realizados al prompt después de la prueba.
   - [ ] Identifiqué al responsable humano que validará el resultado.

5. Cree una sección final titulada:

   ```markdown
   Registro de ajustes posteriores a la prueba
   ```

6. Inserte esta tabla:

   | Prompt | Hallazgo durante la prueba | Ajuste aplicado | Motivo del ajuste | Validado por |
   |---|---|---|---|---|
   | P-01 |  |  |  |  |
   | P-02 |  |  |  |  |
   | P-03 |  |  |  |  |
   | P-04 |  |  |  |  |

7. Complete al menos un ajuste real si detectó una salida incompleta, ambigua o no sustentada. Si no se requirieron ajustes, escriba:

   ```text
   Sin ajustes adicionales; la salida fue revisada contra los criterios definidos y permanece pendiente de validación formal por el responsable aplicable.
   ```

8. Guarde el documento y confirme que OneDrive muestra el estado de sincronización correcto.

**Resultado esperado:**

Una biblioteca consolidada que contiene cuatro prompts, cuatro resultados de prueba, criterios de aceptación, matriz de reutilización, lista de verificación y registro de ajustes.

**Verificación:**

- El documento contiene los cuatro prompts obligatorios.
- Cada prompt incorpora las reglas de verificación requeridas.
- El caso de torque aparece de forma consistente.
- Cada resultado de prueba tiene una revisión humana documentada.
- El archivo está guardado con el nombre obligatorio y sincronizado con el repositorio corporativo.

## Validación y pruebas

Complete la siguiente validación final antes de entregar el laboratorio.

| Prueba | Criterio de aceptación | Resultado |
|---|---|---|
| Nombre y ubicación | El archivo se llama exactamente `02_Biblioteca_Prompts_Calidad.docx` y está en la carpeta corporativa Batch_01. | Cumple / No cumple |
| Trazabilidad del caso | Los cuatro prompts hacen referencia al caso de torque en línea de ensamble. | Cumple / No cumple |
| Estructura de prompts | Cada prompt incluye rol, contexto, fuente, tarea, delimitaciones, formato, tono y reglas de verificación. | Cumple / No cumple |
| Restricciones explícitas | Cada prompt contiene las expresiones obligatorias: “no inventes datos”, “indica supuestos”, “separa hechos de hipótesis”, “usa únicamente la información suministrada” y “solicita información faltante”. | Cumple / No cumple |
| Prompt de NC | Genera resumen factual, evidencia disponible y preguntas de seguimiento. | Cumple / No cumple |
| Prompt de auditoría | Genera preguntas auditables y evidencia objetiva esperada sin declarar hallazgos. | Cumple / No cumple |
| Prompt 8D | Incluye D0 a D8 y diferencia información confirmada de pendiente. | Cumple / No cumple |
| Prompt de causa | Genera hipótesis no verificadas con evidencia necesaria para validarlas o descartarlas. | Cumple / No cumple |
| Validación humana | Cada prueba tiene una tabla de revisión completada. | Cumple / No cumple |
| Uso responsable | Ninguna salida se presenta como evidencia definitiva, causa raíz confirmada, CAPA aprobada o cierre autorizado. | Cumple / No cumple |

### Criterio de finalización

El laboratorio se considera completado cuando todos los criterios anteriores están marcados como `Cumple`, o cuando los elementos pendientes están claramente documentados con una acción de corrección y responsable de validación identificado.

## Solución de problemas

### Problema 1. Copilot no puede acceder al archivo o responde sin considerar el caso de torque

**Síntomas:**

- Copilot genera una respuesta genérica que no utiliza la información del archivo fuente.
- No aparecen referencias al caso de torque.
- Copilot indica que no puede acceder al documento o no encuentra información relevante.

**Causa probable:**

El archivo no está sincronizado, el usuario no tiene permisos en SharePoint, el documento no está abierto en el contexto de Word o el prompt no incluye los datos relevantes de forma explícita.

**Solución:**

1. Confirme que `01_Casos_Uso_Priorizados.docx` está en la carpeta sincronizada corporativa.
2. Verifique el icono de estado de OneDrive y espere a que finalice la sincronización.
3. Abra el archivo fuente en Word con la cuenta corporativa correcta.
4. Incluya en el prompt los hechos confirmados extraídos del archivo, en lugar de asumir que Copilot accederá automáticamente a todo el contenido.
5. Si el problema persiste, valide los permisos del sitio `/sites/CopilotCalidad/` con el instructor o administrador del repositorio.

### Problema 2. La respuesta de Copilot inventa datos o presenta hipótesis como conclusiones

**Síntomas:**

- La respuesta asigna fechas, responsables, cantidades, requisitos o causas no incluidos en la fuente.
- Copilot afirma que una causa está confirmada.
- Se presentan recomendaciones o acciones como aprobadas.

**Causa probable:**

El prompt contiene restricciones insuficientes, los datos no están claramente delimitados o el formato de salida no exige separar hechos, hipótesis e información faltante.

**Solución:**

1. Revise que el prompt incluya literalmente las cinco reglas obligatorias.
2. Delimite los datos con un bloque titulado `Datos suministrados` o `Hechos disponibles`.
3. Añada la instrucción: `Si un dato no está disponible, escribe "No suministrado" y formula una pregunta de seguimiento.`
4. Añada la instrucción: `No declares una causa raíz, cumplimiento, eficacia o aprobación sin evidencia verificable.`
5. Ejecute nuevamente el prompt y documente el ajuste en el registro de cambios de la biblioteca.
6. No use la salida no conforme como evidencia ni la incorpore a documentación controlada sin corrección y revisión humana.

## Limpieza

1. Confirme que `02_Biblioteca_Prompts_Calidad.docx` está guardado y sincronizado en OneDrive for Business.
2. Cierre los documentos de Word que ya no necesite.
3. No elimine el archivo de salida, los archivos fuente ni la carpeta corporativa del laboratorio.
4. No conserve copias en carpetas personales, dispositivos USB, correo personal ni servicios externos.
5. Si creó borradores temporales fuera de la ruta corporativa por error, elimínelos siguiendo las políticas de retención y seguridad de la organización.

## Resumen

En este laboratorio creó una biblioteca inicial de prompts para calidad basada en el caso de no conformidad de torque. Los prompts desarrollados permiten apoyar la preparación de resúmenes de no conformidad, preguntas de auditoría, estructuras 8D e hipótesis preliminares de causa.

La práctica principal fue transformar una solicitud ambigua en una instrucción estructurada mediante ocho elementos: rol, contexto, fuente de datos, tarea, delimitaciones, formato de salida, tono y reglas de verificación. También aplicó controles para evitar la invención de datos, distinguir hechos de hipótesis y preservar la validación humana obligatoria.

El archivo `02_Biblioteca_Prompts_Calidad.docx` será un insumo para el análisis de datos de no conformidades en Excel durante el Laboratorio 03 y para la generación de documentación 8D durante el Laboratorio 04.

### Recursos opcionales

- [Microsoft Support: Copilot en Microsoft 365](https://support.microsoft.com/es-es/copilot)
- [ISO 9001 — Sistemas de gestión de la calidad](https://www.iso.org/iso-9001-quality-management.html)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
