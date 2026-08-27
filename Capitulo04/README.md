# Práctica: Generación automatizada de un reporte operativo 8D y un instructivo de proceso.

## Metadatos

| Elemento | Valor |
|---|---|
| Duración | 90 minutos |
| Complejidad | Media |
| Nivel de Bloom | Crear |
| Modalidad | Práctica individual con revisión humana obligatoria |
| Tecnologías | Microsoft Word con Copilot, Excel con Copilot, SharePoint Online, OneDrive for Business, reporte 8D, CAPA, control documental |

## Descripción general

En este laboratorio se utilizarán los resultados de los Laboratorios 01, 02 y 03 para generar dos borradores documentales vinculados con una no conformidad de torque en una línea de ensamble. El primer entregable será un reporte operativo 8D con secciones D1 a D8; el segundo será un instructivo operativo para la actividad de torque.

Microsoft 365 Copilot se empleará para estructurar, reformular y organizar contenido documentado. No se utilizará para inventar evidencias, causas raíz, parámetros de proceso, responsables, fechas, resultados de verificación ni aprobaciones. Todo dato no confirmado deberá quedar identificado como **“Pendiente de validación”** o **“Hipótesis por confirmar”**.

## Objetivos de aprendizaje

Al finalizar este laboratorio, podrá:

- [ ] Generar un borrador estructurado de reporte 8D a partir de información validada y evidencia disponible.
- [ ] Diferenciar entre hechos confirmados, hipótesis de investigación y datos pendientes de validación.
- [ ] Redactar un instructivo operativo de torque con pasos verificables, puntos de control, criterios de aceptación y reacción ante desviaciones.
- [ ] Aplicar Copilot en Word como apoyo de redacción sin sustituir la revisión técnica, aprobación ni control documental.
- [ ] Mantener trazabilidad entre la no conformidad, el análisis de datos, las acciones CAPA y los documentos generados.

## Prerrequisitos

### Conocimientos requeridos

Antes de iniciar, el participante debe:

- Haber completado los Laboratorios 01, 02 y 03.
- Comprender los conceptos básicos de no conformidad, CAPA, análisis de causa raíz, evidencia objetiva y metodología 8D.
- Conocer la diferencia entre un borrador de trabajo y un documento controlado aprobado.
- Comprender que Copilot puede asistir en la generación y transformación de texto, pero no valida automáticamente la veracidad de los datos.
- Tener conocimiento básico de Microsoft Word, Microsoft Excel, OneDrive for Business y SharePoint Online.

### Archivos y acceso requeridos

Debe disponer de los siguientes archivos en la carpeta oficial del curso:

- `01_Casos_Uso_Priorizados.docx`
- `02_Biblioteca_Prompts_Calidad.docx`
- `03_Analisis_Patrones_Validado.xlsx`
- Plantilla corporativa de reporte 8D o archivo modelo suministrado por el instructor.
- Plantilla corporativa de instructivo de trabajo o archivo modelo suministrado por el instructor.

También debe contar con:

- Cuenta corporativa de Microsoft Entra ID.
- Licencia activa de Microsoft 365 Copilot asignada.
- Acceso a Word, Excel, OneDrive for Business y SharePoint Online.
- Permisos de lectura y escritura en la biblioteca de SharePoint del curso.
- Acceso a la misma cuenta corporativa utilizada en los Laboratorios 01, 02 y 03.

> **Importante:** No utilice unidades personales, memorias USB, correos personales, servicios externos de IA ni ubicaciones no autorizadas para almacenar o procesar los archivos del laboratorio.

## Entorno del laboratorio

### Ubicación de trabajo oficial

La biblioteca corporativa de trabajo es:

```text
/sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/
```

En equipos Windows sincronizados mediante OneDrive for Business, la ruta local esperada es:

```text
C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
```

### Requisitos de hardware

| Componente | Requisito recomendado |
|---|---|
| Procesador | Intel Core i5 de 10.ª generación o AMD Ryzen 5 4000 Series, o superior |
| Memoria RAM | 8 GB como mínimo |
| Espacio libre | 20 GB como mínimo |
| Pantalla | Resolución mínima de 1920 x 1080 píxeles |
| Conectividad | Conexión corporativa estable de al menos 10 Mbps de descarga y 5 Mbps de carga |
| Audio | Funcional si se revisarán reuniones, transcripciones o resúmenes de Teams |

### Requisitos de software

| Software o servicio | Uso en el laboratorio |
|---|---|
| Windows 11 Enterprise | Sistema operativo de referencia |
| Microsoft Word con Copilot | Creación de los borradores 8D e instructivo |
| Microsoft Excel con Copilot | Consulta de datos y hallazgos validados |
| OneDrive for Business | Sincronización y almacenamiento local corporativo |
| SharePoint Online | Ubicación oficial de documentos |
| Microsoft 365 Copilot | Asistencia para estructuración, redacción y revisión |
| Adobe Acrobat Reader | Opcional, para consultar documentación de referencia en PDF |

