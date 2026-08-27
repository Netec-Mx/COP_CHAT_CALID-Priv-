# Práctica: Ejercicios rápidos de exploración y validación de casos reales de uso en planta.

## Metadatos

| Elemento | Valor |
|---|---|
| Duración | 30 minutos |
| Complejidad | Fácil |
| Nivel de Bloom | Aplicar |

## Descripción general

En esta práctica iniciarás la cadena de trabajo del lote de calidad mediante la exploración de casos reales de uso de Microsoft 365 Copilot en una planta simulada. Trabajarás sobre un escenario de incremento de rechazos, no conformidades recurrentes de torque en la línea de ensamble y retrasos en el cierre de acciones CAPA.

El resultado será un registro priorizado de casos de uso que identificará oportunidades, beneficios, entradas disponibles, salidas esperadas, riesgos y controles de validación humana. Este registro se conservará como el archivo `01_Casos_Uso_Priorizados.docx` y será reutilizado en laboratorios posteriores para diseñar prompts estructurados y verificables.

## Objetivos de aprendizaje

Al finalizar la práctica, podrás:

- [ ] Identificar al menos cinco casos concretos de uso de Copilot aplicables a calidad, producción, auditoría y mejora continua.
- [ ] Relacionar cada caso de uso con un proceso, usuario responsable, entradas verificables y una salida esperada.
- [ ] Distinguir entre resultados que Copilot puede preparar como borrador y decisiones que requieren evidencia técnica y aprobación humana.
- [ ] Aplicar controles básicos de confidencialidad al usar Copilot dentro del entorno corporativo autorizado.
- [ ] Crear y guardar el registro priorizado de casos de uso en la biblioteca corporativa de SharePoint sincronizada.

## Requisitos previos

### Conocimientos requeridos

Antes de comenzar, debes comprender de forma básica los siguientes conceptos:

- No conformidad, contención, acción correctiva y acción preventiva.
- CAPA y seguimiento de compromisos.
- Auditoría interna y evidencia objetiva.
- Proceso de ensamble y control de torque.
- Diferencia entre un hecho confirmado, una hipótesis y una causa raíz demostrada.
- Principio de validación humana de resultados generados por IA.

### Accesos requeridos

Confirma que dispones de lo siguiente:

- Cuenta corporativa de Microsoft Entra ID activa.
- Licencia activa de Microsoft 365 Copilot asignada a tu cuenta.
- Acceso de edición a SharePoint Online y a la biblioteca del curso.
- Acceso a Microsoft Word y Microsoft 365 Copilot Chat.
- Archivo fuente `01_Casos_Uso_Calidad.docx` disponible en la carpeta corporativa definida.
- Sincronización activa de OneDrive for Business con la biblioteca de SharePoint del curso.

> **Importante:** Utiliza exclusivamente el tenant corporativo asignado por la organización. No copies información del laboratorio a cuentas personales, memorias USB, servicios de almacenamiento externos ni herramientas de IA no autorizadas.

## Entorno de laboratorio

### Recursos de hardware

| Recurso | Requisito mínimo recomendado |
|---|---|
| Equipo | Intel Core i5 de 8.ª generación o equivalente |
| Memoria | 8 GB de RAM |
| Espacio disponible | 10 GB libres en disco |
| Pantalla | Resolución mínima de 1920 × 1080 píxeles |
| Red | Conexión corporativa estable de al menos 10 Mbps de descarga y 5 Mbps de carga |
| Audio | Opcional para futuras actividades con Teams |

### Software y servicios

| Componente | Uso en esta práctica |
|---|---|
| Windows 11 Enterprise | Sistema operativo del equipo corporativo |
| Microsoft Word | Revisión, edición y guardado del registro de casos de uso |
| Microsoft 365 Copilot Chat | Exploración inicial de oportunidades, riesgos y preguntas de validación |
| Microsoft 365 Copilot en Word | Apoyo opcional para estructurar contenido dentro del documento |
| OneDrive for Business | Sincronización local de archivos corporativos |
| SharePoint Online | Almacenamiento oficial y colaboración controlada |

