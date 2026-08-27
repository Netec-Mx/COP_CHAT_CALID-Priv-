# Práctica: Análisis de patrones en una base de datos de calidad con apoyo visual automático

## Metadatos

| Elemento | Valor |
|---|---|
| Duración | 90 minutos |
| Complejidad | Media |
| Nivel de Bloom | Aplicar |

## Descripción general

En esta práctica analizarás una base de datos de no conformidades de planta mediante Microsoft Excel y Microsoft 365 Copilot. Explorarás tendencias, desviaciones, recurrencias, anomalías y concentración de impacto mediante un análisis de Pareto y un gráfico de tendencia.

El análisis conservará como hilo conductor la no conformidad de **torque en la línea de ensamble**. Todas las conclusiones generadas con Copilot deberán contrastarse con filtros, tablas dinámicas, fórmulas o gráficos visibles de Excel antes de registrarse como hallazgos verificables.

El resultado será el archivo `03_Analisis_Patrones_Validado.xlsx`, que servirá como evidencia cuantitativa para el reporte 8D del Laboratorio 04 y como fuente de hipótesis para el análisis de causa raíz del Laboratorio 05.

## Objetivos de aprendizaje

Al finalizar la práctica, podrás:

- [ ] Utilizar Copilot en Excel para explorar tendencias, desviaciones, recurrencias y anomalías en `tblNoConformidades`.
- [ ] Generar y validar un análisis de criticidad tipo Pareto por tipo de defecto.
- [ ] Crear y verificar al menos un gráfico de tendencia mensual relacionado con no conformidades de torque.
- [ ] Diferenciar entre un patrón observado, una correlación y una conclusión causal no demostrada.
- [ ] Documentar hallazgos verificables, evidencia, limitaciones y preguntas pendientes en la hoja `Resumen_Copilot_Validado`.

## Prerrequisitos

### Conocimientos previos

- Laboratorios 01 y 02 completados.
- Conocimiento básico de tablas de Excel, filtros, ordenación y gráficos.
- Capacidad para distinguir entre frecuencia, severidad, costo estimado y tasa de no conformidad.
- Comprensión de que una anomalía o correlación no demuestra una causa raíz.
- Familiaridad con los prompts estructurados y validados en el archivo `02_Biblioteca_Prompts_Calidad.docx`.

### Acceso y archivos requeridos

Antes de comenzar, confirme que dispone de lo siguiente:

- Cuenta corporativa Microsoft Entra ID con licencia activa de Microsoft 365 Copilot.
- Acceso a Excel para Microsoft 365 y a Copilot en Excel.
- Acceso a OneDrive for Business y a la biblioteca de SharePoint del curso.
- Archivo fuente `03_Base_Datos_Calidad.xlsx`.
- Archivo `02_Biblioteca_Prompts_Calidad.docx`.
- Permisos de escritura en la carpeta de trabajo asignada.
- La tabla principal del archivo fuente debe llamarse exactamente `tblNoConformidades`.

> **Importante:** No sobrescriba el archivo fuente entregado por el instructor. Trabaje sobre una copia guardada con el nombre obligatorio de salida.

## Entorno de laboratorio

### Ruta de trabajo estándar

Utilice la biblioteca sincronizada de SharePoint:

```text
/sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/
```

En equipos Windows, la ruta local esperada es:

```text
C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
```

Puede abrir la ruta local desde el Explorador de archivos usando:

```text
%USERPROFILE%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
```

### Requisitos de hardware y conectividad

| Recurso | Requisito mínimo recomendado |
|---|---|
| Equipo | Intel Core i5 de 10.ª generación o AMD Ryzen 5 4000 Series, o equivalente |
| Memoria | 8 GB de RAM como mínimo |
| Espacio disponible | 20 GB libres en disco |
| Pantalla | Resolución mínima de 1920 × 1080 |
| Conectividad | Red corporativa estable, al menos 10 Mbps de descarga y 5 Mbps de carga |
| Cuenta | Microsoft Entra ID corporativa con licencia Microsoft 365 Copilot |

### Software previsto

| Componente | Uso en esta práctica |
|---|---|
| Microsoft Excel para Microsoft 365 | Exploración, tabla dinámica, fórmulas, gráficos y hoja de resumen |
| Microsoft 365 Copilot en Excel | Análisis inicial, sugerencias de patrones y propuestas de visualización |
| OneDrive for Business / SharePoint Online | Almacenamiento oficial y sincronización |
| Microsoft Word | Consulta del archivo `02_Biblioteca_Prompts_Calidad.docx` |
| Microsoft Edge | Acceso alternativo a archivos o servicios corporativos si fuera necesario |

### Controles de uso responsable

Durante la práctica, aplique los siguientes controles:

1. Utilice únicamente la cuenta corporativa y el tenant asignado.
2. No copie datos del archivo a servicios externos de IA, cuentas personales, memorias USB ni unidades no autorizadas.
3. No trate una salida de Copilot como evidencia definitiva sin validación visible en Excel.
4. No modifique, elimine ni renombre la tabla `tblNoConformidades`.
5. No convierta asociaciones observadas en afirmaciones causales sin investigación adicional.
6. Registre limitaciones y preguntas pendientes en la hoja de resumen.

## Procedimiento paso a paso