### Verificación inicial de la carpeta de trabajo

1. Abra el Explorador de archivos de Windows.
2. Navegue a la ruta sincronizada:

   ```text
   C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
   ```

3. Confirme que los archivos de los Laboratorios 01, 02 y 03 estén disponibles.
4. Verifique que el icono de sincronización de OneDrive no indique errores.
5. Si desea validar la existencia de la ruta desde PowerShell, ejecute:

   ```powershell
   $RutaLab = "$env:USERPROFILE\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua"
   Test-Path $RutaLab
   ```

6. El resultado esperado es:

   ```text
   True
   ```

> Si la organización utiliza una denominación distinta para OneDrive, ubique la carpeta sincronizada desde el icono de OneDrive en la barra de tareas y use la ruta corporativa equivalente.

## Procedimiento paso a paso

### Paso 1. Preparar los archivos fuente y confirmar la trazabilidad del caso

**Objetivo:** Identificar el caso de torque, sus datos validados, sus evidencias disponibles y los límites de información que Copilot podrá utilizar.

**Instrucciones:**

1. Abra `01_Casos_Uso_Priorizados.docx` en Microsoft Word.
2. Localice el caso priorizado relacionado con la no conformidad de torque en la línea de ensamble.
3. Registre en una nota de trabajo temporal los siguientes elementos, únicamente si aparecen documentados:
   - ID de la no conformidad.
   - Fecha o periodo del hallazgo.
   - Línea, proceso, producto y turno involucrados.
   - Descripción objetiva de la desviación.
   - Requisito incumplido o criterio aplicable.
   - Responsable o área asignada.
   - Riesgo asociado, si fue documentado.
4. Abra `03_Analisis_Patrones_Validado.xlsx`.
5. Confirme que la tabla principal se denomina exactamente:

   ```text
   tblNoConformidades
   ```

6. Revise los registros relacionados con torque mediante filtros en las columnas disponibles, por ejemplo:
   - `Tipo_Defecto`
   - `Proceso`
   - `Línea`
   - `Turno`
   - `Producto`
   - `Severidad`
   - `Estado_CAPA`
7. Identifique los hallazgos que hayan sido validados en el Laboratorio 03, tales como patrones por línea, turno, producto, severidad, costo estimado o tendencia.
8. Abra `02_Biblioteca_Prompts_Calidad.docx`.
9. Localice los prompts estructurados creados o validados en el Laboratorio 02 para:
   - Reporte 8D.
   - Análisis de causas.
   - Acciones CAPA.
   - Procedimientos o instructivos de trabajo.
10. Cree una lista de tres categorías para organizar la información:
    - **Hechos confirmados:** información respaldada por archivos, registros o análisis validado.
    - **Hipótesis por confirmar:** relaciones o causas potenciales sin demostración suficiente.
    - **Pendiente de validación:** campos obligatorios sin datos disponibles.

**Resultado esperado:**

Una lista de trabajo con información trazable sobre el caso de torque, separada claramente entre evidencia confirmada, hipótesis y datos faltantes.

**Verificación:**

- Puede relacionar el caso de torque con un registro, filtro o hallazgo presente en `tblNoConformidades`.
- No ha convertido una correlación estadística o una observación aislada en causa raíz.
- Puede indicar la fuente de cada hecho confirmado: Laboratorio 01, Laboratorio 03, registro de inspección, procedimiento o evidencia corporativa.
- Los datos no disponibles están identificados como pendientes y no se han completado por suposición.

---

### Paso 2. Crear la estructura controlada del borrador 8D

**Objetivo:** Crear un documento de trabajo con la estructura D1 a D8, control documental básico y campos trazables antes de solicitar asistencia a Copilot.

**Instrucciones:**

1. Abra la plantilla corporativa de reporte 8D o el archivo modelo suministrado por el instructor.
2. Guarde una copia en la carpeta oficial con el nombre exacto:

   ```text
   04_Reporte_8D_Borrador.docx
   ```

3. No sobrescriba la plantilla original ni los archivos fuente de laboratorios anteriores.
4. Complete, cuando exista información documentada, los campos de identificación del documento:
   - Título: `Borrador de reporte 8D – No conformidad de torque`.
   - ID de no conformidad.
   - Proceso o línea.
   - Fecha de elaboración.
   - Elaborado por.
   - Estado documental: `BORRADOR – Pendiente de revisión técnica y aprobación`.
5. Mantenga el código, número de revisión y aprobaciones como **“Pendiente de validación”** si deben ser asignados mediante el sistema formal de control documental.
6. Cree o confirme las siguientes secciones:

   | Sección | Contenido requerido |
   |---|---|
   | D1 | Formación del equipo |
   | D2 | Descripción del problema |
   | D3 | Acciones de contención inmediata |
   | D4 | Análisis de causa raíz y causa de escape |
   | D5 | Acciones correctivas permanentes |
   | D6 | Verificación de implementación y efectividad |
   | D7 | Prevención de recurrencia y estandarización |
   | D8 | Reconocimiento, cierre y lecciones aprendidas |