### Ruta de trabajo corporativa

La biblioteca de SharePoint que debes sincronizar es:

```text
/sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/
```

En un equipo Windows, la ruta local esperada es:

```text
C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
```

Puedes abrir la carpeta mediante el Explorador de archivos o ejecutar el siguiente comando en PowerShell:

```powershell
Start-Process "$env:USERPROFILE\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua"
```

> Si el nombre de la organización mostrado por OneDrive es diferente de `Organizacion`, abre OneDrive desde el Explorador de archivos y navega manualmente a la carpeta `CopilotCalidad\Batch_01_Calidad_Mejora_Continua`.

### Controles de uso responsable

Durante toda la práctica, aplica los siguientes controles:

1. Usa solamente datos ficticios, anonimizados o autorizados para el ejercicio.
2. No incluyas nombres de clientes, proveedores, empleados ni números de parte confidenciales si no están autorizados en el archivo fuente.
3. No solicites a Copilot que invente registros de inspección, resultados de medición, causas raíz, firmas, fechas de aprobación o evidencias de auditoría.
4. Trata toda salida de Copilot como un borrador que debe ser revisado por una persona competente.
5. Conserva la trazabilidad de los casos de uso, sus entradas y la validación humana requerida.

## Procedimiento paso a paso

### Paso 1. Verificar la carpeta de trabajo y proteger el archivo fuente

**Objetivo:** Confirmar que la biblioteca corporativa está disponible, ubicar el archivo fuente y evitar su sobrescritura.

**Instrucciones:**

1. Abre el Explorador de archivos de Windows.
2. Navega a la ruta local sincronizada:

   ```text
   C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
   ```

3. Localiza el archivo:

   ```text
   01_Casos_Uso_Calidad.docx
   ```

4. Verifica que el icono de OneDrive indique que el archivo está sincronizado. Según la configuración corporativa, puede mostrarse una marca de verificación verde o un icono de nube.
5. Haz clic derecho sobre `01_Casos_Uso_Calidad.docx` y selecciona **Abrir**.
6. Revisa el contenido inicial sin modificarlo todavía.
7. En Word, selecciona **Archivo > Guardar una copia** o **Archivo > Guardar como**, según la versión disponible.
8. Guarda la copia en la misma carpeta corporativa con el nombre exacto:

   ```text
   01_Casos_Uso_Priorizados.docx
   ```

9. Confirma que estás editando el archivo nuevo. Revisa el nombre en la barra superior de Word.

**Resultado esperado:**

- El archivo fuente `01_Casos_Uso_Calidad.docx` permanece sin cambios.
- Existe una copia de trabajo llamada `01_Casos_Uso_Priorizados.docx` en la carpeta corporativa.
- El documento de trabajo está abierto en Word y listo para completar.

**Verificación:**

- En el Explorador de archivos deben verse ambos documentos:
  - `01_Casos_Uso_Calidad.docx`
  - `01_Casos_Uso_Priorizados.docx`
- En la barra de título de Word debe aparecer `01_Casos_Uso_Priorizados.docx`.
- Si aparece el texto **Solo lectura**, revisa los permisos de la biblioteca o solicita apoyo al instructor antes de continuar.

---

### Paso 2. Revisar el escenario y separar hechos de supuestos

**Objetivo:** Identificar los hechos confirmados del escenario y reconocer la información que todavía requiere verificación técnica.

**Instrucciones:**

1. En el archivo `01_Casos_Uso_Priorizados.docx`, revisa el escenario de planta proporcionado por el instructor.
2. Identifica como mínimo los siguientes elementos del hilo conductor del curso:
   - Incremento de rechazos en la línea de ensamble.
   - No conformidades recurrentes relacionadas con torque.
   - Retrasos en el cierre de acciones correctivas o CAPA.
3. Crea, si no existe ya, una sección breve titulada:

   ```text
   Contexto validado del escenario
   ```

