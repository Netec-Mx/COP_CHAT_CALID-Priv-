# Práctica: Resolución de un problema real de la operación utilizando Copilot para deducir la causa raíz.

## Metadatos

| Elemento | Valor |
|---|---|
| Duración | 90 minutos |
| Complejidad | Difícil |
| Nivel de Bloom | Aplicar |

## Descripción general

En este laboratorio culminará la cadena de análisis de calidad iniciada en los laboratorios anteriores. Utilizará la base de datos validada de no conformidades, el borrador 8D y el instructivo de torque para investigar la recurrencia de no conformidades de torque en la línea de ensamble.

Microsoft 365 Copilot se utilizará para organizar evidencia, generar preguntas de investigación, estructurar un diagrama Ishikawa, desarrollar cadenas de 5 Why y redactar documentación. Las conclusiones técnicas, la validación de causas y la aprobación de acciones corresponden siempre al participante y al responsable técnico o instructor.

## Objetivos de aprendizaje

Al finalizar el laboratorio, podrá:

- [ ] Diferenciar hechos confirmados, inferencias sustentadas, hipótesis y datos faltantes durante una investigación de causa raíz.
- [ ] Elaborar un análisis Ishikawa para la no conformidad de torque usando las categorías Mano de obra, Máquina, Método, Material, Medición, Medio ambiente y Gestión.
- [ ] Desarrollar y validar al menos dos cadenas de 5 Why sin presentar hipótesis como causas confirmadas.
- [ ] Priorizar al menos cinco acciones Kaizen mediante criterios de impacto, esfuerzo, riesgo, factibilidad y verificación de efectividad.
- [ ] Actualizar las secciones D4, D5, D6 y D7 del reporte 8D, el instructivo de torque y el archivo final de cierre.

## Requisitos previos

### Conocimientos requeridos

- Laboratorios 01, 02, 03 y 04 completados.
- Conocimiento básico de no conformidades, CAPA, metodología 8D, 5 Why, Ishikawa y Kaizen.
- Capacidad para interpretar datos de calidad y diferenciar entre síntoma, problema, causa inmediata y causa raíz.
- Comprensión de que una salida de Copilot es un borrador o una hipótesis hasta que sea revisada y respaldada por evidencia objetiva.

### Acceso y archivos requeridos

Debe utilizar la misma cuenta corporativa de Microsoft Entra ID y el tenant asignado por la organización. Confirme que dispone de acceso a:

- Microsoft 365 Copilot Chat.
- Microsoft Word con Copilot.
- Microsoft Excel con Copilot.
- OneDrive for Business y SharePoint Online.
- Biblioteca sincronizada de SharePoint:
  `/sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/`
- Responsable técnico, líder de calidad o instructor disponible para validar la causa raíz propuesta.

Los siguientes archivos deben estar disponibles en la carpeta de trabajo:

```text
03_Analisis_Patrones_Validado.xlsx
04_Reporte_8D_Borrador.docx
04_Instructivo_Torque_Borrador.docx
02_Biblioteca_Prompts_Calidad.docx
```

El archivo de cierre que generará en este laboratorio será:

```text
05_Plan_Causa_Raiz_y_Mejora.docx
```

> **Regla de control documental:** no sobrescriba archivos fuente suministrados por el instructor. Si los archivos disponibles son plantillas originales, use **Guardar una copia** en la carpeta de trabajo con los nombres obligatorios antes de editarlos. No use memorias USB, unidades personales ni servicios externos de IA.

## Entorno del laboratorio

### Hardware mínimo recomendado

| Recurso | Requisito |
|---|---|
| Conectividad | Conexión corporativa estable de al menos 10 Mbps de descarga y 5 Mbps de carga |
| Equipo | Intel Core i5 de 10.ª generación o AMD Ryzen 5 4000 Series, o equivalente |
| Memoria | 8 GB de RAM como mínimo |
| Almacenamiento | 20 GB libres como mínimo |
| Pantalla | Resolución mínima de 1920 × 1080 píxeles |
| Audio | Funcional si se utiliza Teams o una revisión colaborativa |

### Software y servicios

| Componente | Uso en el laboratorio |
|---|---|
| Windows 11 Enterprise | Estación de trabajo corporativa |
| Microsoft 365 Apps for enterprise | Edición de Word y Excel |
| Microsoft 365 Copilot | Organización, redacción y análisis asistido |
| OneDrive for Business | Sincronización de archivos |
| SharePoint Online | Almacenamiento oficial |
| Microsoft Teams | Revisión opcional con responsable técnico |

### Preparación inicial