7. Debajo de cada sección, agregue inicialmente una tabla o subtítulos con los campos:
   - Hecho o acción.
   - Evidencia o fuente.
   - Responsable.
   - Fecha o plazo.
   - Estado.
   - Observaciones de validación.
8. Inserte una nota visible al inicio del documento:

   > Este documento es un borrador generado y revisado con apoyo de Microsoft 365 Copilot. No constituye un documento controlado ni evidencia aprobada hasta completar la revisión técnica, validación de datos, aprobación y control de cambios conforme al sistema de calidad aplicable.

**Resultado esperado:**

Un archivo `04_Reporte_8D_Borrador.docx` con estructura D1 a D8, estado de borrador y campos destinados a soportar trazabilidad y revisión.

**Verificación:**

- El archivo está almacenado en la carpeta corporativa oficial.
- El documento contiene las ocho disciplinas D1 a D8.
- La portada o encabezado identifica que el documento es un borrador.
- No se han agregado aprobaciones, firmas, fechas de cierre o números de revisión ficticios.
- Cada sección permite registrar evidencia, responsable y estado.

---

### Paso 3. Generar el primer borrador del reporte 8D con Copilot en Word

**Objetivo:** Utilizar Copilot para transformar los hechos confirmados en un borrador estructurado, objetivo y revisable.

**Instrucciones:**

1. En `04_Reporte_8D_Borrador.docx`, ubique el cursor después de la estructura D1 a D8 o en la sección que deba desarrollarse.
2. Abra Copilot en Word desde la cinta de opciones o el panel lateral, según la versión disponible en su entorno corporativo.
3. Copie y adapte el siguiente prompt. Reemplace los campos entre corchetes exclusivamente con información validada:

   ```text
   Actúa como asistente de redacción para documentación de calidad. Redacta un borrador de reporte 8D para una no conformidad de torque en una línea de ensamble.

   Propósito: organizar información disponible para revisión humana; no generar un documento aprobado.

   Usa exclusivamente los hechos confirmados incluidos a continuación y conserva una redacción objetiva, clara y profesional.

   Hechos confirmados:
   - ID de no conformidad: [ID_NC confirmado]
   - Fecha o periodo: [fecha o periodo confirmado]
   - Línea/proceso/producto/turno: [datos confirmados]
   - Descripción de la desviación: [descripción objetiva confirmada]
   - Requisito o criterio aplicable: [requisito confirmado]
   - Datos validados del análisis: [hallazgos de 03_Analisis_Patrones_Validado.xlsx]
   - Contención documentada: [acciones confirmadas]
   - Responsables ya asignados: [solo responsables confirmados]
   - Evidencia disponible: [registros, informes, fotos, órdenes, inspecciones u otras fuentes confirmadas]

   Estructura obligatoria:
   D1 Equipo
   D2 Descripción del problema
   D3 Acciones de contención
   D4 Análisis de causa raíz y causa de escape
   D5 Acciones correctivas permanentes
   D6 Verificación de implementación y efectividad
   D7 Prevención de recurrencia
   D8 Reconocimiento y cierre

   Restricciones obligatorias:
   - No inventes nombres, fechas, valores de torque, límites de especificación, responsables, resultados, evidencias ni aprobaciones.
   - Distingue de forma explícita los hechos confirmados de las hipótesis.
   - Cuando falte evidencia, usa exactamente “Pendiente de validación”.
   - Cuando exista una causa posible aún no demostrada, usa exactamente “Hipótesis por confirmar”.
   - No declares una causa raíz como confirmada sin evidencia de investigación.
   - No declares efectividad, cierre CAPA ni cierre 8D si no existe evidencia validada.
   - Incluye referencias a las fuentes disponibles entre corchetes, por ejemplo: [Fuente: 03_Analisis_Patrones_Validado.xlsx].
   - Propón tablas cuando ayuden a revisar responsables, acciones, evidencia, plazos y estado.

   Entrega el contenido en español y con tono técnico, objetivo y apto para revisión de calidad.
   ```

4. Revise el texto propuesto por Copilot antes de insertarlo o conservarlo en el documento.
5. Si Copilot genera información no documentada, elimínela o reemplácela por:
   - `Pendiente de validación`, si falta un dato objetivo.
   - `Hipótesis por confirmar`, si se trata de una posible relación causal sin evidencia suficiente.
6. Inserte o conserve únicamente el contenido que pueda cotejar con las fuentes de trabajo.
7. Asegúrese de que D1 incluya funciones necesarias, sin inventar personas. Ejemplo de redacción aceptable:

   > Líder de investigación: Pendiente de validación.  
   > Representante de calidad: Pendiente de validación.  
   > Representante de producción: Pendiente de validación.  
   > Mantenimiento/ingeniería: Pendiente de validación.