4. Registra en viñetas únicamente hechos confirmados en el archivo fuente. No agregues explicaciones que no estén respaldadas por el escenario.
5. Debajo, crea una segunda lista titulada:

   ```text
   Datos pendientes de confirmar
   ```

6. Incluye ejemplos de información que normalmente requeriría consulta a registros controlados, tales como:
   - Especificación aplicable de torque.
   - Identificación de herramientas usadas.
   - Estado de calibración de torquímetros.
   - Lotes o turnos afectados.
   - Registros de inspección.
   - Resultados de pruebas de verificación.
   - Evidencia de implementación y eficacia de una CAPA.
7. Asegúrate de no declarar que alguno de esos elementos está confirmado a menos que el documento fuente lo indique expresamente.

**Resultado esperado:**

El documento contiene una separación clara entre información confirmada y datos que deben investigarse o verificarse antes de tomar decisiones.

**Verificación:**

Comprueba que cada afirmación de la sección “Contexto validado del escenario” pueda rastrearse al archivo fuente o a una instrucción explícita del laboratorio. Las afirmaciones sin fuente confirmada deben trasladarse a “Datos pendientes de confirmar” o eliminarse.

> **Criterio de calidad:** Una salida de IA puede ser clara y bien redactada, pero no es evidencia objetiva si no está respaldada por registros, observaciones, mediciones, entrevistas u otros documentos controlados.

---

### Paso 3. Explorar oportunidades de uso con Microsoft 365 Copilot Chat

**Objetivo:** Utilizar Copilot para identificar aplicaciones posibles en el escenario, sin convertir hipótesis en hechos ni delegar decisiones críticas.

**Instrucciones:**

1. Abre Microsoft 365 Copilot Chat con tu cuenta corporativa.
2. Verifica que estás en el entorno corporativo autorizado y que no has iniciado sesión con una cuenta personal.
3. Introduce el siguiente prompt de exploración. Ajusta únicamente los datos que estén confirmados en el documento fuente:

   ```text
   Actúa como asistente de mejora continua en una planta de ensamble.

   Contexto confirmado:
   - Existe un incremento de rechazos en la línea de ensamble.
   - Hay no conformidades recurrentes relacionadas con torque.
   - Existen retrasos en el cierre de acciones CAPA.

   Propón casos de uso de Microsoft 365 Copilot para las siguientes actividades:
   1. Gestión de no conformidades.
   2. Análisis preliminar de causas.
   3. Auditorías internas.
   4. Seguimiento CAPA.
   5. Redacción de instructivos de trabajo.

   Para cada caso, indica:
   - Proceso.
   - Usuario principal.
   - Información de entrada que debe estar verificada.
   - Salida esperada.
   - Beneficio potencial.
   - Riesgo si la salida se utiliza sin revisión.
   - Validación humana requerida.

   No inventes valores de torque, causas raíz, registros de inspección, requisitos normativos ni acciones aprobadas. Distingue explícitamente entre borrador generado y evidencia objetiva.
   ```

4. Revisa la respuesta de Copilot. No copies el contenido directamente sin analizarlo.
5. Identifica propuestas que sean útiles para el escenario. Por ejemplo:
   - Preparar un borrador de reporte de no conformidad a partir de hechos confirmados.
   - Organizar preguntas para una investigación de causa.
   - Generar una lista de verificación de auditoría basada en criterios proporcionados.
   - Resumir el estado de acciones CAPA a partir de una lista validada.
   - Estructurar un borrador de instructivo de control de torque.
6. Identifica al menos dos elementos de la respuesta que requieran confirmación adicional. Por ejemplo:
   - Referencias a requisitos específicos no suministrados.
   - Sugerencias de causa raíz presentadas como si fueran conclusiones.
   - Recomendaciones de acción correctiva sin análisis de eficacia.
   - Suposiciones sobre responsables, fechas o datos de producción.
7. Regresa a Word y anota, en una sección de notas de trabajo o comentarios, los elementos que deberán ser validados antes de usar cualquier respuesta como documentación o decisión operativa.

