# Práctica: Creación integral de una lista de verificación (checklist) para una auditoría interna de calidad.

### Duración Estimada
60 minutos

---

### Descripción de la Actividad
En este laboratorio práctico, asumirás el rol de Lead Auditor y Diseñador de Soluciones de Calidad en Cerámicas del Norte. Frente a la necesidad de estandarizar las auditorías internas bajo la norma ISO 9001, utilizarás Microsoft 365 Copilot para diseñar las instrucciones del sistema (prompt de sistema) de un Agente Personalizado de Auditoría. Posteriormente, configurarás el agente en Copilot Studio o GPTs/Copilot Builder, probarás su desempeño mediante prompts de evaluación técnica y adaptarás su comportamiento en un reto de modificación en vivo.

---

## Objetivos del Laboratorio
- Diseñar la arquitectura de instrucciones (System Prompt / Custom Instructions) para un Agente de IA especializado en auditorías de calidad ISO 9001.
- Configurar y desplegar un Agente Personalizado de Copilot copiando y pegando parámetros de comportamiento definidos.
- Validar la precisión del agente mediante la ejecución de prompts de prueba para la generación de checklists y detección de evidencias.
- Modificar las reglas operativas del agente en tiempo real para adaptar su comportamiento a escenarios de auditoría combinada (Calidad y Seguridad).

---

## Prerrequisitos
- Acceso a Microsoft 365 Copilot Chat (Enterprise / Web)

---

### Fase 1: Ingeniería del Prompt de Sistema para el Agente Auditor

**Herramienta objetivo:** Copilot Chat (Diseño de Instrucciones de Agente)

Diseña el prompt de sistema completo que definirá el rol, reglas, restricciones y formato de respuesta del Agente de Auditoría de Calidad.

```
Actúa como Arquitecto de Soluciones de IA para Sistemas de Gestión de Calidad.

Redacta el Prompt de Sistema (System Instructions) completo e independiente para crear un Agente Personalizado llamado "Auditor-ISO9001-Bot".

El prompt de sistema redactado debe contener las siguientes secciones claramente delimitadas dentro de un bloque de código:
1. Rol y Propósito: Auditor Líder ISO 9001 experto en la industria cerámica.
2. Reglas de Comportamiento: Debe exigir evidencias objetivas, citar cláusulas específicas de la norma (ej. 8.5.1, 9.2, 10.2) y mantener un tono formal e imparcial.
3. Formato de Salida Obligatorio: Siempre que se le pida una lista de verificación, debe entregar una tabla Markdown con las columnas: | Cláusula ISO | Punto de Chequeo | Evidencia Requerida | Criterio de Aceptación | Método de Verificación |.
4. Restricción de Alcance: Si se le consulta sobre temas ajenos a auditorías de calidad o manufactura cerámica, debe responder que su alcance está limitado a sistemas ISO.

```

---

### Fase 2: Configuración y Despliegue del Agente Personalizado

**Herramienta objetivo:** Copilot Studio / Configuración de Agentes Personalizados

Aprende a trasladar la instrucción generada en la Fase 1 para dar vida al agente dentro de la plataforma de Microsoft.

#### Guía Paso a Paso para Crear el Agente:

1. **Copiar las Instrucciones:** Copia todo el texto generado dentro del bloque de código en la Fase 1 (*Prompt de Sistema para Auditor-ISO9001-Bot*).
2. **Acceder a la Creación de Agentes:** Abre la interfaz de creación de agentes en tu entorno de Microsoft Copilot (Copilot Studio o el menú *Crear Agente / Custom GPTs*).
3. **Asignar Nombre y Descripción:**
   - **Nombre:** `Auditor-ISO9001-Bot`
   - **Descripción:** *Agente especializado en la generación de listas de verificación y análisis de hallazgos para auditorías ISO 9001 en Cerámicas del Norte.*
