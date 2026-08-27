# Práctica: Redacción formal de un hallazgo crítico acompañado del correo ejecutivo de notificación para la gerencia.

## Metadatos

| Elemento | Valor |
|---|---|
| Duración | 60 minutos |
| Complejidad | Media |
| Nivel de Bloom | Crear |

## Descripción general

En este laboratorio transformarás evidencia de auditoría interna simulada sobre registros incompletos de liberación de producto en un hallazgo crítico estructurado, verificable y orientado a riesgos. Utilizarás Microsoft 365 Copilot en Word para generar un borrador controlado y Outlook para elaborar una notificación ejecutiva dirigida a la gerencia de Calidad y Operaciones.

Todo contenido generado por Copilot deberá tratarse como borrador asistido. Antes de utilizarlo como comunicación formal, deberás validar manualmente cada afirmación contra el archivo de caso, evitando datos inventados, conclusiones no sustentadas, responsables no confirmados, fechas supuestas o referencias normativas no proporcionadas.

## Objetivos de aprendizaje

Al finalizar el laboratorio, podrás:

- [ ] Organizar hechos, criterio interno y evidencia documental de un caso de auditoría simulada.
- [ ] Redactar un hallazgo crítico con estructura trazable: criterio, condición, evidencia, riesgo, causa preliminar, recomendación, responsable y plazo.
- [ ] Utilizar Microsoft 365 Copilot en Word para generar un borrador con restricciones explícitas de no invención.
- [ ] Aplicar una revisión humana sistemática para distinguir hechos verificables, interpretaciones profesionales y acciones propuestas.
- [ ] Elaborar en Outlook un correo ejecutivo formal con solicitud de respuesta, responsables y fecha de seguimiento confirmada.

## Requisitos previos

### Conocimientos requeridos

- Redacción profesional en español.
- Conceptos básicos de auditoría: criterio, condición, evidencia objetiva, riesgo, causa preliminar, corrección y acción correctiva.
- Capacidad para distinguir entre:
  - Un **hecho verificable**.
  - Una **interpretación profesional**.
  - Una **acción propuesta**.
- Conocimiento básico de Word y Outlook de Microsoft 365.

### Accesos requeridos

- Cuenta corporativa Microsoft Entra ID con licencia activa de Microsoft 365 Copilot.
- Acceso a Microsoft Word y Outlook corporativos.
- Acceso a OneDrive for Business y a la biblioteca de SharePoint del curso.
- Buzón corporativo habilitado para enviar correos internos de prueba.
- Acceso al archivo fuente `Caso_Hallazgo_Critico_L06.docx`.
- Autorización del instructor para utilizar destinatarios internos de prueba o, si aplica, para dejar el mensaje como borrador sin enviarlo.

## Entorno de laboratorio

### Recursos de hardware

| Recurso | Requisito mínimo |
|---|---|
| Equipo | Intel Core i5 de 10.ª generación, AMD Ryzen 5 4000 Series o equivalente |
| Memoria | 8 GB de RAM |
| Pantalla | Resolución mínima de 1920 x 1080 |
| Espacio libre | 20 GB |
| Red corporativa | 10 Mbps de descarga y 5 Mbps de carga |
| Audio | Funcional si se usan reuniones o transcripciones de Teams |

### Recursos de software

| Componente | Uso en este laboratorio |
|---|---|
| Windows 11 Enterprise | Sistema operativo de trabajo |
| Microsoft Word para Microsoft 365 | Elaboración y validación del hallazgo |
| Microsoft Outlook para Microsoft 365 | Redacción del correo ejecutivo |
| Microsoft 365 Copilot | Generación de borradores asistidos |
| OneDrive for Business | Sincronización y conservación de archivos |
| SharePoint Online | Repositorio oficial de trabajo |

### Ubicación de trabajo

Utiliza exclusivamente la biblioteca sincronizada de SharePoint:

```text
/sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/
```