**Resultado esperado:**

Dispones de una lista inicial de oportunidades de uso y de riesgos asociados a una respuesta no verificada.

**Verificación:**

La exploración es satisfactoria si puedes responder a estas preguntas:

- ¿La propuesta distingue entre datos de entrada verificados y contenido generado?
- ¿La respuesta evita afirmar una causa raíz sin evidencia?
- ¿Los usos identificados apoyan actividades humanas en lugar de reemplazar la aprobación del responsable?
- ¿Se mantuvo el escenario de no conformidad de torque como hilo conductor?

---

### Paso 4. Completar el registro de cinco casos de uso priorizados

**Objetivo:** Documentar como mínimo cinco casos de uso aplicables al escenario y establecer el control humano requerido para cada uno.

**Instrucciones:**

1. En `01_Casos_Uso_Priorizados.docx`, ubica la tabla proporcionada por el instructor. Si no existe, inserta una tabla con las siguientes columnas:

   | Prioridad | Caso de uso | Proceso | Usuario principal | Entrada disponible y verificable | Salida esperada | Beneficio esperado | Riesgo de uso sin revisión | Validación humana requerida |
   |---|---|---|---|---|---|---|---|---|

2. Completa al menos cinco filas, una para cada caso obligatorio:
   - Gestión de no conformidades.
   - Análisis preliminar de causas.
   - Auditorías internas.
   - Seguimiento CAPA.
   - Redacción de instructivos.

3. Conserva el caso de torque en todas las filas donde sea pertinente. Puedes incluir otros defectos de la base de calidad posteriormente, pero no sustituyas el caso de torque.
4. Usa como referencia el siguiente modelo de contenido. Adáptalo al formato del archivo fuente y evita presentar estos ejemplos como datos reales de planta.

| Prioridad | Caso de uso | Proceso | Usuario principal | Entrada disponible y verificable | Salida esperada | Beneficio esperado | Riesgo de uso sin revisión | Validación humana requerida |
|---|---|---|---|---|---|---|---|---|
| Alta | Borrador de reporte de no conformidad de torque | Gestión de calidad | Ingeniero o analista de calidad | Registro de hallazgo, producto afectado, fecha, requisito aplicable, estado de contención | Borrador estructurado con descripción objetiva, requisito incumplido, alcance inicial y datos pendientes | Reduce tiempo de preparación documental y mejora consistencia | Declarar causas, alcance o acciones no confirmadas | Responsable de calidad verifica datos contra registros y aprueba el documento conforme al procedimiento |
| Alta | Organización de preguntas para investigación de torque | Análisis de causas | Equipo multifuncional de mejora | Hallazgos confirmados, diagrama de proceso, registros de herramientas, datos de inspección disponibles | Lista de preguntas y plan preliminar de recolección de evidencia | Facilita una investigación ordenada | Confundir preguntas o hipótesis con causa raíz demostrada | Equipo técnico valida hipótesis con evidencia, pruebas y metodología de causa raíz |
| Media | Lista de verificación para auditoría de control de torque | Auditoría interna | Auditor interno | Criterios de auditoría, procedimiento vigente, requisito de control de torque y alcance de auditoría | Borrador de lista de verificación trazable a criterios suministrados | Mejora preparación y cobertura de la auditoría | Usar preguntas sin verificar vigencia documental o requisitos aplicables | Auditor competente valida criterios, evidencia esperada y alcance antes de usarla |
| Alta | Resumen del estado de acciones CAPA | Seguimiento CAPA | Responsable CAPA o líder de proceso | Registro CAPA con responsables, fechas, estado, evidencia de avance y acciones vencidas | Resumen de estado, acciones abiertas, compromisos y datos faltantes | Acelera reuniones de seguimiento | Interpretar una acción como cerrada sin evidencia de eficacia aprobada | Dueño de CAPA confirma estado, evidencia y cierre según procedimiento |
| Media | Borrador de instructivo para verificación de torque | Documentación operativa | Ingeniero de procesos o supervisor de producción | Procedimiento aprobado, especificación vigente, equipo autorizado y controles definidos | Borrador de instructivo con pasos, precauciones y puntos de verificación | Reduce tiempo de estructuración documental | Crear instrucciones incompatibles con el proceso aprobado o valores no autorizados | Ingeniería, calidad y control documental revisan, aprueban y liberan el instructivo |