1. Abra el Explorador de archivos y confirme que OneDrive está sincronizado.
2. Vaya a la carpeta local esperada:

   ```text
   C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
   ```

3. Si necesita comprobar la ruta mediante PowerShell, ejecute:

   ```powershell
   $ruta = "C:\Users\$env:USERNAME\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua"
   Test-Path $ruta
   Get-ChildItem $ruta | Select-Object Name, LastWriteTime
   ```

4. Confirme que `Test-Path` devuelve `True` y que se visualizan los archivos requeridos.
5. Abra `03_Analisis_Patrones_Validado.xlsx` y verifique que la tabla principal se denomina exactamente `tblNoConformidades`.
6. Compruebe que la tabla contiene, como mínimo, los campos obligatorios:

   ```text
   ID_NC, Fecha, Línea, Turno, Producto, Proceso, Tipo_Defecto,
   Cantidad_Inspeccionada, Cantidad_No_Conforme, Severidad,
   Costo_Estimado, Estado_CAPA, Responsable, Observaciones
   ```

7. Mantenga abiertos Excel, Word y, si aplica, Copilot Chat. Trabaje únicamente con información corporativa autorizada para este ejercicio.

---

## Procedimiento paso a paso

### Paso 1. Confirmar el caso, la evidencia disponible y la línea base

**Objetivo:** delimitar el problema de torque con datos verificables antes de solicitar apoyo a Copilot.

**Instrucciones:**

1. Abra `03_Analisis_Patrones_Validado.xlsx`.
2. En la tabla `tblNoConformidades`, aplique filtros para revisar registros relacionados con torque. Utilice, según corresponda, valores de los campos:
   - `Tipo_Defecto`
   - `Proceso`
   - `Observaciones`
   - `Línea`
   - `Producto`
   - `Fecha`
3. Identifique el patrón asociado con la no conformidad de torque. Como mínimo, documente:
   - Periodo analizado.
   - Línea o líneas afectadas.
   - Producto o productos afectados.
   - Turno o turnos con mayor recurrencia.
   - Cantidad inspeccionada y cantidad no conforme.
   - Severidad predominante.
   - Costo estimado o impacto disponible.
   - Estado CAPA vigente.
4. Calcule la tasa de no conformidad cuando existan los datos necesarios:

   ```text
   Tasa de no conformidad = (Cantidad_No_Conforme / Cantidad_Inspeccionada) × 100
   ```

5. Revise filtros, tablas dinámicas, gráficos o análisis ya validados en el Laboratorio 03. No modifique los datos fuente ni cambie el nombre de `tblNoConformidades`.
6. Abra `04_Reporte_8D_Borrador.docx` y lea las secciones previas para confirmar:
   - La descripción del problema.
   - Las acciones de contención existentes.
   - El alcance de lotes, productos, turnos o equipos.
   - La evidencia citada.
7. En Word o en notas de trabajo, formule una declaración objetiva del problema. Use este formato:

   ```text
   Entre [fecha inicial] y [fecha final], se registraron [cantidad] no conformidades
   de torque en [línea/proceso/producto]. La tasa observada fue [porcentaje] frente
   al criterio o meta de [valor, si existe]. El impacto documentado incluye [impacto].
   La evidencia revisada es [fuentes].
   ```

8. Clasifique la información que haya encontrado usando las siguientes etiquetas:
   - **Hecho confirmado:** respaldado directamente por registros, procedimiento, medición o evidencia verificable.
   - **Inferencia sustentada:** interpretación razonable basada en varios hechos, pendiente de confirmación directa.
   - **Hipótesis:** posible explicación aún no demostrada.
   - **Dato faltante:** información necesaria que no está disponible o no ha sido revisada.

**Salida esperada:**

Una definición cuantificada y acotada de la recurrencia de torque, con fuentes de evidencia identificadas y una lista inicial de hechos, inferencias, hipótesis y datos faltantes.

**Verificación:**

- La definición incluye periodo, alcance, impacto y evidencia.
- No se presenta como hecho una explicación que no esté respaldada por registros.
- La tabla `tblNoConformidades` conserva su nombre y estructura.
- El caso de torque permanece como hilo conductor, aunque se hayan observado otros defectos.

---

### Paso 2. Generar preguntas de investigación y un diagrama Ishikawa asistido

**Objetivo:** organizar hipótesis de investigación para la no conformidad de torque sin concluir prematuramente una causa raíz.

**Instrucciones:**