### Paso 1. Preparar una copia controlada del archivo de análisis

**Objetivo:** Crear un archivo de trabajo independiente sin modificar la fuente original y confirmar que la tabla de datos cumple la convención obligatoria.

**Instrucciones:**

1. Abra el Explorador de archivos y navegue a la ruta de trabajo estándar:

   ```text
   C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
   ```

2. Localice el archivo fuente:

   ```text
   03_Base_Datos_Calidad.xlsx
   ```

3. Abra el archivo en Excel para comprobar que se carga correctamente.

4. Seleccione **Archivo > Guardar como**.

5. Guarde una copia en la misma carpeta con el nombre exacto:

   ```text
   03_Analisis_Patrones_Validado.xlsx
   ```

6. Cierre el archivo fuente si permaneció abierto y continúe trabajando únicamente en `03_Analisis_Patrones_Validado.xlsx`.

7. En Excel, seleccione cualquier celda de la tabla principal.

8. Abra la pestaña **Diseño de tabla** o **Table Design**.

9. Confirme que el campo **Nombre de la tabla** contiene exactamente:

   ```text
   tblNoConformidades
   ```

10. Verifique que estén disponibles, como mínimo, los siguientes campos:

   ```text
   ID_NC
   Fecha
   Línea
   Turno
   Producto
   Proceso
   Tipo_Defecto
   Cantidad_Inspeccionada
   Cantidad_No_Conforme
   Severidad
   Costo_Estimado
   Estado_CAPA
   Responsable
   Observaciones
   ```

11. Active el guardado manual frecuente mediante **Ctrl+S**. Si el archivo se sincroniza con OneDrive, espere a que desaparezcan indicadores de carga antes de cerrar Excel.

**Resultado esperado:**

- Existe una copia de trabajo llamada `03_Analisis_Patrones_Validado.xlsx`.
- El archivo fuente `03_Base_Datos_Calidad.xlsx` permanece sin modificaciones.
- La tabla se denomina exactamente `tblNoConformidades`.
- Los campos mínimos requeridos están presentes y visibles.

**Verificación:**

- Revise la barra de título de Excel: debe mostrar `03_Analisis_Patrones_Validado.xlsx`.
- Seleccione una celda de datos y confirme el nombre de tabla en **Diseño de tabla**.
- Compruebe que la primera fila contiene encabezados y que los filtros de tabla están habilitados.
- Si el nombre no es `tblNoConformidades`, detenga el análisis y corrija el nombre antes de usar Copilot o crear tablas dinámicas.

---

### Paso 2. Revisar la calidad inicial de los datos y aislar el caso de torque

**Objetivo:** Confirmar que los datos son interpretables, identificar registros relacionados con torque y evitar que errores de estructura se conviertan en conclusiones incorrectas.

**Instrucciones:**

1. Revise visualmente los encabezados de `tblNoConformidades`. Compruebe que no existan columnas duplicadas, encabezados vacíos o nombres ambiguos.

2. Verifique que la columna `Fecha` contiene fechas reconocidas por Excel:
   - Seleccione varias celdas de la columna.
   - Confirme que Excel permite aplicar filtros por año, mes o periodo.
   - Si las fechas están alineadas como texto o no permiten filtros cronológicos, documente la limitación y solicite corrección al instructor antes de realizar análisis temporales.

3. Revise las columnas numéricas:
   - `Cantidad_Inspeccionada`
   - `Cantidad_No_Conforme`
   - `Costo_Estimado`

4. Aplique temporalmente un filtro en `Cantidad_Inspeccionada` para identificar valores vacíos o iguales a cero. Registre si existen, ya que afectan el cálculo de tasas.

5. Aplique temporalmente un filtro en `Cantidad_No_Conforme` para identificar valores negativos, vacíos o no numéricos. No modifique los datos fuente salvo indicación del instructor; solo documente anomalías de calidad de datos.

6. En la columna `Tipo_Defecto`, use el filtro para buscar el término:

   ```text
   torque
   ```

   Si existen variaciones de escritura, como `Torque`, `TORQUE`, `torque bajo` o `torque alto`, identifíquelas. Excel normalmente no distingue mayúsculas de minúsculas, pero sí puede distinguir textos distintos.

7. Anote las categorías de torque detectadas. Por ejemplo:

   ```text
   Torque bajo
   Torque alto
   Torque fuera de especificación
   ```

8. Quite los filtros aplicados para restaurar la vista completa de la tabla.

9. Abra `02_Biblioteca_Prompts_Calidad.docx` y localice los prompts validados relacionados con:
   - Tendencias mensuales.
   - Recurrencia de defectos.
   - Priorización Pareto.
   - Anomalías.
   - Análisis de costos.
   - Limitaciones y preguntas de validación.

10. Mantenga el documento disponible como referencia, pero realice las solicitudes a Copilot únicamente desde el libro de Excel que contiene la tabla de datos.

**Resultado esperado:**

- La tabla está disponible para análisis y no presenta problemas estructurales críticos no documentados.
- Se conocen las etiquetas reales utilizadas para la no conformidad de torque.
- Se han identificado posibles limitaciones de datos, especialmente fechas no válidas, cantidades inspeccionadas iguales a cero o categorías inconsistentes.

**Verificación:**