En equipos Windows, verifica que la carpeta local sincronizada esté disponible:

```text
C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
```

> **Importante:** No utilices unidades USB, almacenamiento personal, cuentas externas, herramientas de IA externas ni servicios no autorizados. No sobrescribas el archivo fuente suministrado por el instructor.

### Archivos de entrada y salida

| Tipo | Archivo |
|---|---|
| Fuente obligatoria | `Caso_Hallazgo_Critico_L06.docx` |
| Salida propuesta | `06_Hallazgo_Critico_Validado.docx` |
| Comunicación de salida | Correo enviado o borrador aprobado en Outlook, con enlace al documento validado |

> Si el instructor indica una convención de nombre distinta para el archivo de salida, utiliza la convención indicada. Conserva siempre el archivo fuente sin modificaciones.

---

## Procedimiento paso a paso

### Paso 1. Preparar el entorno y proteger la fuente de evidencia

**Objetivo:** Confirmar que el archivo de caso está disponible en la ubicación corporativa autorizada y crear una copia de trabajo sin alterar la fuente original.

**Instrucciones:**

1. Abre el Explorador de archivos de Windows.
2. Navega a la carpeta sincronizada:

   ```text
   C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
   ```

3. Confirma que el archivo `Caso_Hallazgo_Critico_L06.docx` esté disponible localmente y no presente iconos de error de sincronización.
4. Haz clic derecho sobre el archivo fuente y selecciona **Copiar**.
5. En la misma carpeta, selecciona **Pegar**.
6. Renombra la copia como:

   ```text
   06_Hallazgo_Critico_Validado.docx
   ```

7. Abre el archivo copiado en Microsoft Word.
8. Verifica que hayas iniciado sesión con la cuenta corporativa correcta en Word. Para ello, revisa la cuenta mostrada en la esquina superior derecha.
9. Confirma que el botón o panel de **Copilot** esté disponible en Word.

**Resultado esperado:**

- El archivo fuente permanece sin cambios.
- Existe una copia de trabajo denominada `06_Hallazgo_Critico_Validado.docx`.
- Word está conectado a la cuenta corporativa con acceso a Copilot.

**Verificación:**

- Comprueba que existen ambos archivos en la carpeta:
  - `Caso_Hallazgo_Critico_L06.docx`
  - `06_Hallazgo_Critico_Validado.docx`
- Verifica que OneDrive muestre estado de sincronización correcto.
- Confirma que el contenido del archivo fuente no haya sido editado.

---

### Paso 2. Extraer y clasificar la información del caso

**Objetivo:** Identificar los elementos sustentados por la evidencia antes de solicitar un borrador a Copilot.

**Instrucciones:**

1. Lee completamente el contenido de `06_Hallazgo_Critico_Validado.docx`.
2. Identifica en el caso los datos disponibles sobre:
   - Proceso auditado.
   - Registros de liberación de producto revisados.
   - Periodo, turno, línea, producto u órdenes involucradas, si están indicados.
   - Criterio interno aplicable.
   - Condición observada.
   - Evidencia documental o registros revisados.
   - Riesgo o consecuencia potencial descrita o razonablemente asociada.
   - Personas, áreas o roles mencionados.
   - Fecha de respuesta o seguimiento, si está definida.
3. Inserta al inicio del documento una sección temporal con el título:

   ```text
   Matriz de hechos para validación humana
   ```

4. Crea una tabla con las siguientes columnas:

   | Categoría | Información extraída | Fuente o evidencia en el caso | Estado de validación |
   |---|---|---|---|

5. Completa la tabla usando únicamente información existente en el archivo de caso.
6. Clasifica cada elemento con una de las siguientes categorías:
   - Hecho verificable.
   - Criterio interno.
   - Evidencia documental.
   - Riesgo o consecuencia potencial.
   - Causa preliminar.
   - Acción propuesta.
   - Información no confirmada.
7. Para toda información no confirmada, escribe explícitamente:

   ```text
   No confirmar ni incluir como hecho sin evidencia adicional.
   ```