1. Abra `02_Biblioteca_Prompts_Calidad.docx`.
2. Localice un prompt relacionado con análisis de causa raíz, 5 Why, Ishikawa, CAPA o clasificación de evidencia.
3. Adapte el prompt usando exclusivamente los datos confirmados del Paso 1. Si no dispone de un prompt aplicable, utilice el siguiente modelo en Copilot Chat o en Copilot de Word:

   ```text
   Actúa como facilitador de análisis de causa raíz para un sistema de gestión de calidad.

   Caso de estudio: recurrencia de no conformidades de torque en la línea de ensamble.

   Datos confirmados:
   - Periodo: [completar].
   - Línea, producto y proceso: [completar].
   - Registros de no conformidad: [completar].
   - Tasa de no conformidad: [completar].
   - Impacto, severidad y estado CAPA: [completar].
   - Evidencia disponible: [completar].

   Genera un análisis Ishikawa preliminar usando exactamente estas categorías:
   Mano de obra, Máquina, Método, Material, Medición, Medio ambiente y Gestión.

   Para cada categoría:
   1. Propón entre 2 y 4 hipótesis de investigación.
   2. Clasifica cada elemento como hipótesis o dato faltante.
   3. Formula una pregunta verificable.
   4. Indica qué evidencia objetiva permitiría validar o descartar la hipótesis.

   No declares causas raíz confirmadas. No atribuyas responsabilidad individual sin evidencia.
   Presenta el resultado en una tabla.
   ```

4. Revise la salida de Copilot. Elimine o reformule sugerencias que:
   - No estén relacionadas con el proceso de torque.
   - Introduzcan datos no presentes en la evidencia.
   - Atribuyan fallas a personas sin registros, entrevistas u observaciones.
   - Presenten una hipótesis como una causa confirmada.
5. Cree en `05_Plan_Causa_Raiz_y_Mejora.docx` una sección titulada **“1. Definición del problema y evidencia inicial”**. Incluya la declaración del problema del Paso 1.
6. Agregue una sección titulada **“2. Ishikawa preliminar y plan de validación”**.
7. Inserte una tabla con las siguientes columnas:

   | Categoría Ishikawa | Posible causa o condición | Clasificación | Pregunta de investigación | Evidencia requerida | Estado |
   |---|---|---|---|---|---|

8. Complete las siete categorías obligatorias:
   - Mano de obra.
   - Máquina.
   - Método.
   - Material.
   - Medición.
   - Medio ambiente.
   - Gestión.
9. Marque inicialmente el estado como `Pendiente de validar`, `Descartada`, `En validación` o `Confirmada`, según la evidencia disponible.
10. Guarde el archivo como:

   ```text
   05_Plan_Causa_Raiz_y_Mejora.docx
   ```

**Salida esperada:**

Un Ishikawa preliminar con las siete categorías obligatorias, hipótesis claramente etiquetadas y preguntas de investigación vinculadas con evidencia objetiva.

**Verificación:**

- Las siete categorías están presentes.
- Cada causa propuesta tiene una clasificación explícita.
- Las hipótesis no se presentan como hechos confirmados.
- Cada hipótesis incluye una fuente de evidencia o una actividad de verificación posible.
- El archivo de cierre se guarda en la carpeta oficial sincronizada.

---

### Paso 3. Validar y priorizar hipótesis de mayor criticidad

**Objetivo:** seleccionar hipótesis relevantes para investigar con 5 Why usando criterios basados en datos, impacto y posibilidad de verificación.

**Instrucciones:**

1. Revise el Ishikawa junto con la evidencia disponible en Excel, el reporte 8D y el instructivo de torque.
2. Identifique las hipótesis con mayor criticidad. Considere:
   - Frecuencia del patrón.
   - Severidad o impacto de la no conformidad.
   - Relación temporal con turnos, equipos, lotes o cambios.
   - Posibilidad de verificar la hipótesis con evidencia objetiva.
   - Riesgo de que la condición permita recurrencia.
3. Seleccione al menos dos hipótesis para desarrollar cadenas de 5 Why.
4. Registre en `05_Plan_Causa_Raiz_y_Mejora.docx` una tabla de priorización:

   | Hipótesis | Evidencia inicial | Impacto potencial | Facilidad de verificación | Prioridad | Justificación |
   |---|---|---:|---:|---|---|

5. Use Copilot para proponer preguntas de validación, no conclusiones. Puede utilizar el siguiente prompt:

   ```text
   A partir de las siguientes hipótesis sobre no conformidades de torque,
   ayúdame a priorizar cuáles deben investigarse primero.

   Hipótesis y evidencia disponible:
   [pegar tabla resumida]

   Evalúa cada hipótesis usando:
   - impacto potencial en calidad y seguridad;
   - recurrencia aparente en los datos;
   - disponibilidad de evidencia verificable;
   - riesgo de implementar una acción incorrecta;
   - relación con el requisito de torque.

   No confirmes causas raíz. Devuelve una tabla de prioridad y preguntas
   específicas para validar cada hipótesis con registros, observación,
   entrevistas, calibración, mantenimiento o revisión documental.
   ```