5. En la columna **Entrada disponible y verificable**, escribe únicamente fuentes que puedan ser revisadas, como:
   - Registros de inspección.
   - Procedimientos vigentes.
   - Especificaciones aprobadas.
   - Reportes de no conformidad.
   - Registros CAPA.
   - Evidencias de auditoría.
   - Datos de producción autorizados.
6. En la columna **Riesgo de uso sin revisión**, registra un riesgo concreto, no una frase genérica. Ejemplos:
   - Atribuir una causa raíz sin pruebas.
   - Citar un procedimiento obsoleto.
   - Cerrar una acción CAPA sin evidencia de eficacia.
   - Incluir una instrucción no aprobada en un documento de operación.
7. En la columna **Validación humana requerida**, identifica el rol que revisa el resultado y la acción de validación. Ejemplos:
   - “Auditor interno verifica trazabilidad de cada pregunta al criterio aplicable.”
   - “Responsable de calidad compara el borrador con el registro de no conformidad.”
   - “Ingeniería de procesos verifica factibilidad técnica y control documental aprueba la versión.”
8. Asigna una prioridad inicial: **Alta**, **Media** o **Baja**. Considera como prioritarios los casos que atiendan el problema de torque, ayuden al cierre CAPA o reduzcan un riesgo importante de calidad.
9. Revisa que cada fila tenga todos los campos completos y comprensibles.

**Resultado esperado:**

La tabla contiene al menos cinco casos de uso completos, trazables y aplicables al escenario de planta.

**Verificación:**

Confirma que se cumplen los siguientes criterios:

- Hay al menos cinco filas completas.
- Están incluidos los cinco procesos obligatorios.
- Cada caso identifica un usuario principal.
- Cada caso indica entradas verificables y no solo “datos de planta”.
- Cada caso define una salida concreta, por ejemplo, borrador, resumen, lista de verificación o plan de preguntas.
- Cada caso presenta un riesgo específico.
- Cada caso asigna una validación humana clara.
- El caso de torque se mantiene como elemento trazable del lote.

---

### Paso 5. Aplicar una prueba breve de calidad a un prompt de exploración

**Objetivo:** Comparar una solicitud vaga con una solicitud estructurada para reconocer la influencia del contexto, las restricciones y la validación humana.

**Instrucciones:**

1. En Copilot Chat, introduce primero una solicitud deliberadamente vaga:

   ```text
   Analiza el problema de torque y dime qué hacer.
   ```

2. Observa la respuesta. Identifica posibles limitaciones, tales como:
   - Recomendaciones genéricas.
   - Ausencia de datos de entrada definidos.
   - Suposiciones sobre la causa del problema.
   - Acciones sugeridas sin validación ni criterios de aceptación.
   - Falta de delimitación entre contención, investigación y acción correctiva.
3. Ahora introduce una solicitud estructurada:

   ```text
   Actúa como asistente de calidad para preparar una exploración inicial, no una decisión técnica.

   Caso: no conformidades recurrentes de torque en una línea de ensamble.

   Usa únicamente los siguientes hechos confirmados:
   - Existen no conformidades recurrentes relacionadas con torque.
   - Se requiere investigar el problema y dar seguimiento a acciones CAPA.
   - No se ha confirmado una causa raíz.

   Tarea:
   Propón una lista de preguntas de investigación y fuentes de evidencia que un equipo de calidad e ingeniería debería revisar.

   Formato:
   1. Pregunta de investigación.
   2. Registro o fuente de evidencia a revisar.
   3. Rol que debería validar la información.
   4. Riesgo de asumir una respuesta sin evidencia.

   Restricciones:
   - No determines la causa raíz.
   - No inventes valores de torque ni requisitos técnicos.
   - No declares acciones correctivas como aprobadas.
   - Indica explícitamente qué información falta confirmar.
   ```