- Aplique el filtro de `Tipo_Defecto` y confirme que puede recuperar registros asociados a torque.
- Confirme que `Fecha` permite filtros cronológicos.
- Revise que los campos numéricos se comportan como números: al seleccionar un rango, Excel debe mostrar cálculos básicos en la barra de estado, como suma o promedio cuando corresponda.
- Si detecta registros con datos faltantes, no los elimine; anote su posible impacto en `Resumen_Copilot_Validado`.

---

### Paso 3. Solicitar a Copilot una exploración estructurada de patrones

**Objetivo:** Utilizar Copilot como apoyo para formular hipótesis analíticas iniciales sobre recurrencias, líneas, turnos, tendencias y costos.

**Instrucciones:**

1. Seleccione una celda dentro de `tblNoConformidades`.

2. Abra Copilot en Excel desde el botón **Copilot** de la cinta de opciones o desde el panel lateral disponible en su versión de Excel.

3. Si Copilot solicita confirmar el rango de análisis, asegúrese de que el contexto incluya `tblNoConformidades`.

4. Use un prompt validado del Laboratorio 02 o adapte el siguiente prompt estructurado:

   ```text
   Analiza la tabla tblNoConformidades como exploración inicial de calidad.
   Resume:
   1. Los tipos de defecto más recurrentes por cantidad de registros y por Cantidad_No_Conforme.
   2. Las líneas y turnos que concentran mayor Cantidad_No_Conforme.
   3. La evolución mensual de Cantidad_No_Conforme y de Costo_Estimado.
   4. Posibles meses, líneas o turnos con variaciones inusuales respecto al periodo.
   5. El comportamiento específico de los registros cuyo Tipo_Defecto contiene “torque”.
   
   Distingue claramente entre hechos observados, patrones que requieren validación e hipótesis no causales.
   No atribuyas causas raíz. Indica qué cálculos, filtros o gráficos debo revisar en Excel para validar cada hallazgo.
   ```

5. Revise la respuesta de Copilot. No copie todavía la respuesta como conclusión oficial.

6. Identifique entre tres y cinco afirmaciones concretas que puedan validarse. Ejemplos:
   - “El defecto de torque figura entre las categorías más frecuentes.”
   - “La Línea X concentra la mayor cantidad no conforme relacionada con torque.”
   - “Un mes determinado presenta un aumento frente al promedio del periodo.”
   - “Un turno concentra un costo estimado superior al de otros turnos.”
   - “Tres categorías acumulan aproximadamente el 80 % de los defectos.”

7. Para cada afirmación, clasifíquela preliminarmente como una de las siguientes:
   - **Hecho cuantificable:** puede comprobarse mediante suma, conteo, tabla dinámica o gráfico.
   - **Patrón observado:** indica una tendencia o concentración, pero requiere revisión contextual.
   - **Hipótesis de investigación:** plantea una posibilidad, pero no está demostrada.
   - **Afirmación no aceptable:** contiene una causa raíz o una relación no sustentada por la base.

8. Si Copilot atribuye una causa, por ejemplo, “el turno nocturno causa fallas de torque”, reformule la afirmación de manera válida:

   ```text
   Los registros disponibles muestran una concentración de no conformidades de torque en el turno nocturno. Esta asociación requiere investigación; la base no demuestra que el turno sea la causa.
   ```

9. Guarde el libro con **Ctrl+S**.

**Resultado esperado:**

- Copilot proporciona un resumen exploratorio de tendencias, recurrencias y posibles anomalías.
- Se identifican afirmaciones medibles que pueden contrastarse dentro de Excel.
- Las conclusiones causales no demostradas se rechazan o se convierten en hipótesis de investigación.

**Verificación:**

- La respuesta de Copilot menciona explícitamente que los resultados requieren validación o propone formas de validarlos.
- Puede señalar al menos tres afirmaciones verificables y una limitación o advertencia.
- Ninguna salida de Copilot se registra todavía como evidencia final sin una fuente visible en Excel.

---

### Paso 4. Crear y validar un análisis de Pareto por tipo de defecto

**Objetivo:** Construir una visualización Pareto que priorice tipos de defecto por `Cantidad_No_Conforme` y validar los resultados frente a una tabla dinámica.

**Instrucciones:**

1. Seleccione cualquier celda de `tblNoConformidades`.

2. Cree una tabla dinámica:
   - Seleccione **Insertar > Tabla dinámica**.
   - Confirme que el origen de datos sea `tblNoConformidades`.
   - Elija crearla en una nueva hoja de cálculo.
   - Renombre la hoja como:

   ```text
   Validacion_Pareto
   ```

3. Configure los campos de la tabla dinámica:
   - Arrastre `Tipo_Defecto` al área **Filas**.
   - Arrastre `Cantidad_No_Conforme` al área **Valores**.
   - Compruebe que el cálculo sea **Suma de Cantidad_No_Conforme**, no conteo.

4. Ordene la tabla dinámica de mayor a menor:
   - Haga clic con el botón derecho sobre un valor de la columna de suma.
   - Seleccione **Ordenar > Ordenar de mayor a menor**.

5. Agregue una segunda vez el campo `Cantidad_No_Conforme` al área **Valores**.

