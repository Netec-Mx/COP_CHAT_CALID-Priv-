# Práctica: Resolución de un problema real de la operación utilizando Copilot para deducir la causa raíz.

### Duración Estimada
90 minutos

---

### Descripción de la Actividad
En este laboratorio práctico, asumirás el rol de un Facilitador de Mejora Continua en Cerámicas del Norte. Frente a un problema recurrente de rotura de piezas porcelánicas de gran formato a la salida del secador vertical, utilizarás Microsoft 365 Copilot Chat para aplicar el método de los 5 Porqués, construir la estructura lógica de un Diagrama de Ishikawa (Causa-Efecto) diagramado con líneas de texto ASCII, generar un gráfico analítico de distribución mediante código Mermaid.js para su renderizado directo y documentar el plan de acción para los sistemas de la empresa.

---

## Objetivos del Laboratorio
- Deducción asistida por IA de causas raíz complejas utilizando la técnica de los 5 Porqués.
- Construcción de un Diagrama de Ishikawa de 6M con líneas de texto limpio para su integración en documentos técnicos.
- Generación de código de diagramación técnica (Mermaid.js) para renderizar gráficos de causa-efecto y Pareto sin usar imágenes.
- Estructuración de matrices de contención en tablas Markdown compatibles con Microsoft Excel.
- Redacción del reporte de causa raíz para Microsoft Word, la notificación operativa para Microsoft Outlook y la diapositiva resumen para Microsoft PowerPoint.

---

## Prerrequisitos
- Acceso a Microsoft 365 Copilot Chat (Enterprise / Web).

---

### Fase 1: Deducción de Causa Raíz mediante los 5 Porqués

**Herramienta objetivo:** Copilot Chat (Análisis Deductivo)

Utiliza Copilot Chat para ejecutar la técnica iterativa de los 5 Porqués a partir de un síntoma de falla recurrente en la línea de prensado y secado.

```
Actúa como un Especialista Master en Metodologías Lean y Diagnóstico Cerámico.

Analiza la siguiente falla en Cerámicas del Norte: "Rotura transversal del 6.5% en piezas porcelánicas de 120x240 cm al salir del secador vertical".

Aplica la metodología de los 5 Porqués encadenando cada pregunta con la respuesta anterior hasta llegar a la causa raíz sistémica o de mantenimiento.

Estructura la respuesta numerando claramente del Porqué 1 al Porqué 5, evaluando factores como la humedad del prensado, el gradiente de temperatura en el secador, la alineación de rodillos y los programas de mantenimiento preventivo.

```

---

### Fase 2: Diagrama de Ishikawa Esquemático con Líneas ASCII

**Herramienta objetivo:** Copilot Chat (Visualización Estructurada en Texto)

Pide a Copilot Chat que traduzca el análisis del problema en un Diagrama de Ishikawa (6M: Mano de obra, Maquinaria, Métodos, Materiales, Medio Ambiente y Medición) dibujado exclusivamente mediante líneas de texto y conectores planos.

```
Con base en el problema de rotura de piezas porcelánicas y los 5 Porqués desarrollados en la fase anterior, genera un Diagrama de Ishikawa (Espina de Pescado) completo estructurado con las 6M.

Requisitos del formato:
1. Diseña el diagrama utilizando únicamente líneas de texto, guiones, barras y conectores (|, -, +, >) en formato de bloque de código (`text`).
2. Muestra la flecha central que apunta al efecto principal ("Rotura de Piezas en Secador").
3. Despliega las 6 ramas principales (Maquinaria, Métodos, Materiales, Medición, Mano de Obra, Medio Ambiente) conectadas a la espina central con 2 causas secundarias por cada rama.

```

---

### Fase 3: Generación del Gráfico Analítico con Código Mermaid.js

**Herramienta objetivo:** Copilot Chat (Generación de Gráfico Vectorial / Código de Diagramación)

Utiliza Copilot Chat para generar el código técnico en sintaxis Mermaid.js que permite renderizar el gráfico del árbol de causas o diagrama de Ishikawa de forma nativa en visores Markdown o herramientas de documentación técnica, evitando el uso de imágenes fotorrealistas.

```
Con la información de las causas raíz identiﬁcadas, genera el código completo en sintaxis Mermaid.js para renderizar un diagrama de causas en bloque de código `mermaid`.

Requisitos del código Mermaid:
1. Utiliza la sintaxis de diagrama de flujo (`graph TD` o `graph LR`).
2. Define el nodo principal con el efecto central [Rotura en Secador 6.5%].
3. Crea subsistemas para las 3 causas principales detectadas (Gradiente Térmico, Humedad Excesiva y Desalineación de Rodillos).
4. Conecta cada causa principal con sus factores contribuyentes específicos usando etiquetas en las flechas.

```

---

### Fase 4: Matriz de Acciones Correctivas para Excel

**Herramienta objetivo:** Copilot Chat para estructuración en Microsoft Excel (Tabla Markdown)

Estructura la solución a las causas identificadas en el Ishikawa dentro de una matriz de contención y prevención para Microsoft Excel.