4. Compara ambas respuestas.
5. En el documento Word, agrega una sección titulada:

   ```text
   Observación sobre calidad de prompts
   ```

6. Redacta entre tres y cinco viñetas que expliquen por qué el segundo prompt es más adecuado. Incluye, como mínimo:
   - Contexto confirmado.
   - Tarea delimitada.
   - Formato esperado.
   - Restricciones explícitas.
   - Necesidad de revisión humana.

**Resultado esperado:**

El documento demuestra que una instrucción estructurada produce una salida más verificable y útil que una solicitud vaga.

**Verificación:**

La comparación es correcta si tu sección de observación indica que el prompt estructurado:

- Reduce la posibilidad de que Copilot invente datos.
- Separa preguntas de investigación de conclusiones técnicas.
- Define qué salida se necesita.
- Asigna controles de revisión humana.
- Facilita convertir la respuesta en un borrador utilizable, no en evidencia por sí misma.

---

### Paso 6. Priorizar los casos de uso según valor y riesgo

**Objetivo:** Determinar qué casos conviene abordar primero en la cadena de trabajo del curso.

**Instrucciones:**

1. Revisa las cinco filas de tu tabla de casos de uso.
2. Evalúa cada caso según los siguientes criterios:
   - Impacto potencial en el problema de torque.
   - Aporte al control de no conformidades.
   - Apoyo al seguimiento de CAPA.
   - Disponibilidad de entradas verificables.
   - Riesgo si se utiliza la salida sin validación.
   - Facilidad de revisión por un responsable competente.
3. Ajusta la prioridad de cada caso como **Alta**, **Media** o **Baja**.
4. Añade, debajo de la tabla, una sección titulada:

   ```text
   Casos priorizados para la cadena de trabajo
   ```

5. Selecciona los tres casos de uso con mayor prioridad.
6. Para cada uno, redacta una justificación de una o dos frases. Usa un formato similar al siguiente:

   ```text
   1. Gestión de no conformidades de torque — Prioridad alta.
      Justificación: permite estructurar información confirmada en un borrador de reporte y mejora la trazabilidad inicial del caso. Requiere revisión del responsable de calidad antes de su uso oficial.

   2. Seguimiento CAPA — Prioridad alta.
      Justificación: ayuda a identificar acciones abiertas, retrasos y datos faltantes a partir de registros controlados. El cierre solo puede aprobarse con evidencia de implementación y eficacia.

   3. Lista de verificación de auditoría de torque — Prioridad media o alta.
      Justificación: facilita la preparación de preguntas trazables a criterios definidos, pero el auditor debe validar la vigencia del procedimiento y la evidencia requerida.
   ```

7. Verifica que la priorización no se base solo en rapidez o facilidad de generación. Debe considerar el riesgo y la disponibilidad de evidencia.

**Resultado esperado:**

El documento identifica tres casos de uso prioritarios y justifica su selección considerando valor, evidencia y control humano.

**Verificación:**

Las justificaciones deben responder claramente:

- ¿Qué problema de calidad ayuda a atender el caso?
- ¿Qué resultado puede generar Copilot?
- ¿Qué evidencia o fuente controlada se necesita?
- ¿Quién debe revisar o aprobar el resultado?
- ¿Qué riesgo se controla mediante la validación humana?

---

### Paso 7. Revisar, guardar y confirmar la sincronización del entregable

**Objetivo:** Completar el entregable con trazabilidad, conservar el archivo en el repositorio corporativo y verificar que no se haya sobrescrito el archivo fuente.

**Instrucciones:**

1. Revisa que el documento contenga, como mínimo:
   - Contexto validado del escenario.
   - Datos pendientes de confirmar.
   - Tabla con cinco o más casos de uso.
   - Riesgos de utilización sin revisión.
   - Validación humana requerida por cada caso.
   - Observación sobre calidad de prompts.
   - Tres casos priorizados con justificación.