8. En D2, mantenga una descripción basada en qué ocurrió, dónde ocurrió, cuándo se detectó, alcance conocido, requisito incumplido y evidencia.
9. En D3, incluya únicamente medidas de contención realmente documentadas. Si no se conoce su estado o fecha, indíquelo explícitamente.
10. Guarde el documento.

**Resultado esperado:**

Un borrador 8D con contenido inicial para D1, D2 y D3, y con las secciones D4 a D8 estructuradas sin presentar hipótesis o datos no confirmados como hechos.

**Verificación:**

- Cada afirmación relevante puede vincularse a una fuente existente.
- D2 describe el problema sin atribuir una causa no comprobada.
- D3 no afirma que una contención fue efectiva si no hay resultado documentado.
- D4 diferencia las causas potenciales de una causa raíz validada.
- El documento contiene etiquetas de pendiente o hipótesis cuando corresponde.

---

### Paso 4. Completar D4 a D8 con enfoque verificable y controlado

**Objetivo:** Convertir el contenido generado en una propuesta de investigación y mejora que mantenga la trazabilidad necesaria para CAPA y auditoría.

**Instrucciones:**

1. Revise la sección D4 del reporte 8D.
2. Identifique si existen resultados documentados de herramientas de análisis, por ejemplo:
   - Cinco porqués.
   - Diagrama de Ishikawa.
   - Revisión de parámetros de torque.
   - Verificación de calibración de herramienta.
   - Revisión de instrucciones de trabajo.
   - Análisis por línea, turno, producto o proceso.
   - Registros de capacitación.
3. Si el análisis no ha confirmado una causa raíz, mantenga una tabla como la siguiente:

   | Causa potencial | Evidencia disponible | Estado de validación | Acción de investigación |
   |---|---|---|---|
   | [Causa potencial] | [Fuente o dato] | Hipótesis por confirmar | [Prueba o revisión requerida] |

4. No use frases como “la causa raíz fue” a menos que exista evidencia documentada y validada.
5. En D5, formule acciones correctivas permanentes únicamente como propuestas o acciones aprobadas según el estado real. Utilice una tabla:

   | Acción correctiva propuesta o aprobada | Responsable | Plazo | Evidencia de implementación | Estado |
   |---|---|---|---|---|
   | [Acción] | [Responsable confirmado o Pendiente de validación] | [Fecha confirmada o Pendiente de validación] | [Registro requerido] | [Estado] |

6. Si Copilot propone acciones tales como recalibrar una herramienta, cambiar un parámetro, modificar una especificación o capacitar personal, no las acepte automáticamente. Confirme que:
   - La acción es técnicamente viable.
   - El responsable tiene autoridad definida.
   - La acción no altera un proceso controlado sin gestión formal de cambios.
   - Existen criterios verificables para demostrar su implementación.
7. En D6, defina cómo se verificará la implementación y cómo se medirá la efectividad. No declare resultados si aún no se han obtenido.
8. Incluya criterios de verificación solo cuando estén definidos por el proceso o puedan ser aprobados posteriormente. Ejemplos de redacción aceptable:
   - `Pendiente de validación: definir periodo de seguimiento posterior a la implementación.`
   - `Pendiente de validación: confirmar tamaño de muestra y criterio de aceptación conforme al plan de control aplicable.`
   - `Verificar existencia de registros de capacitación y liberación de la instrucción revisada.`
9. En D7, documente acciones de prevención de recurrencia que afecten al sistema, tales como actualización de instructivos, planes de control, listas de verificación, capacitación o revisión de mantenimiento preventivo. Marque como pendiente toda modificación no aprobada.
10. En D8, incluya reconocimiento, lecciones aprendidas y cierre solo si existen elementos confirmados. Si el caso sigue abierto, indique:

    > Estado de cierre: Pendiente de validación. El cierre formal requiere evidencia de implementación, resultados de efectividad, revisión técnica y aprobación conforme al procedimiento CAPA aplicable.

11. Utilice Copilot para mejorar la consistencia del texto sin alterar hechos. Puede usar este prompt:

   ```text
   Revisa el texto seleccionado para mejorar claridad, consistencia terminológica y tono técnico. No agregues datos, conclusiones, responsables, fechas, parámetros, acciones ni evidencias. Conserva literalmente las etiquetas “Pendiente de validación” e “Hipótesis por confirmar”. Señala cualquier frase que parezca presentar una hipótesis como hecho confirmado.
   ```

12. Revise manualmente cada modificación sugerida.
13. Guarde el archivo.

**Resultado esperado:**

Un reporte 8D borrador completo desde D1 hasta D8, con acciones, responsables, evidencia y estados documentados o etiquetados de forma explícita cuando falten datos.

**Verificación:**