```
Con base en el Diagrama de Ishikawa y el código de gráfico generado, elabora una tabla Markdown estructurada para copiar directamente a Microsoft Excel.

Requisitos de la tabla:
1. Usa bordes claros en sintaxis Markdown (| Columna 1 | Columna 2 |).
2. La primera fila debe contener exactamente estos encabezados:
| Categoría (6M) | Causa Raíz Detectada | Acción Correctiva / Preventiva | Responsable | Impacto Estimado (% Reducción) | Costo de Implementación (USD) |
3. Llena la tabla con 4 filas correspondientes a las causas de mayor peso halladas en la Maquinaria, Métodos, Materiales y Medición.

```

---

### Fase 5: Redacción del Reporte Técnico de Causa Raíz en Word

**Herramienta objetivo:** Copilot Chat para documentación en Microsoft Word

Sintetiza la deducción de la causa raíz, la estructura del Ishikawa y el plan de mitigación en un reporte formal adaptado para Microsoft Word.

```
Actúa como Jefe de Mejora Continua. Con base en los 5 Porqués, el esquema Ishikawa y la matriz de acciones desarrollados en este chat, redacta el Informe Técnico de Diagnóstico de Causa Raíz para Microsoft Word.

Estructura el documento en 3 secciones:
1. Diagnóstico del Problema y Metodología Aplicada: Resumen del evento de rotura y hallazgos clave de los 5 Porqués.
2. Transcripción del Análisis Ishikawa (6M): Listado detallado de factores por categoría.
3. Plan de Erradicación de Falla: Resumen de las modificaciones operativas y de mantenimiento a implementar en el secador vertical.

```

---

### Fase 6: Comunicación de Diagnóstico por Outlook y PowerPoint

**Herramienta objetivo:** Copilot Chat para Microsoft Outlook y Microsoft PowerPoint

Transforma los hallazgos del diagnóstico en una notificación operativa por correo y la diapositiva ejecutiva para el comité.

```
Con base en el reporte de causa raíz finalizado, genera dos entregables de comunicación:

1. Correo para Microsoft Outlook: Redacta una notificación para los Supervisores de Mantenimiento y Operaciones informando la causa raíz hallada (falla en termopar de la zona 2 del secador) y la instrucción de calibración inmediata.
2. Diapositiva para Microsoft PowerPoint: Estructura una diapositiva ejecutiva con el título "Diagnóstico y Solución: Rotura en Secador", 3 puntos en viñetas con los datos clave del hallazgo y la indicación de insertar el código gráfico Mermaid o esquema ASCII en el panel central.

```

---

### Reto Práctico: Diagnóstico Expres de Falla por "Bolsas de Aire" en Esmaltado

**Herramienta objetivo:** Copilot Chat (Resolución Autónoma)

**Escenario de Desafío:**
Se presenta un defecto recurrente de "bolsas de aire" (ampollas atrapadas bajo la capa de esmalte) en la línea de esmaltado rápido de piezas de 120x120 cm, provocando el rechazo del 5% del lote. La sospecha inicial apunta a la viscosidad del esmalte, pero la causa podría estar en la presión del soplador de polvo previo a la aplicación.

**Tu Desafío:**
1. Escribe y ejecuta un primer prompt conciso de máximo 3 líneas para que Copilot realice los 5 Porqués de este problema e identifique la causa raíz.
2. Escribe y ejecuta un segundo prompt breve para que te entregue el gráfico técnico en código Mermaid.js que conecte la causa con la solución y redacte una nota de alerta por correo para Outlook.

Pistas para construir tus prompts:
- Mantenlos de máximo 3 líneas cada uno.
- Asigna el rol de Ingeniero Ceramista y Especialista en Esmaltes.
- Solicita entregables específicos (5 Porqués en texto, código `mermaid` y borrador de correo).

---

## Conceptos Clave para Recordar

- Deducción Lógica con IA: Los 5 Porqués guiados por Copilot permiten pasar de síntomas superficiales a causas raíz técnicas en minutos.
- Gráficos por Código vs. Imágenes: La generación de código como Mermaid.js o diagramas ASCII permite crear esquemas visuales precisos, editables y livianos sin depender de herramientas de diseño gráfico o generadores fotorrealistas.
- Estandarización de Esquemas 6M: Mapear causas en las categorías de Mano de Obra, Maquinaria, Métodos, Materiales, Medio Ambiente y Medición asegura no pasar por alto variables críticas de proceso.

---

## Resultado Esperado del Estudiante

Al finalizar los 90 minutos del laboratorio, el estudiante habrá generado en Copilot Chat:
1. El análisis deductivo de los 5 Porqués sobre la rotura de piezas en el secador.
2. El Diagrama de Ishikawa estructurado visualmente mediante líneas de texto ASCII.
3. El código Mermaid.js listo para renderizar el gráfico analítico de causas.
4. La matriz de acciones correctivas formateada para Microsoft Excel.
5. El Informe Técnico de Diagnóstico de Causa Raíz formateado para Microsoft Word.
6. El correo de notificación para Microsoft Outlook y la estructura de diapositiva para Microsoft PowerPoint.
7. Los dos prompts propios resueltos para el reto de diagnóstico de bolsas de aire en esmaltado.