6. Compare la propuesta de Copilot con la evidencia real. Ajuste la prioridad si la salida de Copilot no refleja los datos revisados.
7. Solicite al responsable técnico o instructor una revisión breve de las dos hipótesis elegidas. Registre su nombre, función, fecha y comentarios en una sección titulada **“3. Revisión técnica de hipótesis”**.
8. Si no hay evidencia suficiente para validar una hipótesis, clasifíquela como `Dato faltante` o `Hipótesis pendiente`; no la convierta en causa raíz.

**Salida esperada:**

Dos hipótesis prioritarias para análisis 5 Why, seleccionadas mediante criterios explícitos y revisadas por un responsable técnico o instructor.

**Verificación:**

- Existen al menos dos hipótesis priorizadas.
- La prioridad está justificada con datos o evidencia disponible.
- La revisión humana quedó documentada.
- Ninguna hipótesis se registra como causa raíz sin evidencia suficiente.

---

### Paso 4. Desarrollar dos cadenas de 5 Why con control de evidencia

**Objetivo:** explorar relaciones causales de manera estructurada y distinguir causas inmediatas, fallas sistémicas, hipótesis y datos faltantes.

**Instrucciones:**

1. Cree una sección titulada **“4. Análisis 5 Why”** en `05_Plan_Causa_Raiz_y_Mejora.docx`.
2. Para la primera hipótesis prioritaria, formule el problema inicial con lenguaje verificable. Ejemplo de estructura:

   ```text
   Problema: Se detectaron unidades con torque fuera de especificación en
   [línea/proceso/periodo], según [registro o fuente].
   ```

3. Utilice el siguiente prompt en Copilot. Sustituya los campos entre corchetes con datos reales:

   ```text
   Actúa como facilitador de 5 Why en un análisis de calidad.

   Problema confirmado:
   [describir el problema con datos verificables].

   Hipótesis prioritaria:
   [describir].

   Evidencia disponible:
   [listar registros, procedimientos, resultados de calibración, mantenimiento,
   entrevistas, observaciones u otros datos].

   Construye una cadena preliminar de 5 Why.
   Para cada nivel, incluye:
   - pregunta "¿Por qué?";
   - respuesta provisional;
   - clasificación: hecho confirmado, inferencia sustentada, hipótesis o dato faltante;
   - evidencia que respalda o que se requiere;
   - decisión de validación necesaria.

   No inventes registros ni confirmes una causa raíz sin evidencia.
   Detente si no existe evidencia suficiente para continuar.
   ```

4. Revise cada respuesta propuesta. Reemplace formulaciones ambiguas como “el operador no tuvo cuidado” por condiciones verificables, por ejemplo:
   - El instructivo no define el valor de torque, la secuencia o el método de registro.
   - El equipo no tiene evidencia vigente de calibración.
   - No existe una verificación documentada posterior al cambio de herramienta.
   - El sistema permite liberar el producto sin registrar el torque.
5. Complete una tabla de 5 Why para la primera hipótesis:

   | Nivel | Pregunta | Respuesta provisional | Clasificación | Evidencia revisada o requerida | Resultado de validación |
   |---:|---|---|---|---|---|
   | 0 | ¿Cuál es el problema? |  | Hecho confirmado |  |  |
   | 1 | ¿Por qué ocurrió? |  |  |  |  |
   | 2 | ¿Por qué ocurrió esa condición? |  |  |  |  |
   | 3 | ¿Por qué ocurrió esa condición? |  |  |  |  |
   | 4 | ¿Por qué ocurrió esa condición? |  |  |  |  |
   | 5 | ¿Por qué el sistema permitió esa condición? |  |  |  |  |

6. Repita el proceso para la segunda hipótesis prioritaria.
7. Determine para cada cadena si la investigación llegó a:
   - Una **causa confirmada**, respaldada por evidencia.
   - Una **inferencia sustentada**, que requiere confirmación adicional.
   - Una **hipótesis pendiente**, que no debe generar una CAPA definitiva.
   - Un **dato faltante**, que requiere una actividad adicional de investigación.
8. Identifique explícitamente la diferencia entre:
   - Síntoma: unidades con torque fuera de especificación.
   - Problema: incumplimiento de requisito de torque dentro de un periodo y alcance definidos.
   - Causa inmediata: condición que produjo directamente el torque incorrecto, si fue confirmada.
   - Causa raíz: falla de sistema que permitió la causa inmediata, si fue confirmada.