- D4 contiene evidencia, hipótesis y pruebas de validación claramente diferenciadas.
- D5 no presenta propuestas como acciones implementadas.
- D6 no presenta efectividad sin medición documentada.
- D7 relaciona la prevención con documentos, controles o prácticas del sistema de calidad.
- D8 no declara cierre formal sin la aprobación correspondiente.
- El documento conserva una redacción objetiva y trazable.

---

### Paso 5. Crear el borrador del instructivo operativo de torque

**Objetivo:** Preparar un instructivo de trabajo claro, verificable y vinculado con el caso de no conformidad de torque.

**Instrucciones:**

1. Abra la plantilla corporativa de instructivo de trabajo o el archivo modelo proporcionado por el instructor.
2. Guarde una copia en la carpeta oficial con el nombre exacto:

   ```text
   04_Instructivo_Torque_Borrador.docx
   ```

3. No reutilice ni sobrescriba el archivo del reporte 8D.
4. Complete la información de identificación disponible:
   - Título: `Instructivo operativo de torque – Borrador`.
   - Área o proceso aplicable.
   - Línea o estación, si está confirmada.
   - Relación con la no conformidad: `[ID_NC confirmado]`.
   - Estado documental: `BORRADOR – Pendiente de revisión técnica, validación y aprobación`.
5. Inserte las siguientes secciones obligatorias:

   | Sección | Propósito |
   |---|---|
   | Propósito | Indicar por qué existe el instructivo |
   | Alcance | Definir proceso, estación, producto o familia aplicable |
   | Responsabilidades | Identificar roles, no personas no confirmadas |
   | Seguridad | Identificar requisitos y riesgos aplicables |
   | Materiales, equipos y herramientas | Listar recursos requeridos |
   | Precondiciones | Definir verificaciones antes de iniciar |
   | Secuencia de trabajo | Describir pasos observables y verificables |
   | Parámetros críticos | Documentar parámetros aprobados o pendientes |
   | Criterios de aceptación | Definir condiciones para aceptar el trabajo |
   | Reacción ante desviación | Definir contención, escalamiento y registro |
   | Registros requeridos | Identificar evidencias que deben conservarse |
   | Control de revisión | Incluir control documental y aprobación |

6. Revise los documentos fuente para identificar parámetros y controles realmente disponibles.
7. No introduzca valores de torque, tolerancias, números de herramienta, frecuencias de calibración o métodos de inspección si no están respaldados por documentación vigente.
8. Si un parámetro crítico no está disponible, use una formulación como:

   > Parámetro de torque aplicable: Pendiente de validación contra la especificación de producto, plan de control e instrucción técnica vigente.

9. Inserte una nota de uso controlado:

   > Este documento es un borrador de trabajo. No debe utilizarse como instrucción operativa liberada hasta que sea revisado técnicamente, aprobado y publicado mediante el proceso corporativo de control documental.

**Resultado esperado:**

Un archivo `04_Instructivo_Torque_Borrador.docx` con la estructura completa de un instructivo operativo y con relación explícita al caso de no conformidad de torque.

**Verificación:**

- El nombre del archivo es exacto.
- El instructivo identifica su condición de borrador.
- La estructura incluye seguridad, parámetros críticos, criterios de aceptación, reacción ante desviación, registros y control de revisión.
- No existen parámetros técnicos inventados.
- Existe una referencia al ID de la no conformidad cuando dicho ID está confirmado.

---

### Paso 6. Generar y revisar la secuencia operativa con Copilot

**Objetivo:** Emplear Copilot para redactar una secuencia de trabajo verificable sin sustituir la validación técnica de ingeniería, producción o calidad.

**Instrucciones:**

1. En `04_Instructivo_Torque_Borrador.docx`, coloque el cursor en la sección de secuencia de trabajo.
2. Abra Copilot en Word.
3. Utilice el siguiente prompt y complete únicamente los datos confirmados:

   ```text
   Redacta un borrador de instructivo operativo para una operación de torque en una línea de ensamble.

   Finalidad: convertir información disponible en una secuencia de trabajo clara, verificable y apta para revisión técnica.

   Información confirmada:
   - Proceso o estación: [dato confirmado]
   - Producto o familia de producto: [dato confirmado]
   - Herramienta autorizada: [dato confirmado o “Pendiente de validación”]
   - Parámetro de torque: [valor aprobado con unidad o “Pendiente de validación”]
   - Método de verificación: [dato confirmado o “Pendiente de validación”]
   - Criterio de aceptación: [dato confirmado o “Pendiente de validación”]
   - Registros requeridos: [datos confirmados]
   - Riesgos de seguridad documentados: [datos confirmados]
   - Reacción ante desviación documentada: [datos confirmados]
   - Relación con no conformidad: [ID_NC confirmado]

   Estructura obligatoria:
   1. Propósito
   2. Alcance
   3. Responsabilidades
   4. Seguridad
   5. Materiales, equipos y herramientas
   6. Precondiciones
   7. Secuencia de trabajo numerada
   8. Parámetros críticos
   9. Criterios de aceptación
   10. Reacción ante desviación
   11. Registros requeridos
   12. Control de revisión

   Reglas obligatorias:
   - Usa verbos de acción claros y pasos observables.
   - Cada paso debe permitir verificación por un supervisor o auditor.
   - No inventes valores de torque, tolerancias, herramientas, frecuencias, responsables, equipos de protección, registros o criterios de aceptación.
   - Para información faltante usa exactamente “Pendiente de validación”.
   - Si una relación con la no conformidad es posible pero no demostrada, usa “Hipótesis por confirmar”.
   - No declares que el proceso está aprobado, liberado o conforme.
   - Incluye una reacción explícita ante desviación: detener según corresponda, segregar el producto afectado, identificar el estado, registrar y escalar al rol definido, solo si estos elementos están documentados; de lo contrario, marcarlos como “Pendiente de validación”.
   - Redacta en español técnico, claro y conciso.
   ```