2. Revisa ortografía, claridad y consistencia de términos. Utiliza siempre “no conformidad”, “CAPA”, “evidencia objetiva”, “validación humana” y “torque” de manera coherente.
3. Elimina cualquier texto que presente una hipótesis como hecho confirmado.
4. Verifica que no hayas incluido información sensible no autorizada.
5. Guarda el documento usando **Archivo > Guardar**.
6. Cierra Word.
7. En el Explorador de archivos, confirma que el archivo tiene el nombre exacto:

   ```text
   01_Casos_Uso_Priorizados.docx
   ```

8. Espera a que OneDrive complete la sincronización.
9. Si tienes acceso a la biblioteca mediante el navegador, abre SharePoint Online y verifica que el archivo aparezca en:

   ```text
   /sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/
   ```

10. Confirma que `01_Casos_Uso_Calidad.docx` sigue existiendo y no ha sido reemplazado.

**Resultado esperado:**

El entregable está guardado, sincronizado en SharePoint Online y disponible para el siguiente laboratorio.

**Verificación:**

La práctica queda completada si se cumplen todos los puntos siguientes:

- El archivo se llama exactamente `01_Casos_Uso_Priorizados.docx`.
- El archivo está en la carpeta corporativa indicada.
- El archivo fuente no fue modificado ni eliminado.
- La tabla contiene cinco o más casos de uso.
- Cada caso incluye beneficio, riesgo y validación humana.
- El escenario de torque se conserva como hilo conductor.
- No se declara una causa raíz ni una acción correctiva como confirmada sin evidencia.

## Validación y pruebas

Realiza la siguiente lista de validación antes de entregar el archivo:

| Criterio de validación | Resultado esperado | Confirmación |
|---|---|---|
| Nombre del archivo | `01_Casos_Uso_Priorizados.docx` | ☐ |
| Ubicación | Biblioteca corporativa sincronizada de CopilotCalidad | ☐ |
| Archivo fuente protegido | `01_Casos_Uso_Calidad.docx` permanece disponible y sin sobrescritura | ☐ |
| Número de casos de uso | Cinco o más | ☐ |
| Casos obligatorios | Gestión de NC, análisis de causas, auditoría, CAPA e instructivos | ☐ |
| Hilo conductor | El caso de no conformidad de torque está incluido | ☐ |
| Entradas | Cada caso incluye registros, datos o documentos verificables | ☐ |
| Salidas | Cada caso define un borrador, resumen, lista o estructura concreta | ☐ |
| Riesgos | Cada caso identifica un riesgo específico de uso sin revisión | ☐ |
| Validación humana | Cada caso asigna un responsable o rol de revisión | ☐ |
| Uso responsable | No contiene datos sensibles no autorizados | ☐ |
| Control técnico | No presenta causas raíz, valores de torque ni acciones aprobadas sin evidencia | ☐ |

### Prueba de trazabilidad mínima

Selecciona uno de los casos de uso de prioridad alta y responde por escrito o verbalmente las siguientes preguntas:

1. ¿Qué proceso apoya este caso?
2. ¿Qué registros o documentos controlados requiere como entrada?
3. ¿Qué salida puede preparar Copilot?
4. ¿Qué no puede concluir Copilot con la información disponible?
5. ¿Qué rol humano debe validar el resultado?
6. ¿Qué evidencia sería necesaria antes de usar el contenido en una decisión de calidad?

La prueba se considera satisfactoria si puedes distinguir claramente entre:

- Información de entrada verificada.
- Borrador o propuesta generada por Copilot.
- Evidencia objetiva.
- Decisión o aprobación humana.

## Solución de problemas

### Problema 1: No aparece Copilot Chat o Word no muestra las funciones de Copilot

**Síntomas:**

- No se muestra el icono de Copilot en Word.
- Copilot Chat indica que no hay licencia disponible.
- El sistema solicita iniciar sesión repetidamente.
- Las funciones de Copilot aparecen deshabilitadas.

**Causa probable:**

