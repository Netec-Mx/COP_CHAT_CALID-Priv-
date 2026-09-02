# Práctica: Generación automatizada de un reporte operativo 8D y un instructivo de proceso.

### Duración Estimada
90 minutos

---

### Descripción de la Actividad
En este laboratorio práctico, asumirás el rol de Especialista en Documentación y Mejora Continua en Cerámicas del Norte. Utilizarás Microsoft 365 Copilot Chat para estructurar la documentación técnica de resolución de problemas bajo la metodología 8D (Ocho Disciplinas), diseñar material de apoyo gráfico para operarios, adaptar el contenido en un instructivo operativo estándar para Microsoft Word y generar el plan de comunicación para Microsoft Outlook y Microsoft PowerPoint.

---

## Objetivos del Laboratorio
- Consolidar la información de una falla masiva en la metodología estándar 8D.
- Generar cuadros de contención y métricas en tablas Markdown para su migración a Microsoft Excel.
- Diseñar la instrucción visual y generar una ilustración técnica fotorrealista para el instructivo de trabajo en Copilot Designer.
- Estructurar el Informe 8D y el Instructivo Operativo de Trabajo (SOP) formateados para Microsoft Word.
- Redactar la notificación ejecutiva para Microsoft Outlook y la síntesis visual para Microsoft PowerPoint.

---

## Prerrequisitos
- Acceso a Microsoft 365 Copilot Chat (Enterprise / Web).

---

### Fase 1: Estructuración del Reporte 8D (Disciplinas D1 a D4)

**Herramienta objetivo:** Copilot Chat (Análisis y Metodología 8D)

Consolida la información de un evento crítico de grietas estructurales en lotes de porcelánico de gran formato (120x240 cm) aplicando las primeras cuatro disciplinas del método 8D.

```
Actúa como Ingeniero Senior de Calidad en Cerámicas del Norte.

Estructura las primeras 4 disciplinas (D1 a D4) de un Informe 8D para un evento crítico de grietas en porcelanicos de 120x240 cm:
- D1 (Equipo): Asigna 4 roles clave de planta.
- D2 (Problema): Describe la falla con la técnica Qué, Dónde, Cuándo y Alcance (2,500 m² afectados).
- D3 (Contención): Define 2 acciones inmediatas de aislamiento en almacén.
- D4 (Causa Raíz): Detalla el análisis técnico identificando exceso de presión en el prensado y enfriamiento rápido en el horno.
```

---

### Fase 2: Matriz de Acciones Correctivas para Excel (Disciplinas D5 a D8)

**Herramienta objetivo:** Copilot Chat para estructuración en Microsoft Excel (Tabla Markdown)

Estructura el plan de cierre del 8D en una matriz clara lista para copiar directamente a Microsoft Excel.

```
Con base en el análisis 8D de la fase anterior, genera una tabla estructurada en formato Markdown estándar para exportar directamente a Microsoft Excel con las Disciplinas D5 a D8.

Requisitos de la tabla:
1. Utiliza bordes claros en sintaxis Markdown (| Columna 1 | Columna 2 |).
2. La primera fila debe contener exactamente estos encabezados:
| Disciplina 8D | Acción Definida | Responsable | Fecha Límite | Estado de Verificación | Costo Est. (USD) |
3. Completa la tabla con 4 filas detallando las acciones preventivas, correctivas y la validación del cierre del problema de grietas.

Fuera de la tabla, en texto plano, escribe una nota técnica sobre la efectividad comprobada de la medida.
```

---

### Fase 3: Ingeniería de Prompts Visuales — Creación de la Instrucción para el Instructivo

**Herramienta objetivo:** Copilot Chat (Diseño de Instrucción de Imagen)

Genera la instrucción detallada para obtener una ilustración visual técnica que acompañe las instrucciones de inspección en el documento final.

```
Actúa como un Diseñador Técnico Industrial. Redacta una instrucción de imagen concisa (máximo 3 líneas) lista para ejecutar en Copilot Designer. Debe solicitar una fotografía fotorrealista de un operador comprobando la presión neumática de la prensa continua de porcelánicos, con indicador de manómetro en zona verde y marcado gráfico de inspección.
```

---

### Fase 4: Ejecución del Prompt Visual en Copilot Designer

**Herramienta objetivo:** Copilot Chat / Copilot Designer (Generador de Imágenes)

**Instrucción para el estudiante:**
Copia la instrucción de imagen de 3 líneas que Copilot te entregó en la Fase 3, pégala en el chat y ejecútala.