8. No conviertas una sospecha en una conclusión. Por ejemplo:
   - Correcto: “No se confirmó en la evidencia disponible si hubo producto liberado sin registro completo.”
   - Incorrecto: “Se liberó producto no conforme”, si el caso no lo demuestra.

**Resultado esperado:**

- Una matriz de hechos que permita rastrear cada afirmación del hallazgo a una fuente del caso.
- Separación clara entre evidencia, interpretación y acciones propuestas.
- Identificación explícita de incertidumbres.

**Verificación:**

Revisa que puedas responder con evidencia a las cinco preguntas siguientes:

1. ¿Qué ocurrió o qué condición se observó?
2. ¿Qué criterio interno aplica?
3. ¿Qué evidencia respalda la condición?
4. ¿Qué riesgo potencial existe?
5. ¿Qué información continúa pendiente de confirmación?

Si alguna respuesta depende de una suposición, regístrala como información no confirmada.

---

### Paso 3. Generar un borrador estructurado del hallazgo con Copilot en Word

**Objetivo:** Utilizar Copilot para convertir la evidencia organizada en un borrador de hallazgo crítico con estructura obligatoria.

**Instrucciones:**

1. Después de la matriz de hechos, inserta un salto de página.
2. Agrega el encabezado:

   ```text
   Borrador de hallazgo crítico
   ```

3. Abre Copilot en Word.
4. Utiliza el siguiente prompt. Reemplaza los elementos entre corchetes solamente con información validada en tu matriz de hechos.

   ```text
   Actúa como asistente de redacción para una auditoría interna de calidad.

   Redacta un borrador formal de hallazgo crítico en español, dirigido a la gerencia de Calidad y Operaciones.

   Utiliza exclusivamente los hechos, criterios y evidencias incluidos en la sección “Matriz de hechos para validación humana” de este documento.

   Caso:
   - Proceso auditado: [proceso validado]
   - Criterio interno aplicable: [criterio exacto disponible]
   - Condición observada: [condición validada]
   - Evidencia documental: [registros, fechas, identificadores o referencias disponibles]
   - Riesgo o consecuencia potencial: [riesgo sustentado o formulado como potencial]
   - Causa preliminar: [solo si está indicada en la evidencia; de lo contrario, indicar “pendiente de determinar”]
   - Responsable propuesto: [rol o área confirmada; no inventar nombres]
   - Plazo de respuesta: [fecha confirmada; si no existe, indicar “por definir por la gerencia”]

   Usa obligatoriamente esta estructura:
   1. Título
   2. Proceso auditado
   3. Clasificación
   4. Criterio
   5. Condición observada
   6. Evidencia objetiva
   7. Riesgo o consecuencia
   8. Causa preliminar
   9. Recomendación
   10. Responsable propuesto
   11. Plazo de respuesta

   Restricciones:
   - No inventes fechas, nombres, cantidades, requisitos normativos, causas, impactos, responsables ni conclusiones.
   - Distingue los hechos de las acciones propuestas.
   - Si un dato no está confirmado, usa expresiones como “pendiente de confirmar”, “no determinado con la evidencia disponible” o “por definir”.
   - No afirmes liberación de producto sin evidencia de inspección si el caso no lo confirma.
   - Mantén tono formal, objetivo, verificable y orientado a riesgos.
   - No cites normas externas si no aparecen en la evidencia del caso.
   ```

5. Revisa el borrador generado antes de insertarlo.
6. Inserta el contenido solamente si mantiene la estructura solicitada.
7. Si Copilot omite una sección, solicita una corrección puntual. Por ejemplo:

   ```text
   Reestructura el borrador manteniendo únicamente la información sustentada y agrega las secciones “Evidencia objetiva”, “Causa preliminar” y “Plazo de respuesta”. No agregues datos nuevos.
   ```

**Resultado esperado:**