4. **Pegar las Instrucciones de Sistema:** Localiza el campo **Instrucciones (Instructions / System Prompt)** y pega exactamente el texto copiado de la Fase 1.
5. **Guardar y Publicar:** Haz clic en **Guardar** o **Publicar**. El agente está listo para recibir interactividades en el panel de pruebas.

---

### Fase 3: Prueba de Generación de Checklist con el Agente (Evaluación 1)

**Herramienta objetivo:** Agente "Auditor-ISO9001-Bot" recién configurado

Pon a prueba al agente para validar que cumpla la regla de salida en tabla Markdown e identifique requisitos clave del proceso de prensado.

```
Genera la lista de verificación (checklist) para auditar el proceso de prensado de baldosas cerámicas de gran formato bajo la cláusula 8.5.1 de la ISO 9001. Necesito al menos 4 puntos de chequeo críticos sobre control de presión y humedad.

```

---

### Fase 4: Prueba de Análisis de Caso y Evaluación de Evidencias (Evaluación 2)

**Herramienta objetivo:** Agente "Auditor-ISO9001-Bot" recién configurado

Evalúa la capacidad de análisis técnico del agente frente a la presentación de una evidencia de auditoría ambigua en la línea de cocción.

```
Durante la auditoría en la zona de hornos, el operador indica que ajusta la temperatura de cocción "de oído y por experiencia" cuando nota variación en el tono de la arcilla, porque el sensor térmico lleva 2 meses descalibrado. ¿Cómo evalúas esta evidencia y qué punto de tu checklist se incumple?

```

---

### Reto Práctico: Modificación e Integración Normativa del Agente (ISO 9001 + ISO 45001)

**Herramienta objetivo:** Configuración del Agente + Panel de Pruebas

**Escenario de Desafío:**
La Dirección de Planta exige que todas las auditorías internas sean integradas, evaluando simultáneamente la Calidad (ISO 9001) y la Seguridad e Higiene Industrial (ISO 45001 en prensas y hornos).

**Tu Desafío:**
1. **Modificar el Agente:** Regresa a la pestaña de configuración de tu agente `Auditor-ISO9001-Bot` y añade una nueva regla al Prompt de Sistema:
   > *"Debes integrar el análisis de Seguridad Industrial (ISO 45001). En las tablas Markdown, añade la columna '| Riesgo SST Asociado |' y exige verificar la presencia de EPP y paradas de emergencia."*
2. **Probar la Modificación:** Ejecuta el siguiente prompt de prueba en tu agente modificado para verificar el nuevo comportamiento:

Prompt del Reto:
Genera la lista de verificación integrada (Calidad + SST) para auditar la zona de preparación de esmaltes y molienda.

---

## Conceptos Clave para Recordar

- Arquitectura de Agentes Especializados: Definir claramente el rol, las restricciones y los formatos obligatorios en el Prompt de Sistema garantiza que la IA no se desvíe del estándar operativo.
- Reusabilidad en Entornos Corporativos: Un agente configurado con las reglas de la empresa puede ser utilizado repetidamente por todo el equipo de auditores con resultados consistentes.
- Adaptabilidad Sistémica: Modificar las instrucciones base del agente permite evolucionar de auditorías simples a sistemas integrados de gestión (Calidad, Ambiente y Seguridad) sin volver a empezar desde cero.

---

## Resultado Esperado del Estudiante

Al finalizar los 60 minutos del laboratorio, el estudiante habrá logrado:
1. Diseñar el Prompt de Sistema para el agente "Auditor-ISO9001-Bot".
2. Crear y desplegar el agente configurado en la plataforma de Copilot.
3. Obtener la lista de verificación formateada en tabla Markdown mediante el primer prompt de prueba.
4. Validar la capacidad de diagnóstico de no conformidades del agente en la segunda prueba.
5. Modificar con éxito la instrucción de sistema del agente para auditorías integradas ISO 9001 + ISO 45001 y probar su funcionamiento final.