La sesión se inició con una cuenta distinta de la cuenta corporativa autorizada, la licencia de Microsoft 365 Copilot no está asignada correctamente o la aplicación aún no ha actualizado el estado de la licencia.

**Solución:**

1. Cierra sesión en Word y en Microsoft 365 Copilot Chat.
2. Cierra completamente las aplicaciones de Microsoft 365.
3. Inicia sesión únicamente con tu cuenta corporativa de Microsoft Entra ID.
4. Abre Word y verifica la cuenta en **Archivo > Cuenta**.
5. Comprueba que tienes conexión a la red corporativa o VPN, si la política de la organización lo requiere.
6. Espera unos minutos y vuelve a abrir Word o Copilot Chat.
7. Si el problema continúa, registra el mensaje mostrado y contacta al administrador de Microsoft 365 o al instructor para verificar la asignación de licencia y permisos.

### Problema 2: El archivo no se sincroniza, aparece como solo lectura o no puede guardarse en la carpeta del curso

**Síntomas:**

- El archivo muestra un icono de sincronización permanente o un error de OneDrive.
- Word indica “Solo lectura” o “No se pudo guardar”.
- El archivo no aparece en SharePoint Online después de guardarlo.
- No se puede crear `01_Casos_Uso_Priorizados.docx` en la carpeta indicada.

**Causa probable:**

La biblioteca de SharePoint no está sincronizada correctamente, el usuario no tiene permisos de edición, existe un conflicto de nombre o OneDrive tiene una conexión interrumpida.

**Solución:**

1. Guarda temporalmente el documento abierto sin cambiar el nombre requerido ni moverlo a una ubicación personal.
2. Haz clic en el icono de OneDrive de la barra de tareas y revisa los errores de sincronización.
3. Confirma que has iniciado sesión en OneDrive con la misma cuenta corporativa utilizada en Word.
4. Abre SharePoint Online en el navegador y verifica que tienes permiso de edición en la biblioteca del curso.
5. Si ya existe un archivo con el mismo nombre creado por ti, revisa si está abierto en otra sesión de Word y cierra la copia duplicada.
6. Reintenta guardar en la carpeta oficial.
7. Si no tienes permisos de edición, solicita al instructor o al administrador del sitio que valide tu acceso; no utilices almacenamiento personal como alternativa.

## Limpieza

1. Cierra Copilot Chat y Microsoft Word cuando hayas confirmado la sincronización.
2. No elimines los archivos del curso ni modifiques el archivo fuente `01_Casos_Uso_Calidad.docx`.
3. Conserva únicamente el entregable requerido en la biblioteca corporativa:

   ```text
   01_Casos_Uso_Priorizados.docx
   ```

4. No descargues copias del archivo a dispositivos personales ni lo envíes a servicios externos.
5. Si creaste notas temporales fuera del documento oficial, elimínalas o incorpóralas al documento únicamente si son necesarias y están autorizadas.

## Resumen

En esta práctica identificaste oportunidades concretas para usar Microsoft 365 Copilot como asistente en procesos de calidad y mejora continua. Elaboraste un registro priorizado de casos de uso para gestión de no conformidades, análisis preliminar de causas, auditorías internas, seguimiento CAPA y redacción de instructivos.

También aplicaste el ciclo de trabajo responsable: definir la necesidad, aportar contexto confirmado, solicitar un resultado delimitado, verificar la salida y documentar la trazabilidad. El archivo `01_Casos_Uso_Priorizados.docx` será el insumo para el siguiente laboratorio, en el que transformarás estos casos de uso en prompts estructurados, verificables y orientados a resultados.

### Recursos opcionales

- [Microsoft Learn: Introducción a Microsoft 365 Copilot](https://learn.microsoft.com/es-es/copilot/microsoft-365/)
- [ISO 9001: Sistemas de gestión de la calidad](https://www.iso.org/standard/62085.html)
- [ISO/IEC 42001: Sistemas de gestión de inteligencia artificial](https://www.iso.org/standard/81230.html)