- Un borrador estructurado de hallazgo crítico.
- El texto incluye las once secciones obligatorias.
- Los elementos no confirmados aparecen como pendientes, no como hechos.

**Verificación:**

Comprueba que el borrador no incluya ninguno de los siguientes errores:

- Fechas que no aparecen en el caso.
- Nombres de personas no mencionadas en la evidencia.
- Citas de ISO, procedimientos o requisitos no incluidos en el caso.
- Conclusiones sobre producto liberado sin registros si la evidencia no lo confirma.
- Causas raíz presentadas como definitivas sin análisis validado.
- Compromisos de plazo no acordados.

---

### Paso 4. Realizar validación humana y emitir la versión final del hallazgo

**Objetivo:** Revisar cada afirmación del borrador para asegurar objetividad, trazabilidad y consistencia con la evidencia disponible.

**Instrucciones:**

1. Revisa el borrador sección por sección usando la matriz de hechos creada en el Paso 2.
2. Agrega al final del documento una tabla titulada:

   ```text
   Registro de validación humana del hallazgo
   ```

3. Crea la siguiente tabla:

   | Sección del hallazgo | Afirmación revisada | Evidencia o fuente | Resultado | Corrección aplicada |
   |---|---|---|---|---|

4. Para cada sección, registra uno de estos resultados:
   - Validado.
   - Corregido.
   - Eliminado por falta de evidencia.
   - Pendiente de confirmación.
5. Verifica específicamente:
   - Que el criterio esté transcrito o parafraseado sin cambiar su sentido.
   - Que la condición describa lo observado, no una opinión.
   - Que la evidencia incluya referencias concretas disponibles: registros, órdenes, fechas, formatos o documentos.
   - Que el riesgo esté formulado como riesgo potencial cuando no exista evidencia de impacto materializado.
   - Que la causa se identifique como preliminar o pendiente cuando no haya análisis de causa raíz.
   - Que el responsable propuesto corresponda a un rol o área confirmada.
   - Que el plazo de respuesta sea una fecha confirmada o se indique “por definir”.
6. Corrige manualmente el contenido del hallazgo con base en los resultados de la tabla.
7. Elimina la sección “Borrador de hallazgo crítico” si contiene texto duplicado y conserva una sola versión final.
8. Cambia el encabezado de la versión aprobada a:

   ```text
   Hallazgo crítico validado
   ```

9. Guarda el documento.
10. Espera a que OneDrive complete la sincronización.

**Resultado esperado:**

- Un hallazgo crítico final, revisado por una persona responsable.
- Un registro de validación que demuestre cómo se verificó cada afirmación relevante.
- Un documento apto para enlazar o adjuntar en una comunicación ejecutiva interna.

**Verificación:**

El hallazgo final debe responder claramente a las preguntas siguientes:

| Pregunta de control | Debe estar presente |
|---|---|
| ¿Qué se observó? | Condición verificable |
| ¿Contra qué criterio? | Criterio interno identificable |
| ¿Con qué evidencia? | Registros o referencias del caso |
| ¿Qué riesgo existe? | Riesgo o consecuencia formulada con prudencia |
| ¿Qué se solicita? | Recomendación o acción requerida |
| ¿Quién responde? | Rol, área o responsable confirmado |
| ¿Para cuándo? | Fecha confirmada o estado “por definir” |

---

### Paso 5. Crear el enlace corporativo al hallazgo validado

**Objetivo:** Preparar un enlace seguro al documento validado para incluirlo en la comunicación ejecutiva.

**Instrucciones:**

1. En el Explorador de archivos, localiza `06_Hallazgo_Critico_Validado.docx`.
2. Haz clic derecho y selecciona **Compartir**.
3. Configura el vínculo según la política corporativa y las instrucciones del instructor:
   - Preferentemente, selecciona acceso para **Personas de la organización con el vínculo**, si la política lo permite.
   - Si el contenido requiere mayor restricción, selecciona **Personas específicas** e incluye únicamente a los destinatarios autorizados.