4. Revise la propuesta antes de incorporarla al documento.
5. Para cada paso operativo, confirme que responde a estas preguntas:
   - ¿Qué debe hacer la persona?
   - ¿Con qué equipo, herramienta o registro?
   - ¿Qué debe verificar?
   - ¿Cuál es el criterio de aceptación?
   - ¿Qué debe hacer si se detecta una desviación?
6. Ajuste los pasos para evitar instrucciones ambiguas. Por ejemplo, reemplace frases genéricas como “realizar el torque correctamente” por una redacción verificable, condicionada a la información disponible:

   > Verificar que la herramienta de torque autorizada se encuentre identificada y en condición vigente conforme al sistema de calibración aplicable. Estado de vigencia específico: Pendiente de validación.

7. Si el valor de torque está aprobado y documentado, indique el valor, unidad, fuente y tolerancia conforme a la especificación vigente.
8. Si el valor no está disponible, no use ejemplos numéricos ni intervalos estimados.
9. Agregue una tabla de parámetros críticos:

   | Parámetro o punto de control | Requisito aplicable | Método de verificación | Registro | Estado |
   |---|---|---|---|---|
   | Torque | Pendiente de validación o valor confirmado | Pendiente de validación o método confirmado | Registro aplicable | Pendiente de validación o confirmado |
   | Herramienta autorizada | Pendiente de validación o identificación confirmada | Inspección visual/documental | Registro aplicable | Pendiente de validación o confirmado |
   | Condición de calibración | Pendiente de validación o criterio confirmado | Verificación de identificación | Registro aplicable | Pendiente de validación o confirmado |

10. Agregue una tabla de reacción ante desviación:

   | Desviación detectada | Acción inmediata | Segregación/identificación | Escalamiento | Registro |
   |---|---|---|---|---|
   | Resultado de torque fuera de criterio | Pendiente de validación o acción confirmada | Pendiente de validación o acción confirmada | Pendiente de validación o rol confirmado | Pendiente de validación o registro confirmado |

11. Guarde el documento.

**Resultado esperado:**

Un instructivo de torque con una secuencia de trabajo numerada, verificable y basada en información confirmada, sin parámetros o responsabilidades ficticias.

**Verificación:**

- Los pasos están redactados con verbos de acción observables.
- Cada parámetro técnico cuenta con fuente confirmada o etiqueta de pendiente.
- La reacción ante desviación no libera producto ni establece acciones no autorizadas.
- El documento identifica los registros requeridos o marca su definición como pendiente.
- El instructivo no se presenta como documento liberado.

---

### Paso 7. Ejecutar la revisión humana de trazabilidad, objetividad y control documental

**Objetivo:** Validar que los dos borradores sean utilizables como documentos de trabajo y que no contengan contenido generado sin respaldo.

**Instrucciones:**

1. Abra simultáneamente:
   - `04_Reporte_8D_Borrador.docx`
   - `04_Instructivo_Torque_Borrador.docx`
   - `03_Analisis_Patrones_Validado.xlsx`
   - `01_Casos_Uso_Priorizados.docx`
2. Revise el reporte 8D aplicando los siguientes controles:

   | Control | Pregunta de revisión |
   |---|---|
   | Claridad | ¿La descripción del problema puede entenderse sin ambigüedad? |
   | Objetividad | ¿Distingue hechos de hipótesis y opiniones? |
   | Trazabilidad | ¿Cada afirmación crítica tiene una fuente, referencia o estado pendiente? |
   | Consistencia | ¿Usa el mismo ID, proceso, línea y terminología en todo el documento? |
   | Control documental | ¿Está identificado como borrador y sin aprobación ficticia? |
   | Acción CAPA | ¿Las acciones tienen responsable, plazo, evidencia o estado pendiente? |