9. Solicite validación técnica de la causa raíz propuesta. Si el responsable técnico no confirma la evidencia, regístrela como hipótesis y defina una acción de investigación, no una acción correctiva final.

**Salida esperada:**

Dos cadenas de 5 Why documentadas, cada una con clasificación de evidencia, criterio de validación y resultado técnico.

**Verificación:**

- Existen dos análisis 5 Why completos.
- Cada “por qué” tiene una clasificación y una fuente de evidencia.
- La causa raíz propuesta se diferencia de la causa inmediata.
- No se adopta una causa raíz sin revisión humana documentada.

---

### Paso 5. Diseñar y priorizar acciones Kaizen

**Objetivo:** generar soluciones orientadas al sistema y seleccionar acciones viables según impacto, esfuerzo, riesgo, factibilidad y verificación de efectividad.

**Instrucciones:**

1. Cree la sección **“5. Opciones de mejora Kaizen”** en el archivo de cierre.
2. Genere ideas de mejora vinculadas exclusivamente con causas confirmadas o hipótesis claramente identificadas. No proponga acciones punitivas ni base la solución únicamente en “tener más cuidado”.
3. Solicite apoyo a Copilot mediante el siguiente prompt:

   ```text
   Propón opciones de mejora Kaizen para reducir la recurrencia de no conformidades
   de torque en una línea de ensamble.

   Causas confirmadas:
   [listar únicamente causas confirmadas].

   Hipótesis pendientes:
   [listar por separado].

   Restricciones:
   - No atribuir la causa a una persona sin evidencia.
   - Priorizar controles de proceso, prevención, detección temprana y trazabilidad.
   - Diferenciar acciones correctivas para causas confirmadas de acciones de investigación
     para hipótesis pendientes.
   - Incluir responsable sugerido, evidencia de implementación y método de verificación
     de eficacia.

   Propón al menos siete opciones y no declares que una acción resolverá el problema
   sin definir cómo se verificará.
   ```

4. Revise las ideas y seleccione al menos cinco acciones para evaluarlas.
5. Incluya alternativas tales como, cuando sean pertinentes y autorizadas por el proceso:
   - Revisión del instructivo para aclarar secuencia, valor objetivo, tolerancia y registro.
   - Validación documentada tras cambio de herramienta, ajuste o programa.
   - Verificación de calibración o mantenimiento de la herramienta de torque.
   - Control visual o sistema de confirmación de parámetros.
   - Muestreo reforzado temporal o verificación de primera pieza.
   - Capacitación con evaluación de competencia.
   - Revisión de registros de torque y criterios de liberación.
   - Escalamiento de desviaciones repetitivas a gestión de calidad o mantenimiento.
6. Cree una matriz de evaluación con escala de 1 a 5, donde 5 representa la condición más favorable salvo en riesgo, donde 5 representa riesgo alto:

   | Acción propuesta | Causa vinculada | Impacto | Esfuerzo | Riesgo | Factibilidad | Verificabilidad | Prioridad recomendada | Decisión |
   |---|---|---:|---:|---:|---:|---:|---|---|

7. Aplique el siguiente criterio de decisión:
   - **Implementar primero:** alto impacto, bajo o medio esfuerzo, riesgo controlable, alta factibilidad y alta verificabilidad.
   - **Planificar:** alto impacto con esfuerzo mayor, siempre que exista responsable, plazo y control de riesgo.
   - **Investigar antes de implementar:** acción relacionada con hipótesis no confirmada.
   - **Descartar o posponer:** bajo impacto, riesgo elevado o falta de relación demostrable con el problema.
8. Documente al menos cinco acciones evaluadas y seleccione las que pasarán a D5 y D6 del 8D.
9. Para cada acción seleccionada, defina:
   - Responsable funcional.
   - Fecha objetivo.
   - Recursos o aprobaciones necesarias.
   - Evidencia de implementación.
   - Riesgo de implementación.
   - Indicador o criterio de efectividad.

**Salida esperada:**

Una matriz impacto-esfuerzo-riesgo con al menos cinco acciones evaluadas y una selección justificada de acciones correctivas, preventivas o de investigación.

**Verificación:**

- La matriz contiene al menos cinco acciones.
- Cada acción se vincula con una causa confirmada o una hipótesis claramente marcada.
- Las acciones seleccionadas incluyen responsable, plazo y método de verificación.
- Se priorizan controles de sistema sobre acciones genéricas dirigidas a personas.

---