4. Confirma que el permiso sea de solo lectura, salvo que se requiera revisión colaborativa formal.
5. Copia el vínculo.
6. Abre el enlace en una ventana privada del navegador o valida que el vínculo muestre el archivo correcto según los permisos disponibles.
7. Si no puedes crear un vínculo por políticas de seguridad, prepara el archivo como adjunto para el correo interno autorizado.

**Resultado esperado:**

- Un enlace corporativo funcional al documento validado o un archivo preparado para adjuntar.
- Permisos acordes con la confidencialidad y los destinatarios definidos.

**Verificación:**

- El enlace abre el archivo correcto.
- El archivo conserva el nombre `06_Hallazgo_Critico_Validado.docx`.
- El vínculo no apunta a almacenamiento personal o externo.
- Los permisos no conceden edición innecesaria.

---

### Paso 6. Redactar y validar el correo ejecutivo en Outlook

**Objetivo:** Elaborar una notificación formal para la gerencia que comunique el hallazgo, solicite una respuesta y defina seguimiento sin introducir información no sustentada.

**Instrucciones:**

1. Abre Microsoft Outlook con tu cuenta corporativa.
2. Selecciona **Nuevo correo**.
3. Completa los destinatarios según la lista proporcionada por el instructor:
   - **Para:** Gerencia de Calidad y Gerencia de Operaciones, o sus buzones internos de prueba.
   - **CC:** Solo las áreas o responsables autorizados.
4. Utiliza un asunto claro y trazable. Ejemplo:

   ```text
   Notificación de hallazgo crítico – Registros de liberación de producto – Solicitud de respuesta
   ```

5. En el cuerpo del mensaje, utiliza Copilot en Outlook o redacta directamente. Si utilizas Copilot, ingresa el siguiente prompt:

   ```text
   Redacta un correo ejecutivo formal en español dirigido a la Gerencia de Calidad y la Gerencia de Operaciones.

   Propósito: notificar un hallazgo crítico validado relacionado con registros incompletos de liberación de producto y solicitar un plan de acción correctiva.

   Usa exclusivamente la información validada en el documento “06_Hallazgo_Critico_Validado.docx”.

   El correo debe incluir:
   - Notificación breve y objetiva del hallazgo.
   - Proceso auditado.
   - Resumen de la condición observada.
   - Referencia al criterio y a la evidencia disponible, sin copiar información sensible innecesaria.
   - Riesgo o consecuencia expresado solo según el hallazgo validado.
   - Solicitud explícita de un plan de acción correctiva.
   - Responsable o área propuesta, únicamente si está confirmada.
   - Fecha de respuesta confirmada; si no existe, indicar que se solicita a la gerencia definirla.
   - Enlace o referencia al documento validado.
   - Cierre formal.

   Restricciones:
   - No inventes hechos, fechas, responsables, causas raíz, compromisos ni requisitos normativos.
   - No presentes información pendiente como conclusión.
   - Mantén tono ejecutivo, objetivo, respetuoso y orientado a la acción.
   ```

6. Revisa el texto generado antes de insertarlo o enviarlo.
7. Incluye el enlace corporativo al documento validado. Ejemplo de redacción:

   ```text
   El documento de hallazgo validado se encuentra disponible en el siguiente enlace corporativo: [pegar vínculo].
   ```

8. Si no existe una fecha de respuesta validada, no inventes una. Utiliza una solicitud como:

   ```text
   Se solicita confirmar el responsable y la fecha compromiso para la presentación del plan de acción correctiva.
   ```

9. Si existe una fecha confirmada en el caso o por el instructor, inclúyela exactamente como fue definida.
10. Revisa los destinatarios, asunto, adjuntos o enlace y contenido sensible.
11. Guarda el mensaje como borrador para revisión del instructor o envíalo únicamente si cuentas con autorización y utilizas destinatarios internos de prueba.

**Resultado esperado:**