6. Configure el segundo campo de valores:
   - Seleccione **Configuración de campo de valor**.
   - Seleccione **Mostrar valores como**.
   - Elija **% del total acumulado en**.
   - Establezca como campo base:

   ```text
   Tipo_Defecto
   ```

7. Cambie el encabezado de la primera columna de valores a:

   ```text
   Cantidad_No_Conforme_Total
   ```

8. Cambie el encabezado de la segunda columna de valores a:

   ```text
   Porcentaje_Acumulado
   ```

9. Seleccione la tabla dinámica y cree un gráfico combinado:
   - Seleccione **Insertar > Gráfico combinado**.
   - Configure `Cantidad_No_Conforme_Total` como columna agrupada.
   - Configure `Porcentaje_Acumulado` como línea.
   - Active el eje secundario para `Porcentaje_Acumulado`.
   - Formatee el eje secundario con mínimo 0 % y máximo 100 %.

10. Asigne al gráfico el título:

   ```text
   Pareto de no conformidades por tipo de defecto
   ```

11. Si Copilot ofrece crear un gráfico Pareto automáticamente, puede solicitarlo con el siguiente prompt:

   ```text
   Propón un gráfico de Pareto por Tipo_Defecto usando la suma de Cantidad_No_Conforme. Ordena las categorías de mayor a menor e incluye porcentaje acumulado. No reemplaces la validación manual: indica los campos y agregaciones utilizados.
   ```

12. Compare el gráfico o propuesta de Copilot con la tabla dinámica creada manualmente. Deben coincidir en:
   - Categorías principales.
   - Orden descendente.
   - Totales por categoría.
   - Punto aproximado en el que se alcanza el 80 % acumulado.

13. Identifique si el defecto de torque se encuentra dentro de las categorías prioritarias por frecuencia. Si no está dentro del 80 %, conserve igualmente el caso de torque como foco trazable por requerimiento del curso.

14. Documente una conclusión prudente para el resumen final. Ejemplo:

   ```text
   El análisis Pareto muestra que las categorías [indicar categorías verificadas] concentran aproximadamente el 80 % de la Cantidad_No_Conforme. El defecto de torque [se encuentra/no se encuentra] dentro de este grupo prioritario por frecuencia. La priorización final debe considerar también severidad, costo, riesgo para el cliente y requisitos aplicables.
   ```

**Resultado esperado:**

- Existe una hoja llamada `Validacion_Pareto`.
- La tabla dinámica presenta tipos de defecto ordenados de mayor a menor por suma de `Cantidad_No_Conforme`.
- El gráfico combina columnas de cantidad no conforme y línea de porcentaje acumulado.
- El análisis permite identificar las categorías que concentran aproximadamente el 80 % del impacto por frecuencia.

**Verificación:**

- La suma total de `Cantidad_No_Conforme_Total` en la tabla dinámica debe coincidir con el total visible al quitar filtros de `tblNoConformidades`.
- El último valor de `Porcentaje_Acumulado` debe ser 100 % o muy cercano debido a redondeo.
- El orden de categorías del gráfico debe coincidir con el orden de la tabla dinámica.
- Confirme que el gráfico usa `Cantidad_No_Conforme`, no solo el número de registros, salvo que haya documentado una decisión distinta.
- Verifique que el Pareto no se interpreta como una prueba de causa raíz.

---

### Paso 5. Analizar y validar la tendencia mensual de no conformidades de torque

**Objetivo:** Construir un análisis temporal verificable del caso de torque y distinguir tendencia, desviación y anomalía.

**Instrucciones:**

1. Cree una nueva tabla dinámica a partir de `tblNoConformidades`:
   - Seleccione una celda de la tabla.
   - Seleccione **Insertar > Tabla dinámica**.
   - Cree la tabla en una nueva hoja.
   - Renombre la hoja como:

   ```text
   Tendencia_Torque
   ```

2. Configure el filtro específico de torque:
   - Arrastre `Tipo_Defecto` al área **Filtros**.
   - Abra el filtro de `Tipo_Defecto`.
   - Seleccione la categoría o categorías relacionadas con torque identificadas en el Paso 2.

3. Configure la tendencia mensual:
   - Arrastre `Fecha` al área **Filas**.
   - Arrastre `Cantidad_No_Conforme` al área **Valores**.
   - Confirme que se presenta como **Suma de Cantidad_No_Conforme**.

4. Si Excel muestra fechas diarias, agrúpelas:
   - Haga clic con el botón derecho sobre una fecha.
   - Seleccione **Agrupar**.
   - Seleccione **Meses** y **Años**, si el periodo abarca más de un año.
   - Confirme la agrupación.

5. Agregue `Cantidad_Inspeccionada` al área **Valores** como suma.

6. Fuera de la tabla dinámica, cree una columna auxiliar titulada:

   ```text
   Tasa_Torque
   ```

7. Calcule la tasa mensual de no conformidad de torque mediante una fórmula. Ajuste las referencias según la ubicación real de su tabla dinámica:

   ```excel
   =SI.ERROR([celda_Cantidad_No_Conforme]/[celda_Cantidad_Inspeccionada];0)
   ```

   En instalaciones de Excel configuradas en inglés, use:

   ```excel
   =IFERROR([Cantidad_No_Conforme_cell]/[Cantidad_Inspeccionada_cell],0)
   ```

8. Formatee `Tasa_Torque` como porcentaje con dos decimales.