### Paso 6. Actualizar D4, D5, D6 y D7 del reporte 8D

**Objetivo:** documentar el análisis de causa raíz y el plan CAPA en el reporte 8D con trazabilidad hacia evidencia y verificación de eficacia.

**Instrucciones:**

1. Abra `04_Reporte_8D_Borrador.docx`.
2. Guarde los cambios únicamente en la copia de trabajo autorizada con el nombre obligatorio:

   ```text
   04_Reporte_8D_Borrador.docx
   ```

3. Actualice **D4: Identificación y verificación de causa raíz**. Incluya:
   - Definición resumida del problema.
   - Evidencia analizada.
   - Resultados del Ishikawa.
   - Resultados de las dos cadenas 5 Why.
   - Distinción entre causas confirmadas, inferencias, hipótesis y datos faltantes.
   - Nombre y función de quien realizó la validación técnica.
4. Actualice **D5: Selección de acciones correctivas permanentes**. Incluya:
   - Acciones seleccionadas a partir de la matriz.
   - Causa vinculada a cada acción.
   - Justificación de selección.
   - Responsable y fecha objetivo.
   - Riesgos y aprobaciones requeridas.
5. Actualice **D6: Implementación y validación de acciones correctivas**. Para cada acción, defina:
   - Actividad de implementación.
   - Evidencia requerida, por ejemplo: registro de calibración, instrucción aprobada, capacitación evaluada, registro de primera pieza o cambio de configuración autorizado.
   - Fecha de ejecución.
   - Responsable.
   - Resultado esperado.
   - Estado inicial: `Pendiente`, `En curso`, `Implementada` o `Verificada`.
6. Actualice **D7: Prevención de recurrencia**. Incluya controles sistémicos aplicables:
   - Actualización controlada del instructivo de torque.
   - Revisión de frecuencia de verificación, calibración o mantenimiento, según evidencia.
   - Control de cambios de parámetro o herramienta.
   - Revisión periódica de indicadores de torque.
   - Capacitación y evaluación de competencia cuando corresponda.
   - Comunicación de lecciones aprendidas a líneas o productos similares.
7. Utilice Copilot en Word para mejorar claridad y consistencia, sin alterar el sentido técnico. Ejemplo:

   ```text
   Revisa las secciones D4, D5, D6 y D7 siguientes como auditor interno de calidad.

   Conserva exclusivamente las afirmaciones respaldadas por evidencia.
   Señala cualquier frase que presente una hipótesis como una causa confirmada.
   Verifica que cada acción tenga causa vinculada, responsable, plazo, evidencia
   de implementación y criterio de efectividad.

   No agregues datos, resultados ni aprobaciones que no estén en el texto.
   Devuelve primero observaciones y después una versión redactada para revisión humana.
   ```

8. Revise manualmente la redacción sugerida antes de aceptarla.
9. Guarde el documento y espere a que OneDrive confirme la sincronización.

**Salida esperada:**

El reporte 8D actualizado en D4, D5, D6 y D7, con trazabilidad entre evidencia, causa, acción, responsable y verificación de efectividad.

**Verificación:**

- D4 no contiene causas no verificadas presentadas como confirmadas.
- D5 relaciona cada acción con una causa o condición validada.
- D6 define evidencia de implementación.
- D7 incorpora controles para prevenir recurrencia.
- El archivo conserva el nombre obligatorio y está sincronizado en SharePoint.

---

### Paso 7. Actualizar el instructivo de torque y cerrar el plan de mejora

**Objetivo:** incorporar controles operativos aplicables al instructivo y consolidar el plan final de causa raíz y mejora.

**Instrucciones:**

1. Abra `04_Instructivo_Torque_Borrador.docx`.
2. Revise las causas confirmadas y las acciones aprobadas. No modifique el instructivo basándose únicamente en hipótesis pendientes.
3. Actualice los controles operativos aplicables, según el análisis validado. Incluya solo los que correspondan al proceso real:
   - Valor objetivo de torque y tolerancia aprobada.
   - Secuencia de apriete.
   - Identificación de herramienta o programa autorizado.
   - Verificación antes de inicio de turno, primera pieza o cambio de lote.
   - Requisitos de calibración, mantenimiento o revisión de condición.
   - Registro requerido y criterio de aceptación.
   - Acción ante resultado fuera de especificación.
   - Escalamiento al responsable de calidad, supervisión o mantenimiento.
   - Control de cambio cuando se modifiquen parámetros, herramienta o método.
4. Añada una sección de trazabilidad documental que indique:
   - Referencia al reporte 8D.
   - Fecha de actualización.
   - Responsable de revisión.
   - Requisito de aprobación antes de liberar el instructivo como documento controlado.