- Un correo ejecutivo formal, conciso y trazable.
- Solicitud explícita de respuesta o plan de acción correctiva.
- Referencia al hallazgo validado mediante enlace corporativo o archivo adjunto.
- Ausencia de afirmaciones no sustentadas.

**Verificación:**

Antes de enviar, utiliza esta lista de control:

- [ ] El asunto identifica el tipo de comunicación y el tema.
- [ ] Los destinatarios son internos y están autorizados.
- [ ] El mensaje describe el hallazgo sin exagerar ni minimizar los hechos.
- [ ] La condición coincide con el documento validado.
- [ ] La evidencia no incluye información confidencial innecesaria.
- [ ] El riesgo está formulado como potencial si no existe impacto confirmado.
- [ ] Se solicita un plan de acción correctiva o una definición de responsable y plazo.
- [ ] La fecha indicada está confirmada o se solicita su definición.
- [ ] El enlace o adjunto corresponde al archivo validado.
- [ ] El correo fue guardado como borrador o enviado conforme a la autorización del instructor.

---

## Validación y pruebas

Realiza las siguientes pruebas finales antes de dar por terminado el laboratorio.

### Prueba 1. Trazabilidad de afirmaciones

Selecciona al menos cinco afirmaciones del hallazgo final y completa la siguiente tabla:

| Afirmación del hallazgo | Tipo de contenido | Evidencia en el caso | Resultado |
|---|---|---|---|
| Ejemplo: “Se identificaron registros incompletos de liberación.” | Hecho verificable | Referencia exacta al caso | Validado / Corregido / Eliminado |

**Criterio de aceptación:** Cada afirmación crítica debe contar con una fuente identificable en el caso o estar claramente etiquetada como recomendación, causa preliminar o pendiente de confirmación.

### Prueba 2. Separación entre hecho, interpretación y acción

Verifica que el documento diferencie los siguientes niveles:

| Nivel | Tratamiento esperado |
|---|---|
| Hecho verificable | Redacción objetiva y asociada a evidencia |
| Riesgo o interpretación profesional | Redacción prudente, sustentada y no concluyente cuando falte confirmación |
| Acción propuesta | Responsable, plazo y alcance sujetos a validación humana |

**Criterio de aceptación:** Ninguna acción propuesta debe presentarse como evidencia, y ninguna hipótesis debe presentarse como causa raíz confirmada.

### Prueba 3. Integridad del hallazgo

Confirma que el documento incluye estas secciones:

- [ ] Título.
- [ ] Proceso auditado.
- [ ] Clasificación.
- [ ] Criterio.
- [ ] Condición observada.
- [ ] Evidencia objetiva.
- [ ] Riesgo o consecuencia.
- [ ] Causa preliminar.
- [ ] Recomendación.
- [ ] Responsable propuesto.
- [ ] Plazo de respuesta.
- [ ] Registro de validación humana.

**Criterio de aceptación:** Las once secciones obligatorias están presentes. Cuando un dato no esté disponible, se expresa como “pendiente de determinar”, “por definir” o equivalente, sin inventar información.

### Prueba 4. Calidad del correo ejecutivo

Revisa el correo contra los criterios siguientes:

| Criterio | Resultado esperado |
|---|---|
| Claridad | Explica brevemente qué se notificó |
| Trazabilidad | Incluye asunto, destinatarios autorizados y vínculo o adjunto |
| Acción | Solicita plan de acción correctiva o definición de compromisos |
| Responsabilidad | Identifica responsables confirmados o solicita su asignación |
| Fecha | Incluye fecha validada o solicita establecerla |
| Confidencialidad | No divulga información fuera de los destinatarios autorizados |
| Validación humana | No contiene datos generados sin respaldo |

**Criterio de aceptación:** El mensaje puede ser comprendido por la gerencia sin necesidad de interpretar supuestos ni buscar información fuera del enlace al hallazgo.

---

## Solución de problemas

### Problema 1: Copilot agrega causas, fechas o conclusiones que no aparecen en el caso