9. Cree un gráfico de tendencia:
   - Seleccione los periodos mensuales y la columna `Tasa_Torque`.
   - Seleccione **Insertar > Gráfico de líneas con marcadores**.
   - Asigne el título:

   ```text
   Tendencia mensual de tasa de no conformidad de torque
   ```

10. Solicite una interpretación inicial a Copilot. Use un prompt como el siguiente:

   ```text
   Analiza la tendencia mensual de la tasa de no conformidad de torque construida en este libro.
   Identifica si existe una tendencia ascendente, descendente o estable, y señala meses con desviaciones relevantes.
   Describe los resultados como patrones observados, no como causas raíz.
   Indica qué factores de contexto deben investigarse antes de concluir: volumen inspeccionado, cambios de producto, línea, turno, ajuste de herramienta, método de medición, personal o criterio de inspección.
   ```

11. Compare la respuesta de Copilot con el gráfico y con los valores mensuales visibles.

12. Determine el tipo de hallazgo:
   - **Tendencia:** dirección sostenida durante varios periodos.
   - **Desviación:** diferencia frente a una referencia, promedio o meta definida.
   - **Anomalía:** mes o periodo que se aleja de lo esperado.
   - **Sin evidencia suficiente:** pocos datos, cambios de volumen importantes o información incompleta.

13. Si el archivo no contiene una meta formal de tasa de torque, no invente una. Puede usar el promedio del periodo únicamente como referencia descriptiva y documentarlo como tal.

14. Registre una conclusión basada en evidencia. Ejemplo:

   ```text
   La tasa mensual de no conformidad de torque presenta un incremento entre [periodos], con un máximo en [periodo]. El resultado se calcula como Cantidad_No_Conforme / Cantidad_Inspeccionada para los registros de torque seleccionados. La variación observada requiere confirmar cambios operativos y de inspección antes de atribuir una causa.
   ```

**Resultado esperado:**

- Existe una hoja llamada `Tendencia_Torque`.
- La tabla dinámica filtra correctamente los registros de torque.
- Se muestra la suma mensual de cantidad no conforme, la cantidad inspeccionada y la tasa calculada.
- Existe un gráfico de línea de la tasa mensual de no conformidad de torque.
- Las afirmaciones de Copilot se contrastan con valores visibles.

**Verificación:**

- Revise que la fórmula de tasa use la cantidad inspeccionada del mismo mes.
- Confirme que no hay división por cero sin control; las fórmulas deben devolver `0` o un valor documentado cuando no existan unidades inspeccionadas.
- Cambie temporalmente el filtro de torque y confirme que los resultados de la tabla dinámica se actualizan de forma coherente.
- Compruebe que el gráfico tiene eje temporal ordenado cronológicamente.
- Verifique que no se haya afirmado que un mes, turno o línea “causa” el problema solo por concentrar más registros.

---

### Paso 6. Examinar concentración por línea, turno y costo estimado

**Objetivo:** Identificar concentraciones relevantes para orientar la investigación posterior, manteniendo la diferencia entre asociación observada y causalidad.

**Instrucciones:**

1. Cree una nueva hoja de tabla dinámica y asígnele el nombre:

   ```text
   Validacion_Linea_Turno
   ```

2. Configure una tabla dinámica para el caso de torque:
   - Coloque `Línea` en **Filas**.
   - Coloque `Turno` debajo de `Línea` en **Filas**.
   - Coloque `Cantidad_No_Conforme` en **Valores** como suma.
   - Coloque `Costo_Estimado` en **Valores** como suma.
   - Coloque `Tipo_Defecto` en **Filtros** y seleccione torque.

3. Ordene la tabla por suma de `Cantidad_No_Conforme` de mayor a menor.

4. Revise si una combinación de línea y turno concentra:
   - Mayor cantidad no conforme.
   - Mayor costo estimado.
   - Alta severidad, si el campo `Severidad` está adecuadamente estructurado.

5. Si `Severidad` es numérica y representa una escala coherente, agregue el campo a **Valores** como promedio. Si es texto o contiene categorías no comparables, no calcule promedios; utilícelo solo como criterio cualitativo.

6. Solicite apoyo de Copilot con el siguiente prompt:

   ```text
   Para los registros de torque, compara Línea y Turno según suma de Cantidad_No_Conforme y suma de Costo_Estimado.
   Identifica concentraciones que deban priorizarse para investigación.
   Distingue entre:
   - resultado cuantitativo verificable,
   - patrón observado,
   - pregunta de investigación.
   No atribuyas causalidad a una línea o turno sin evidencia adicional.
   ```

7. Valide los resultados propuestos por Copilot contra la tabla dinámica.

8. Formule preguntas pendientes para la investigación de causa raíz. Ejemplos:
   - ¿Hubo cambios de herramienta de torque en la línea prioritaria?
   - ¿La línea procesó un producto diferente o un volumen superior?
   - ¿Cambió el método de inspección o la frecuencia de verificación?
   - ¿Se calibraron las herramientas de medición y apriete?
   - ¿Existen diferencias entre operadores, instrucciones de trabajo o materiales?

9. No cree acciones correctivas definitivas en este laboratorio. Registre únicamente hipótesis y preguntas que serán tratadas en el Laboratorio 05.