5. Use Copilot únicamente para mejorar la estructura de instrucciones. Ejemplo:

   ```text
   Convierte el siguiente contenido validado en pasos operativos claros para un
   instructivo de torque.

   Requisitos confirmados:
   [pegar requisitos validados].

   Usa lenguaje imperativo, numeración secuencial, criterios de aceptación,
   registros requeridos y acciones ante desviación.

   No inventes valores de torque, frecuencias de calibración, códigos de herramienta
   ni criterios de aceptación. Marca como [PENDIENTE DE DEFINIR] cualquier dato faltante.
   ```

6. Revise que Copilot no haya inventado parámetros técnicos. Sustituya cualquier marcador pendiente mediante información aprobada o manténgalo claramente identificado para aprobación.
7. Guarde el instructivo con el nombre obligatorio:

   ```text
   04_Instructivo_Torque_Borrador.docx
   ```

8. Regrese a `05_Plan_Causa_Raiz_y_Mejora.docx` y agregue una sección final titulada **“6. Plan de implementación y verificación de efectividad”**.
9. Inserte la siguiente tabla:

   | Acción | Tipo de acción | Causa vinculada | Responsable | Fecha objetivo | Evidencia de implementación | Indicador de efectividad | Criterio de aceptación | Fecha de revisión |
   |---|---|---|---|---|---|---|---|---|

10. Defina un criterio cuantificable de efectividad cuando los datos lo permitan. Por ejemplo:

   ```text
   La tasa de no conformidades de torque se mantendrá en o por debajo de la meta
   aprobada durante [periodo definido] y no se registrarán recurrencias atribuibles
   a la causa confirmada. La revisión utilizará tblNoConformidades, registros de
   proceso y evidencia de implementación.
   ```

11. Añada una sección **“7. Aprobación y limitaciones”** con:
   - Nombre y función del revisor técnico o instructor.
   - Fecha de revisión.
   - Causas confirmadas.
   - Hipótesis pendientes y acciones de investigación asociadas.
   - Limitaciones de datos.
   - Declaración de que Copilot apoyó la organización y redacción, pero no sustituyó la validación humana.
12. Guarde, cierre y confirme la sincronización de los tres archivos finales:
   - `04_Reporte_8D_Borrador.docx`
   - `04_Instructivo_Torque_Borrador.docx`
   - `05_Plan_Causa_Raiz_y_Mejora.docx`

**Salida esperada:**

Un instructivo de torque actualizado con controles operativos aplicables y un archivo final de cierre que integra evidencia, Ishikawa, 5 Why, matriz de acciones, plan CAPA y verificación de efectividad.

**Verificación:**

- El instructivo no incorpora valores técnicos inventados por IA.
- Los controles añadidos se relacionan con causas o condiciones validadas.
- El plan final incluye responsables, plazos, evidencia e indicadores.
- Los tres documentos se encuentran en la ubicación oficial y sincronizada.

---

## Validación y pruebas

Realice la siguiente revisión antes de presentar los entregables al instructor o responsable técnico.

| Criterio de validación | Método de comprobación | Resultado esperado |
|---|---|---|
| Integridad de datos | Abrir Excel y confirmar el nombre de tabla | La tabla se llama exactamente `tblNoConformidades` |
| Trazabilidad del problema | Comparar Excel, 8D y plan final | El periodo, línea, proceso y problema de torque son consistentes |
| Clasificación de evidencia | Revisar Ishikawa y 5 Why | Cada afirmación está etiquetada como hecho, inferencia, hipótesis o dato faltante |
| Ishikawa completo | Revisar las categorías | Están presentes Mano de obra, Máquina, Método, Material, Medición, Medio ambiente y Gestión |
| Dos cadenas 5 Why | Revisar el plan final | Hay al menos dos cadenas desarrolladas y revisadas |
| Causa raíz validada | Revisar D4 y aprobación técnica | No se presenta una hipótesis como causa confirmada sin evidencia |
| Priorización de acciones | Revisar matriz Kaizen | Se evaluaron al menos cinco acciones por impacto, esfuerzo, riesgo, factibilidad y verificabilidad |
| Acciones CAPA | Revisar D5 y D6 | Cada acción tiene causa vinculada, responsable, fecha y evidencia requerida |
| Prevención de recurrencia | Revisar D7 e instructivo | Existen controles operativos y sistémicos aplicables |
| Efectividad | Revisar plan final | Cada acción relevante tiene indicador, criterio de aceptación y fecha de revisión |
| Control documental | Revisar SharePoint o iconos de OneDrive | Los archivos están sincronizados y se conservan los nombres obligatorios |