**Síntomas:**

- El borrador menciona una causa raíz no investigada.
- Aparecen fechas compromiso no proporcionadas.
- Se afirma que hubo producto liberado sin evidencia suficiente.
- Se citan requisitos normativos o procedimientos no incluidos en el archivo de caso.

**Causa probable:**

El prompt no delimitó suficientemente las fuentes permitidas o el modelo completó vacíos con lenguaje plausible pero no validado.

**Solución:**

1. No aceptes el texto como evidencia.
2. Elimina o marca las afirmaciones no sustentadas.
3. Revisa la matriz de hechos y confirma qué información está disponible.
4. Solicita una nueva versión con una instrucción restrictiva:

   ```text
   Reescribe el texto utilizando exclusivamente la matriz de hechos de este documento. Elimina cualquier fecha, causa, requisito, responsable o conclusión que no esté explícitamente sustentado. Para datos faltantes, escribe “pendiente de confirmar” o “por definir”.
   ```

5. Actualiza el registro de validación humana indicando qué contenido fue eliminado o corregido.

### Problema 2: No es posible compartir el documento mediante vínculo corporativo o el destinatario no puede abrirlo

**Síntomas:**

- La opción de compartir está restringida.
- El vínculo solicita permisos al destinatario.
- El destinatario recibe un mensaje de acceso denegado.
- El enlace apunta a una ubicación diferente de SharePoint o OneDrive.

**Causa probable:**

La política de SharePoint o OneDrive limita el uso compartido, el destinatario no está incluido en los permisos o el archivo aún no terminó de sincronizarse.

**Solución:**

1. Confirma que el archivo esté almacenado en la carpeta corporativa sincronizada y no en una ubicación personal.
2. Espera a que OneDrive muestre sincronización completada.
3. Crea un nuevo vínculo seleccionando **Personas específicas** e incluye a los destinatarios autorizados.
4. Solicita apoyo al instructor o al administrador de la biblioteca si las políticas impiden compartir.
5. Como alternativa autorizada, adjunta el archivo al correo interno de prueba, verificando que el adjunto sea `06_Hallazgo_Critico_Validado.docx`.

---

## Limpieza

1. Guarda y sincroniza el documento final `06_Hallazgo_Critico_Validado.docx` en la carpeta oficial del curso.
2. Confirma que el archivo fuente `Caso_Hallazgo_Critico_L06.docx` permanece intacto.
3. Si el correo fue creado solo para práctica y no existe autorización para enviarlo, consérvalo como borrador con un prefijo en el asunto:

   ```text
   BORRADOR DE PRÁCTICA –
   ```

4. Si el correo fue enviado a destinatarios internos de prueba, verifica que aparezca en **Elementos enviados**.
5. Cierra Word y Outlook si no se requieren para actividades posteriores.
6. No elimines el documento validado, la matriz de hechos ni el registro de validación humana, ya que serán artefactos de continuidad para el Laboratorio 07-00-01.

## Resumen

En este laboratorio elaboraste un hallazgo crítico a partir de evidencia de auditoría simulada y aplicaste una revisión humana para asegurar que la comunicación fuera objetiva, trazable y verificable. Copilot se utilizó como apoyo para estructurar un borrador, no como autoridad para determinar causas, clasificaciones, responsables, fechas o conclusiones.

El documento `06_Hallazgo_Critico_Validado.docx` y el correo ejecutivo aprobado constituyen la base para el siguiente laboratorio, donde el hallazgo se utilizará para diseñar controles y preguntas de verificación de auditoría.

### Recursos opcionales

- [Microsoft Support: Copilot en Microsoft 365](https://support.microsoft.com/es-es/copilot)
- [Microsoft Learn: Microsoft 365 Copilot](https://learn.microsoft.com/es-es/copilot/microsoft-365/)
- [ISO: Principios de gestión de la calidad](https://www.iso.org/quality-management-principles.html)
