# Práctica: Análisis de patrones en una base de datos de calidad con apoyo visual automático

### Duración Estimada
90 minutos

---

### Descripción de la Actividad
En este laboratorio práctico, asumirás el rol de un Ingeniero de Datos y Calidad en Cerámicas del Norte. Utilizarás Microsoft 365 Copilot Chat para generar un dataset simulado de producción de porcelanicos, optimizar la estructura de los datos para su procesamiento en Microsoft Excel, realizar un análisis estadístico de patrones de fallas, diseñar la maqueta visual de un tablero de control (dashboard) y redactar el informe final de mejora continua para la gerencia.

---

## Objetivos del Laboratorio
- Generar datos numéricos simulados de defectos y parámetros de proceso en formato tabular limpio.
- Depurar y optimizar la estructura de los datos para su importación directa a Microsoft Excel.
- Identificar patrones de fallas, correlaciones térmicas y frecuencias de descarte mediante análisis asistido por IA.
- Diseñar la instrucción gráfica y generar el render de un dashboard ejecutivo de calidad en Copilot Designer.
- Redactar un informe ejecutivo de mejora continua para Microsoft Word y la alerta correspondiente para Microsoft Outlook.

---

## Prerrequisitos
- Acceso a Microsoft 365 Copilot Chat (Enterprise / Web).

---

### Fase 1: Generación de Datos Simulados de Producción

**Herramienta objetivo:** Copilot Chat (Generación de Datos)

Genera un conjunto de datos realista de la línea de cocción y prensado de porcelánicos de gran formato para simular el historial de un mes de producción.

```
Actúa como un Ingeniero de Datos Industrial en una fábrica de porcelánicos.

Genera una base de datos simulada de 10 registros de producción para Cerámicas del Norte en una tabla Markdown estándar. La tabla debe incluir exactamente estas columnas:
| ID_Lote | Fecha | Línea | Formato_cm | Temp_Horno_C | Humedad_Prensado_% | Piezas_Procesadas | Defectos_Alabeo | Defectos_Porosidad | Scrap_Total_% |

Asegúrate de incluir variaciones reales donde las temperaturas superiores a 1220°C y humedades menores al 5% incrementen el porcentaje de scrap.
```

---

### Fase 2: Optimización y Limpieza de la Estructura para Excel

**Herramienta objetivo:** Copilot Chat (Estructuración para Microsoft Excel)

Pide a Copilot que refine la tabla generada en la Fase 1 para garantizar una importación limpia y directa sin errores de formato.

```
Con base en la tabla de datos simulados generada en la fase anterior, optimízala para exportación directa a Microsoft Excel.

Requisitos de la tabla:
1. Formatea la tabla en Markdown estándar con bordes claros (| Columna 1 | Columna 2 |).
2. Añade 2 columnas adicionales calculadas a la derecha: | Costo_Est_Merma_USD | Estado_Lote (Aprobado/Rechazado) |.
3. Asegúrate de que las fechas tengan formato YYYY-MM-DD y los porcentajes usen decimales estándar sin símbolos dentro de la celda.

*(Copia y pega la tabla resultante directamente en Microsoft Excel).*

```

---

### Fase 3: Análisis de Patrones y Correlación de Fallas

**Herramienta objetivo:** Copilot Chat (Análisis Estadístico)

Utiliza el contexto de la tabla optimizada para identificar las causas principales de variabilidad en la calidad de las piezas.

```
Con base en los datos acumulados en la tabla optimizada de la fase anterior, realiza un análisis de patrones de falla y correlaciones operacionales.

Genera un diagnóstico estructurado que incluya:
1. Análisis de Correlación: Relación entre la Temperatura del Horno, la Humedad y el incremento de Defectos por Alabeo.
2. Identificación del Lote Crítico: Lote con mayor impacto económico de merma y sus variables descalibradas.
3. Regla de Control Sugerida: 2 límites operacionales (máximos y mínimos) para evitar que el Scrap supere el 3%.

```

---

### Fase 4: Diseño Visual y Generación del Dashboard de Calidad

**Herramienta objetivo:** Copilot Chat / Copilot Designer (Generador de Imágenes)

Genera una representación visual fotorrealista de la pantalla del tablero de control (Dashboard) que consolidaría estos datos en planta para su uso en presentaciones de Microsoft PowerPoint.