3. Revise el instructivo aplicando los siguientes controles:

   | Control | Pregunta de revisión |
   |---|---|
   | Propósito y alcance | ¿Define dónde y para qué aplica el instructivo? |
   | Seguridad | ¿Evita inventar requisitos de seguridad? |
   | Secuencia | ¿Los pasos son observables y verificables? |
   | Parámetros críticos | ¿Los valores provienen de fuentes vigentes o están marcados como pendientes? |
   | Aceptación | ¿Los criterios están definidos o correctamente etiquetados? |
   | Desviación | ¿Describe contención, identificación, escalamiento y registro según información disponible? |
   | Registros | ¿Identifica la evidencia requerida para demostrar ejecución? |
   | Control documental | ¿Indica revisión, aprobación y publicación pendientes? |

4. Use Copilot únicamente como apoyo de revisión textual mediante el siguiente prompt:

   ```text
   Analiza el documento seleccionado como borrador de calidad. Identifica:
   1. afirmaciones que parezcan no tener evidencia explícita;
   2. posibles contradicciones entre hechos, hipótesis y acciones;
   3. campos obligatorios faltantes;
   4. términos ambiguos o no verificables;
   5. frases que podrían interpretarse como aprobación, cierre o efectividad sin evidencia.

   No reescribas el contenido ni inventes información. Devuelve una lista de observaciones para revisión humana.
   ```

5. Revise cada observación de Copilot contra los archivos fuente.
6. Corrija únicamente los elementos que pueda validar.
7. Registre al final de cada documento una breve sección titulada `Observaciones de revisión interna`, con:
   - Fecha de revisión.
   - Revisor.
   - Cambios realizados.
   - Pendientes para validación técnica.
8. Guarde ambos archivos.
9. Confirme que OneDrive haya sincronizado los cambios con SharePoint.

**Resultado esperado:**

Dos borradores coherentes entre sí, vinculados al mismo caso de torque y preparados para ser utilizados como entrada del Laboratorio 05.

**Verificación:**

- El ID de no conformidad, proceso y terminología son consistentes entre ambos documentos.
- El reporte 8D no presenta acciones como completadas sin evidencia.
- El instructivo no incorpora valores de torque o límites no confirmados.
- Los pendientes de información están visibles y no ocultos en comentarios informales.
- Los archivos muestran estado de sincronización correcto en OneDrive.

## Validación y pruebas

Complete la siguiente lista de validación antes de finalizar el laboratorio.

### Validación del reporte 8D

- [ ] El archivo se llama exactamente `04_Reporte_8D_Borrador.docx`.
- [ ] El archivo está almacenado en la carpeta oficial de SharePoint/OneDrive del curso.
- [ ] El reporte incluye las secciones D1, D2, D3, D4, D5, D6, D7 y D8.
- [ ] La no conformidad de torque se identifica de forma consistente con el caso de los laboratorios anteriores.
- [ ] D2 contiene una descripción objetiva del problema y el requisito incumplido, cuando están disponibles.
- [ ] D3 documenta únicamente acciones de contención confirmadas.
- [ ] D4 separa causas potenciales, evidencia y estado de validación.
- [ ] D5 identifica acciones propuestas o aprobadas sin afirmar implementación no demostrada.
- [ ] D6 no declara efectividad si no existe evidencia de resultados.
- [ ] D7 vincula las acciones preventivas con documentos, controles o prácticas del sistema.
- [ ] D8 no declara el cierre formal sin revisión y aprobación.
- [ ] Los campos sin evidencia están etiquetados como `Pendiente de validación`.
- [ ] Las causas no demostradas están etiquetadas como `Hipótesis por confirmar`.
- [ ] El documento está identificado como borrador y no contiene firmas, revisiones o aprobaciones ficticias.

### Validación del instructivo operativo de torque

- [ ] El archivo se llama exactamente `04_Instructivo_Torque_Borrador.docx`.
- [ ] El instructivo contiene propósito, alcance, responsabilidades, seguridad, materiales, precondiciones y secuencia de trabajo.
- [ ] Incluye parámetros críticos, criterios de aceptación, reacción ante desviación, registros requeridos y control de revisión.
- [ ] Los pasos operativos están numerados y describen acciones observables.
- [ ] Los parámetros de torque y tolerancias se sustentan en documentación vigente o se marcan como pendientes.
- [ ] El instructivo no inventa herramientas, frecuencias de calibración, equipos de protección ni criterios de aceptación.
- [ ] La reacción ante desviación contempla acciones documentadas o marca explícitamente los elementos pendientes.
- [ ] El instructivo está relacionado con el caso de no conformidad de torque.
- [ ] El documento se identifica como borrador pendiente de validación técnica y aprobación.
- [ ] Los archivos están sincronizados en OneDrive y disponibles en SharePoint.

### Prueba de trazabilidad cruzada

Verifique manualmente las siguientes relaciones:

| Elemento a contrastar | Evidencia esperada |
|---|---|
| Caso priorizado del Laboratorio 01 | El mismo caso de torque aparece identificado en el reporte 8D y el instructivo. |
| Biblioteca de prompts del Laboratorio 02 | Los prompts utilizados incluyen propósito, estructura, hechos, restricciones y criterios de validación. |
| Análisis del Laboratorio 03 | Los patrones o datos citados en el 8D provienen de `tblNoConformidades` o de hallazgos validados. |
| Reporte 8D | Las acciones o controles propuestos pueden relacionarse con el instructivo de torque. |
| Instructivo de torque | Los puntos de control y reacciones ante desviación apoyan las acciones de prevención o corrección del 8D. |

> **Criterio de aceptación del laboratorio:** Los dos entregables deben ser borradores trazables, objetivos y revisables. No se exige que todas las causas, acciones o parámetros estén cerrados; se exige que las ausencias de evidencia estén declaradas correctamente.

## Solución de problemas

### Problema 1: Copilot no aparece en Word o no puede generar contenido

**Síntomas:**

- No se visualiza el botón o panel de Copilot en Word.
- Aparece un mensaje de que Copilot no está disponible.
- Copilot no procesa el prompt o devuelve un error de acceso.

**Causa probable:**

La sesión de Word no está iniciada con la cuenta corporativa correcta, la licencia de Microsoft 365 Copilot no está asignada o activa, la aplicación no puede conectarse al servicio corporativo, o la versión de Word no cumple la configuración administrada por la organización.

**Solución:**

1. En Word, seleccione **Archivo > Cuenta**.
2. Confirme que inició sesión con la cuenta corporativa de Microsoft Entra ID asignada al curso.
3. Verifique que la suscripción de Microsoft 365 Apps esté activa.
4. Cierre Word y vuelva a abrirlo desde Microsoft 365 o desde el acceso corporativo.
5. Compruebe la conexión corporativa a Internet y, si aplica, conéctese a la VPN corporativa autorizada.
6. Si el problema persiste, registre el mensaje de error y solicite soporte al administrador de Microsoft 365 o al instructor. No sustituya Copilot con un servicio externo de IA.

### Problema 2: OneDrive muestra conflicto de sincronización o los documentos no aparecen en SharePoint

**Síntomas:**

- El archivo tiene un icono de advertencia, nube con error o conflicto.
- Se visualizan varias copias del mismo documento.
- Los cambios realizados localmente no aparecen en la biblioteca de SharePoint.
- El archivo se abre como solo lectura sin razón aparente.

**Causa probable:**

Existe una edición simultánea, conflicto de versiones, falta de conectividad, sesión de OneDrive desactualizada o el archivo fue guardado fuera de la carpeta sincronizada oficial.

**Solución:**

1. Guarde el documento y cierre Word para evitar ediciones simultáneas.
2. Seleccione el icono de OneDrive en la barra de tareas y revise la actividad de sincronización.
3. Confirme que el archivo se encuentre dentro de:

   ```text
   OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
   ```

4. Abra la biblioteca de SharePoint en el navegador y compare la fecha de modificación con la versión local.
5. Si existe conflicto, no elimine versiones. Compare el contenido y conserve la versión que incluya los cambios válidos.
6. Renombre copias de conflicto solo si es necesario para análisis, sin alterar los nombres finales requeridos.
7. Cuando se resuelva el conflicto, confirme que los archivos finales mantengan exactamente estos nombres:
   - `04_Reporte_8D_Borrador.docx`
   - `04_Instructivo_Torque_Borrador.docx`

## Limpieza

1. Guarde ambos entregables en la carpeta corporativa oficial.
2. Confirme que OneDrive haya sincronizado correctamente los archivos.
3. Cierre Word y Excel después de verificar que no existan cambios sin guardar.
4. Elimine únicamente notas temporales locales que no formen parte de la evidencia o de los entregables requeridos.
5. No elimine, renombre ni sobrescriba:
   - Los archivos fuente de los Laboratorios 01, 02 y 03.
   - Las plantillas corporativas originales.
   - Los dos archivos de salida requeridos.
6. Mantenga disponibles los archivos finales para su uso en el Laboratorio 05:
   - `04_Reporte_8D_Borrador.docx`
   - `04_Instructivo_Torque_Borrador.docx`

## Resumen

En este laboratorio se generaron dos borradores de documentación de calidad vinculados a una no conformidad de torque: un reporte operativo 8D y un instructivo de proceso. Copilot se utilizó para acelerar la estructuración y redacción, mientras que la validación humana se aplicó para asegurar objetividad, trazabilidad, consistencia y control documental.

Los documentos resultantes no representan aprobaciones ni evidencia final de cierre. Su función es servir como borradores controlados de trabajo para contrastar causas potenciales, validar acciones CAPA y ajustar las mejoras durante el Laboratorio 05.

### Recursos opcionales

- [Microsoft Support: Uso de Copilot en Word](https://support.microsoft.com/es-es/copilot-word)
- [ISO 9001 — Sistemas de gestión de la calidad](https://www.iso.org/iso-9001-quality-management.html)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