**Resultado esperado:**

- Existe una tabla dinámica de torque por línea y turno.
- Se pueden identificar concentraciones de cantidad no conforme y costo estimado.
- Las interpretaciones se presentan como patrones o preguntas de investigación, no como causas demostradas.

**Verificación:**

- Los totales de la tabla dinámica deben coincidir con los totales del filtro de torque en `tblNoConformidades`.
- Confirme que los campos de valores se resumen como suma, no como conteo, salvo que el análisis requiera explícitamente conteo de registros.
- Verifique que toda conclusión sobre línea o turno incluye una limitación o necesidad de investigación adicional.

---

### Paso 7. Documentar el resumen analítico verificable

**Objetivo:** Consolidar hallazgos, evidencia, interpretación, limitaciones y preguntas pendientes en una hoja trazable que pueda utilizarse en los laboratorios posteriores.

**Instrucciones:**

1. Inserte una nueva hoja en el libro.

2. Renombre la hoja exactamente como:

   ```text
   Resumen_Copilot_Validado
   ```

3. En la fila 1, cree el título:

   ```text
   Resumen analítico validado: no conformidades de calidad y caso de torque
   ```

4. Incluya debajo información de identificación:

   | Campo | Valor a registrar |
   |---|---|
   | Archivo analizado | `03_Analisis_Patrones_Validado.xlsx` |
   | Tabla fuente | `tblNoConformidades` |
   | Caso trazable | No conformidad de torque en línea de ensamble |
   | Fecha de análisis | Fecha actual |
   | Analista | Nombre o identificador corporativo del participante |
   | Estado | Borrador validado para uso académico y preparación de 8D; no constituye causa raíz confirmada |

5. A partir de la fila 8, cree una tabla con los encabezados siguientes:

   | ID_Hallazgo | Área de análisis | Hallazgo validado | Evidencia en Excel | Interpretación permitida | Limitaciones / riesgo de interpretación | Preguntas pendientes | Estado de validación |
   |---|---|---|---|---|---|---|---|

6. Registre como mínimo cinco hallazgos. Deben incluir obligatoriamente:
   - Un hallazgo del Pareto por tipo de defecto.
   - Un hallazgo de tendencia mensual de torque.
   - Un hallazgo por línea o turno relacionado con torque.
   - Un hallazgo de costos estimados o concentración de impacto.
   - Una limitación de calidad de datos o interpretación.

7. Use referencias concretas en la columna **Evidencia en Excel**. Ejemplos:
   - `Hoja Validacion_Pareto, tabla dinámica, filas 5 a 9 y gráfico Pareto.`
   - `Hoja Tendencia_Torque, tasa mensual calculada y gráfico de línea.`
   - `Hoja Validacion_Linea_Turno, filtro Tipo_Defecto = torque.`
   - `tblNoConformidades, filtro Fecha = [periodo] y Línea = [valor].`

8. Asegúrese de que la columna **Interpretación permitida** use lenguaje prudente. Ejemplos aceptables:
   - “La categoría debe priorizarse para análisis adicional por concentración de frecuencia.”
   - “Se observa un aumento en el periodo indicado.”
   - “La combinación línea-turno concentra registros y requiere revisión operacional.”
   - “El costo estimado puede servir como criterio complementario de priorización.”

9. Evite expresiones no verificables o causales. Ejemplos no aceptables:
   - “El turno B causó el defecto de torque.”
   - “La línea 2 tiene operadores mal capacitados.”
   - “El proveedor fue responsable del incremento.”
   - “La herramienta estaba descalibrada.”

10. En la columna **Estado de validación**, utilice valores como:
    - `Validado con tabla dinámica`
    - `Validado con filtro y cálculo visible`
    - `Pendiente de confirmar contexto operativo`
    - `No apto para conclusión causal`

11. Agregue al final una sección titulada:

    ```text
    Criterios de uso del análisis
    ```

12. Incluya al menos los siguientes criterios:
    - El análisis se basa en registros disponibles al momento de la revisión.
    - Los resultados son evidencia cuantitativa preliminar, no una confirmación de causa raíz.
    - Las decisiones de calidad requieren revisión humana competente.
    - Las acciones CAPA, 8D o cambios de proceso deben considerar severidad, riesgo, requisitos del cliente y evidencia adicional.
    - Las diferencias de volumen inspeccionado pueden afectar la interpretación de cantidades absolutas.

13. Formatee la tabla para facilitar la lectura:
    - Active ajuste de texto.
    - Ajuste el ancho de columnas.
    - Inmovilice la fila de encabezados si la hoja es extensa.
    - Use filtros si resulta útil.

14. Guarde el archivo mediante **Ctrl+S**.

**Resultado esperado:**

- Existe una hoja llamada `Resumen_Copilot_Validado`.
- La hoja incluye hallazgos trazables a tablas dinámicas, filtros, cálculos o gráficos.
- Se documentan limitaciones y preguntas pendientes.
- El caso de torque aparece explícitamente y conserva trazabilidad hacia los laboratorios 04 y 05.

**Verificación:**

- Confirme que existen al menos cinco hallazgos documentados.
- Cada hallazgo debe indicar una fuente visible dentro del libro.
- Cada hallazgo debe contener una interpretación permitida y una limitación o pregunta pendiente.
- Revise que ninguna fila presente una causa raíz como hecho confirmado.
- Compruebe que el nombre de hoja es exactamente `Resumen_Copilot_Validado`.