```
Con base en los indicadores y métricas de scrap, temperatura y defectos calculados en las fases anteriores, genera inmediatamente una imagen del Tablero de Control Ejecutivo (Quality Dashboard) para Cerámicas del Norte.

Estilo y Composición de la imagen:
- Estilo: Interfaz de usuario (UI) moderna de Power BI / Tablero Industrial, render 8K, diseño oscuro elegante con acentos en verde neon y rojo de alerta.
- Elementos Centrales: Gráfico de líneas mostrando la tendencia de temperatura vs. % de scrap, gráfico de pastel con la distribución de defectos (alabeo vs. porosidad) y tarjetas KPIs gigantes mostrando "Scrap Promedio: 3.4%" y "Costo Total Merma".
- Entorno: Render fotorrealista de una pantalla táctil industrial instalada en la sala de control de la fábrica de porcelanicos.

```

---

### Fase 5: Redacción del Informe Ejecutivo de Mejora Continua

**Herramienta objetivo:** Copilot Chat para documentación en Microsoft Word

Sintetiza los hallazgos del análisis de datos y la visualización del dashboard en un informe formal adaptado para Microsoft Word.

```
Actúa como Director de Calidad. Con base en la base de datos analizada, los patrones de alabeo identificados y el dashboard generado, redacta un Informe Ejecutivo de Mejora Continua para la Gerencia de Operaciones.

Estructura el documento para Microsoft Word en 3 secciones:
1. Resumen de Desempeño Mensual: Evaluaciones de volúmenes procesados, pérdidas por scrap y costo de merma.
2. Hallazgos Clave de Proceso: Evidencia del impacto de la temperatura del horno sobre el alabeo de piezas de gran formato.
3. Plan de Acción Kaizen: 3 acciones correctivas concretas con responsables y plazos de ejecución.

```

---

### Fase 6: Redacción de la Alerta Técnica por Correo

**Herramienta objetivo:** Copilot Chat / Preparación para Microsoft Outlook

Transforma las recomendaciones del informe en una notificación inmediata dirigida a los supervisores de línea.

```
Actúa como Ingeniero de Calidad. Con base en el informe de mejora continua, redacta un correo de acción inmediata para Microsoft Outlook dirigido a los Jefes de Planta y Mantenimiento.

El correo debe contener:
- Asunto: AJUSTE OPERATIVO URGENTE - Control de Temperatura en Horno 1 para Evitar Alabeo.
- Cuerpo: Explicación breve del patrón de fallas detectado en los lotes críticos, los nuevos límites de temperatura aprobados (máximo 1215°C) y la solicitud de calibración de termopares antes del siguiente turno.

```

---

### Reto Práctico: Análisis Autónomo de Eficiencia Energética vs. Defectos

**Herramienta objetivo:** Copilot Chat (Resolución Autónoma)

**Escenario de Desafío:**
La gerencia requiere reducir el consumo de gas natural en los hornos un 5% sin afectar la calidad del porcelánico de 120x240 cm. Sospechas que reducir el tiempo de permanencia en el horno aumentará los defectos de falta de cocción (absorción de agua >0.5%).

**Tu Desafío:**
1. Escribe y ejecuta un primer prompt conciso para que Copilot simule una pequeña tabla Markdown de 5 registros que compare Consumo de Gas (m³), Tiempo de Cocción (min) y Absorción de Agua (%).
2. Escribe y ejecuta un segundo prompt breve para que te entregue la conclusión técnica de si es viable la reducción de gas y redacte una nota corta para adjuntar al informe en Microsoft Word.

Pistas para construir tus prompts:
- Mantenlos de máximo 3 líneas cada uno.
- Asigna el rol de Ingeniero de Eficiencia Energética y Cerámica.
- Exige salidas delimitadas (Tabla Markdown para la parte 1, texto de conclusiones para la parte 2).

---

## Conceptos Clave para Recordar

- Sintaxis Tabular Limpia: Garantizar que la IA entregue datos formateados en Markdown sin símbolos intercalados permite copiar directamente las celdas a Microsoft Excel.
- Análisis Predictivo Asistido: Identificar correlaciones entre variables de proceso (temperatura/humedad) y defectos (alabeo) agiliza la toma de decisiones sin requerir software estadístico complejo.
- Visualización de Datos Prompteada: Trasladar métricas numéricas a prompts de imagen permite obtener prototipos visuales de dashboards listos para comités ejecutivos.

---

## Resultado Esperado del Estudiante

Al finalizar el estudiante habrá generado en Copilot Chat:
1. La base de datos simulada de 10 registros de producción.
2. La tabla optimizada con columnas calculadas lista para copiar en Microsoft Excel.
3. El análisis de patrones de falla y correlación térmica.
4. El render fotorrealista del tablero de control (Dashboard) generado en Copilot Designer.
5. El informe ejecutivo de mejora continua redactado para Microsoft Word.
6. El correo de alerta técnica redactado para Microsoft Outlook.
7. Los dos prompts propios resueltos para el reto de eficiencia energética.