### Prueba de consistencia de afirmaciones

Seleccione cinco afirmaciones del reporte 8D y verifique para cada una:

1. ¿La afirmación describe un dato observable o una interpretación?
2. ¿Qué registro, documento, entrevista u observación la respalda?
3. ¿Está clasificada correctamente?
4. Si es una causa raíz, ¿qué evidencia demuestra que es una falla de sistema y no solo una causa inmediata?
5. ¿La acción asociada elimina, controla o detecta la condición que permite la recurrencia?

Si alguna afirmación no puede responder estas preguntas, debe cambiarse a `Hipótesis`, `Inferencia sustentada` o `Dato faltante`.

## Solución de problemas

### Problema 1: Copilot no puede analizar el contenido esperado o genera respuestas genéricas

**Síntomas:** Copilot indica que no puede acceder al archivo, resume información irrelevante o propone causas sin relación con los datos de torque.

**Causa probable:** El archivo no está abierto en la aplicación correspondiente, no se ha sincronizado con OneDrive, el prompt no incluye datos confirmados o Copilot no tiene contexto suficiente sobre la evidencia.

**Solución:**

1. Confirme que el archivo está guardado y sincronizado en la biblioteca corporativa.
2. Abra el archivo en Excel o Word antes de usar Copilot dentro de la aplicación.
3. Incluya en el prompt el periodo, línea, proceso, defecto, datos confirmados y fuentes de evidencia.
4. Solicite explícitamente que Copilot no invente datos ni confirme causas.
5. Si persiste el problema, copie únicamente un resumen autorizado de los hechos confirmados al prompt y revise la salida con el responsable técnico.

### Problema 2: La causa raíz propuesta no puede validarse con evidencia objetiva

**Síntomas:** La cadena de 5 Why termina en afirmaciones como “falta de atención”, “error del operador” o “mantenimiento deficiente”, pero no existen registros, observaciones o entrevistas que lo demuestren.

**Causa probable:** Se ha confundido una opinión o una inferencia con una causa confirmada, o se intentó completar los cinco niveles sin disponer de evidencia suficiente.

**Solución:**

1. Reclasifique la afirmación como `Hipótesis` o `Dato faltante`.
2. Defina una actividad de validación concreta: revisar registros de calibración, historial de mantenimiento, control de cambios, procedimiento vigente, registros de capacitación, observación directa o entrevistas estructuradas.
3. No implemente una acción correctiva permanente basada en esa hipótesis.
4. Documente una acción de investigación y una medida de contención proporcional al riesgo.
5. Solicite revisión del responsable técnico antes de actualizar D4 como causa raíz confirmada.

## Limpieza

1. Guarde todos los cambios en la carpeta corporativa sincronizada.
2. Confirme que OneDrive no muestra errores de sincronización.
3. Cierre Excel, Word y cualquier sesión de Copilot Chat que contenga información del caso.
4. No elimine registros de origen, tablas, archivos del instructor ni evidencia utilizada.
5. No copie archivos a almacenamiento personal, USB, correo externo ni herramientas de IA no autorizadas.
6. Compruebe que permanecen disponibles los siguientes entregables:

   ```text
   03_Analisis_Patrones_Validado.xlsx
   04_Reporte_8D_Borrador.docx
   04_Instructivo_Torque_Borrador.docx
   05_Plan_Causa_Raiz_y_Mejora.docx
   ```

## Resumen

En este laboratorio aplicó un proceso estructurado de análisis de causa raíz para una recurrencia de no conformidades de torque. Partió de datos validados, organizó hipótesis con un Ishikawa de siete categorías, desarrolló dos cadenas de 5 Why y distinguió hechos, inferencias, hipótesis y datos faltantes.

También priorizó acciones Kaizen mediante impacto, esfuerzo, riesgo, factibilidad y verificabilidad; actualizó D4 a D7 del reporte 8D; incorporó controles operativos al instructivo de torque; y creó el plan final de causa raíz y mejora. Copilot apoyó la organización, redacción y formulación de preguntas, mientras que la validación de evidencia, causas y acciones permaneció bajo responsabilidad humana.

### Recursos de consulta

- [ISO 9001: Sistemas de gestión de la calidad](https://www.iso.org/iso-9001-quality-management.html)
- [ASQ: Análisis de causa raíz](https://asq.org/quality-resources/root-cause-analysis)
- [ASQ: Diagrama de Ishikawa](https://asq.org/quality-resources/fishbone)
- [NIST Baldrige: Mejora continua](https://www.nist.gov/baldrige)