---

### Paso 8. Realizar la revisión final y guardar la evidencia

**Objetivo:** Confirmar la integridad del archivo, la trazabilidad de los análisis y la disponibilidad del entregable para los siguientes laboratorios.

**Instrucciones:**

1. Revise que el libro contenga, como mínimo, las siguientes hojas:
   - Hoja original de datos o la hoja suministrada en la fuente.
   - `Validacion_Pareto`
   - `Tendencia_Torque`
   - `Validacion_Linea_Turno`
   - `Resumen_Copilot_Validado`

2. Confirme que la tabla principal se mantiene con el nombre:

   ```text
   tblNoConformidades
   ```

3. Revise que el gráfico Pareto incluya:
   - Tipos de defecto.
   - Valores de cantidad no conforme.
   - Línea de porcentaje acumulado.
   - Eje secundario porcentual.
   - Orden descendente de categorías.

4. Revise que el gráfico de tendencia de torque incluya:
   - Periodos mensuales ordenados cronológicamente.
   - Tasa de no conformidad o medida claramente identificada.
   - Título que indique que corresponde a torque.

5. Actualice todas las tablas dinámicas:
   - Seleccione una tabla dinámica.
   - Seleccione **Analizar tabla dinámica > Actualizar**.
   - Repita para las demás tablas dinámicas o utilice **Datos > Actualizar todo** si está disponible.

6. Guarde el archivo con **Ctrl+S**.

7. Cierre Excel.

8. En el Explorador de archivos, confirme que aparece el archivo:

   ```text
   03_Analisis_Patrones_Validado.xlsx
   ```

9. Espere a que OneDrive complete la sincronización. Verifique que el archivo no muestre icono de sincronización pendiente o error.

10. Vuelva a abrir el archivo y confirme que los gráficos, tablas dinámicas y la hoja de resumen siguen disponibles.

**Resultado esperado:**

- El archivo final está guardado con el nombre obligatorio.
- Las visualizaciones y análisis pueden abrirse sin errores.
- La información está disponible en la ubicación corporativa sincronizada.
- El archivo es apto como entrada cuantitativa para el Laboratorio 04 y como fuente de hipótesis para el Laboratorio 05.

**Verificación:**

- El nombre final coincide exactamente con:

  ```text
  03_Analisis_Patrones_Validado.xlsx
  ```

- El archivo no reemplazó a `03_Base_Datos_Calidad.xlsx`.
- Las hojas de validación existen y contienen resultados.
- La hoja `Resumen_Copilot_Validado` incluye evidencia, interpretación, limitaciones y preguntas pendientes.
- La tabla `tblNoConformidades` conserva su nombre exacto.

## Validación y pruebas

Utilice la siguiente lista de comprobación antes de entregar el archivo:

| Criterio | Método de validación | Resultado esperado |
|---|---|---|
| Archivo de salida correcto | Revisar nombre en Explorador de archivos y barra de título | `03_Analisis_Patrones_Validado.xlsx` |
| Fuente preservada | Confirmar que `03_Base_Datos_Calidad.xlsx` sigue existiendo | El archivo fuente no fue sobrescrito |
| Tabla obligatoria | Seleccionar tabla y revisar Diseño de tabla | Nombre exacto: `tblNoConformidades` |
| Análisis de Pareto disponible | Revisar hoja `Validacion_Pareto` | Tabla dinámica, orden descendente y porcentaje acumulado |
| Pareto numéricamente consistente | Comparar total de tabla dinámica con total filtrado de datos | Totales coincidentes o diferencia explicada |
| Tendencia de torque disponible | Revisar hoja `Tendencia_Torque` | Tasa mensual y gráfico de tendencia |
| Caso de torque preservado | Revisar filtros y resumen | Torque aparece como foco explícito |
| Análisis por línea y turno | Revisar `Validacion_Linea_Turno` | Sumas por línea/turno para registros de torque |
| Validación humana documentada | Revisar `Resumen_Copilot_Validado` | Evidencia, interpretación, limitaciones y preguntas |
| Sin causalidad no demostrada | Leer conclusiones del resumen | No se afirman causas raíz como hechos |
| Uso corporativo responsable | Revisar ubicación de archivo | Archivo almacenado en OneDrive/SharePoint corporativo |

### Prueba de coherencia recomendada

Realice una comprobación manual adicional para uno de los hallazgos principales:

1. Seleccione una categoría prioritaria del gráfico Pareto.
2. Aplique un filtro en `tblNoConformidades` para esa categoría.
3. Compare la suma de `Cantidad_No_Conforme` con el valor de la tabla dinámica.
4. Registre el resultado en el resumen si la coincidencia es correcta.
5. Si no coincide, revise:
   - Filtros activos.
   - Campos resumidos como conteo en lugar de suma.
   - Categorías con espacios o variantes de escritura.
   - Tablas dinámicas no actualizadas.
   - Rango de datos incorrecto.

## Solución de problemas

### Problema 1: Copilot no analiza la tabla o responde sin utilizar los datos correctos

**Síntomas:**