*(Al enviarla, Copilot Designer generará la imagen fotorrealista del control de presión en la prensa, lista para adjuntarse en el instructivo de Microsoft Word).*

---

### Fase 5: Redacción del Instructivo Operativo Estándar (SOP) en Word

**Herramienta objetivo:** Copilot Chat para documentación en Microsoft Word

Transforma las soluciones del 8D en un Instructivo de Trabajo Estándar (SOP) formateado para Microsoft Word.

```
Actúa como Coordinador del Sistema de Gestión de Calidad (ISO 9001). Con base en el 8D resuelto y la imagen de control de prensa generada, redacta el Instructivo Operativo Estándar (SOP-CAL-042): "Operación y Control de Presión en Prensado de Porcelánico de Gran Formato".

Estructura el documento para Microsoft Word en 4 secciones:
1. Objetivo y Control de Parámetros (Presión nominal y límites de tolerancia).
2. Procedimiento de Inspección Paso a Paso (4 pasos para el operador de turno).
3. Verificación de Enfriamiento en Horno (Rangos térmicos seguros).
4. Registro de Liberación de Lote y Manejo de Desviaciones.
```

---

### Fase 6: Comunicación del Cierre del 8D por Outlook y PowerPoint

**Herramienta objetivo:** Copilot Chat para Microsoft Outlook y Microsoft PowerPoint

Sintetiza el cierre del caso en una comunicación formal por correo y la diapositiva resumen de cierre.

```
Con base en el 8D finalizado y el SOP redactado, genera dos entregables:

1. Correo para Microsoft Outlook: Redacta una notificación formal para el Gerente de Planta y la Dirección Comercial anunciando el cierre del 8D, la liberación del lote controlado y la publicación del nuevo SOP.
2. Diapositiva para Microsoft PowerPoint: Diseña la estructura de una diapositiva ejecutiva de cierre que contenga título, 3 viñetas breves con el ahorro de scrap logrado y la sugerencia de ubicación de la imagen del SOP.
```

---

### Reto Práctico: Redacción Autónoma de Procedimiento para Limpieza de Matrices

**Herramienta objetivo:** Copilot Chat (Resolución Autónoma)

**Escenario de Desafío:**
Se detectó que la acumulación de residuo de arcilla en los moldes/matrices de la prensa genera marcas superficiales repetitivas en el 100% de la producción de piezas de 120x120 cm. Se requiere redactar un procedimiento de limpieza rápida de matrices sin detener la línea por más de 8 minutos.

**Tu Desafío:**
1. Escribe y ejecuta un primer prompt conciso para que Copilot redacte un SOP express de 3 pasos de limpieza con matriz de elementos de protección personal (EPP) en tabla Markdown para Excel.
2. Escribe y ejecuta un segundo prompt de 2 líneas para generar una alerta de correo en Outlook convocando al equipo de mantenimiento al procedimiento de limpieza.

Pistas para construir tus prompts:
- Mantenlos de máximo 3 líneas cada uno.
- Asigna el rol de Especialista en Mantenimiento Ceramista.
- Delimita los productos esperados (Tabla Markdown para la parte 1, formato correo para la parte 2).

---

## Conceptos Clave para Recordar

- Metodología 8D Estructurada con IA: Dividir la resolución del problema entre fases analíticas (D1-D4) y matrices de ejecución (D5-D8) facilita la documentación ISO 9001.
- Estandarización Técnica a Procedimientos: Traducir las acciones correctivas de un 8D directamente a un SOP de Word evita la reincidencia de fallas en planta.
- Integración Multicanal: La solución a un problema operativo genera insumos técnicos para Word, datos numéricos para Excel, imágenes para SOPs, alertas para Outlook y resúmenes para PowerPoint.

---

## Resultado Esperado del Estudiante

Al finalizar los 90 minutos del laboratorio, el estudiante habrá generado en Copilot Chat:
1. La estructura analítica de las Disciplinas D1 a D4 del reporte 8D.
2. La matriz de acciones D5 a D8 formateada y lista para copiar en Microsoft Excel.
3. La instrucción de texto para generar la imagen técnica del control de presión.
4. El render fotorrealista generado por Copilot Designer a partir de la instrucción de la Fase 3.
5. El Instructivo Operativo Estándar (SOP-CAL-042) formateado para Microsoft Word.
6. El correo de notificación de cierre para Microsoft Outlook y la estructura de diapositiva para Microsoft PowerPoint.
7. Los dos prompts propios resueltos para el reto de limpieza de matrices.
