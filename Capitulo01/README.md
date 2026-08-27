# Práctica: Ejercicios rápidos de exploración y validación de casos reales de uso en planta.

### Duración Estimada
30 minutos

---

### Descripción de la Actividad
En este laboratorio rápido de familiarización, asumirás el rol de un Ingeniero de Calidad y Procesos en Cerámicas del Norte. Utilizando Microsoft 365 Copilot Chat, explorarás cómo la Inteligencia Artificial puede acelerar la resolución de incidencias en la línea de producción de recubrimientos porcelánicos, estandarizar criterios normativos y preparar documentación operativa para el personal de planta.

---

## Objetivos del Laboratorio
- Identificar casos de uso directos de Microsoft 365 Copilot Chat en el control de calidad industrial.
- Formular instrucciones claras para clasificar defectos de producción en pisos y muros cerámicos.
- Redactar un instructivo técnico breve para su implementación en la operación diaria de la fábrica.

---

## Prerrequisitos
- Acceso a Microsoft 365 Copilot Chat (Enterprise / Web).

---

### Fase 1: Identificación y Clasificación de Defectos de Planta

**Herramienta objetivo:** Copilot Chat (Investigación y Clasificación Técnica)

Abre Microsoft 365 Copilot Chat e ingresa la siguiente instrucción para obtener un catálogo de defectos comunes en recubrimientos y su impacto en la calidad.

```
Actúa como un Ingeniero Senior de Calidad en una fábrica de recubrimientos cerámicos y porcelánicos de gran formato. 

Analiza los problemas más recurrentes en la etapa de horneado y esmaltado. Genera una lista clasificada que incluya:
1. Tres defectos estéticos (ej. tono desigual, pinholes o porosidad, grietas superficiales).
2. Tres defectos estructurales o mecánicos (ej. curvatura/alabeo, baja resistencia al impacto PEI, alta absorción de agua).
3. La causa técnica raíz más probable en el horno o en la preparación de la barbotina para cada uno de los 6 defectos.
```

---

### Fase 2: Estructuración de la Tabla de Criterios de Aceptación/Rechazo

**Herramienta objetivo:** Copilot Chat para estructuración en Microsoft Excel (Tabla Markdown)

Utiliza Copilot Chat para convertir la clasificación de defectos en una matriz de inspección formateada para ser copiada directamente a Microsoft Excel.

```
Con la información procesada en el paso anterior, genera una tabla estructurada en formato de tabla de Markdown estándar para que sea interpretada visualmente por el chat y se pueda copiar directamente a Microsoft Excel.

Requisitos de la tabla:
1. Genera una tabla con bordes claros utilizando la sintaxis estándar de Markdown (| Columna 1 | Columna 2 |).
2. La primera fila debe contener exactamente estos encabezados:
| Tipo de Defecto | Nombre del Defecto | Etapa del Proceso | Criterio de Aceptación (Tolerancia mm/%) | Acción Inmediata en Planta |
3. Completa la tabla con los 6 defectos analizados anteriormente.

Fuera de la tabla, en un párrafo corto de texto normal, escribe una recomendación para el inspector de calidad de turno.
```

---

### Fase 3: Redacción Express del Instructivo de Inspección

**Herramienta objetivo:** Copilot Chat para documentación en Microsoft Word

Pide a Copilot Chat que transforme la matriz en una guía rápida de inspección lista para imprimir o pegar en Microsoft Word.

```
Actúa como Coordinador del Sistema de Gestión de Calidad (ISO 9001) de Cerámicas del Norte. Redacta una Guía Rápida de Inspección Visual para Operadores de Línea de Esmaltado.

El documento debe tener el siguiente formato corto para Microsoft Word:
1. Objetivo: Propósito del control visual en menos de 40 palabras.
2. Pasos de Inspección: 4 pasos secuenciales para validar la calidad de la pieza al salir del secador.
3. Protocolo de Notificación: A quién y cómo reportar cuando la tasa de descarte supere el 3% en una hora.
```

---

### Reto Práctico: Respuesta Express a Incidencia en Horno

**Herramienta objetivo:** Copilot Chat (Resolución Autónoma)

**Escenario de Desafío:**
Durante el turno de la madrugada, la línea 2 reporta un pico del 8% de merma por "alabeo" (curvatura excesiva en las esquinas de los porcelánicos de 120x120 cm). El jefe de turno sugiere bajar la temperatura del horno, pero tú sospechas que el problema está en la velocidad del ciclo de enfriamiento o en la humedad del prensado.

**Tu Desafío:**
Debes redactar y ejecutar tu propio prompt en Copilot Chat sin usar una plantilla. Tu instrucción debe solicitar una recomendación técnica inmediata que evalúe ambas variables sin detener por completo la producción.

Pistas para construir tu prompt estratégico:
- **Asignación de Rol:** Asigna a Copilot el rol de Especialista en Cerámica Térmica y Procesos de Cocción.
- **Detalles del Problema:** Incluye el formato de la pieza (120x120 cm), el porcentaje de falla (8%) y las dos hipótesis (temperatura vs. humedad/enfriamiento).
- **Formato del Resultado:** Pídele que te entregue una lista de comprobación de 3 verificaciones rápidas que el operador puede hacer en 5 minutos en el panel del horno.

---

## Conceptos Clave para Recordar

- Prompts de Clasificación Rápida: Usar a Copilot para categorizar conceptos técnicos permite estructurar criterios de aceptación en minutos.
- Salida Limpia en Tablas: La sintaxis de tabla Markdown asegura la compatibilidad inmediata para copiar datos a Microsoft Excel sin perder formato.
- Asistencia en Tiempo Real: Copilot Chat funciona como un consultor técnico en planta para validar hipótesis operativas ante desviaciones de proceso.

---

## Resultado Esperado del Estudiante

Al finalizar el estudiante habrá generado en Copilot Chat:
1. El catálogo de defectos clasificados en recubrimientos porcelánicos.
2. Una matriz de criterios de aceptación lista para copiar en Microsoft Excel.
3. El borrador de la Guía Rápida de Inspección para Microsoft Word.
4. La resolución prompt estructurada para la contingencia de alabeo en el horno.