- Copilot indica que no encuentra datos relevantes.
- La respuesta es genérica y no menciona columnas del libro.
- Copilot parece analizar un rango parcial o una hoja equivocada.
- No se muestran opciones para crear análisis o gráficos.

**Causa probable:**

- No está seleccionada una celda dentro de `tblNoConformidades`.
- La tabla no tiene el nombre requerido o contiene encabezados ambiguos.
- El archivo no está guardado en OneDrive/SharePoint corporativo o aún no se ha sincronizado.
- La licencia de Microsoft 365 Copilot no está disponible en la sesión actual.

**Corrección:**

1. Guarde el archivo en la ruta corporativa asignada y espere a que OneDrive sincronice.
2. Seleccione una celda dentro de `tblNoConformidades`.
3. Confirme el nombre de tabla en **Diseño de tabla**.
4. Cierre y vuelva a abrir el libro en Excel para Microsoft 365 con la cuenta corporativa correcta.
5. Abra Copilot nuevamente y especifique en el prompt el nombre de tabla:

   ```text
   Analiza la tabla tblNoConformidades.
   ```

6. Si Copilot continúa sin estar disponible, documente la incidencia, complete las validaciones manuales con tablas dinámicas y comuníquelo al instructor o soporte de TI corporativo.

### Problema 2: El gráfico Pareto o la tendencia mensual muestra resultados incoherentes

**Síntomas:**

- El porcentaje acumulado no termina cerca de 100 %.
- El gráfico Pareto no está ordenado de mayor a menor.
- La tendencia mensual muestra fechas desordenadas o días individuales.
- La tasa de torque es excesivamente alta, igual a cero o presenta errores de división.
- Los valores del gráfico no coinciden con los filtros de la tabla original.

**Causa probable:**

- La tabla dinámica usa conteo de registros en lugar de suma de `Cantidad_No_Conforme`.
- El segundo campo de valores no está configurado como porcentaje acumulado.
- Las fechas no fueron agrupadas por meses y años.
- La fórmula de tasa divide por una celda incorrecta o por cantidad inspeccionada igual a cero.
- Existen filtros activos o las tablas dinámicas no se han actualizado.

**Corrección:**

1. En la tabla dinámica, revise cada campo en **Valores** y confirme:
   - `Suma de Cantidad_No_Conforme`.
   - `Suma de Cantidad_Inspeccionada`.
   - `Suma de Costo_Estimado`, cuando corresponda.

2. Para Pareto, configure el segundo valor como:

   ```text
   Mostrar valores como > % del total acumulado en > Tipo_Defecto
   ```

3. Ordene las categorías de mayor a menor por `Cantidad_No_Conforme_Total`.

4. Para tendencia, haga clic con el botón derecho en una fecha y seleccione:

   ```text
   Agrupar > Meses y Años
   ```

5. Corrija la fórmula de tasa para que use valores del mismo periodo:

   ```excel
   =SI.ERROR([celda_Cantidad_No_Conforme]/[celda_Cantidad_Inspeccionada];0)
   ```

6. Ejecute **Datos > Actualizar todo**, revise filtros activos y compare nuevamente contra `tblNoConformidades`.

## Limpieza

1. Guarde todos los cambios en:

   ```text
   03_Analisis_Patrones_Validado.xlsx
   ```

2. Confirme que el archivo se sincronizó con OneDrive for Business o SharePoint Online.

3. Cierre Excel y cualquier instancia adicional del archivo para evitar conflictos de sincronización.

4. No elimine:
   - `03_Analisis_Patrones_Validado.xlsx`
   - `03_Base_Datos_Calidad.xlsx`
   - `02_Biblioteca_Prompts_Calidad.docx`

5. No elimine las hojas de validación creadas durante la práctica, ya que serán utilizadas como evidencia de trazabilidad en los siguientes laboratorios.

6. Si creó archivos temporales no requeridos, elimínelos únicamente si no contienen evidencia, comentarios o versiones necesarias para el curso.

## Resumen

En esta práctica utilizaste Microsoft Excel y Copilot para explorar una base de datos de no conformidades y convertir resultados preliminares en hallazgos verificables. Creaste un Pareto por tipo de defecto, una tendencia mensual de la no conformidad de torque y un análisis de concentración por línea, turno y costo estimado.

La actividad reforzó que Copilot puede acelerar la exploración y proponer interpretaciones útiles, pero no reemplaza la validación humana. Los resultados aceptados deben estar respaldados por filtros, cálculos, tablas dinámicas o gráficos visibles, y deben diferenciar entre datos observados, patrones, desviaciones, anomalías e hipótesis de investigación.

El archivo `03_Analisis_Patrones_Validado.xlsx` será la evidencia cuantitativa de entrada para el borrador de reporte 8D del Laboratorio 04 y para el diagnóstico de causa raíz y mejora del Laboratorio 05.

### Recursos de consulta

- [Soporte de Microsoft: Copilot en Excel](https://support.microsoft.com/es-es/copilot-excel)
- [Microsoft Learn: Analizar datos con Copilot en Excel](https://learn.microsoft.com/es-es/copilot/excel/)
- [ASQ: Diagrama de Pareto](https://asq.org/quality-resources/pareto)
- [ISO: Gestión de la calidad y familia ISO 9000](https://www.iso.org/iso-9001-quality-management.html)
