# Práctica: Desarrollo de una matriz de control de riesgos y guía de uso responsable para el uso corporativo de Copilot.

## Metadatos

| Elemento | Valor |
|---|---|
| Duración | 30 minutos |
| Complejidad | Media |
| Nivel de Bloom | Crear |

## Descripción general

En este laboratorio se desarrollarán dos artefactos de control para el uso corporativo de Microsoft 365 Copilot en auditorías internas de calidad: una matriz de riesgos y controles en Excel, y una guía operativa de validación humana en Word. Los artefactos utilizarán como referencia el hallazgo formal elaborado en el Laboratorio 06 y la checklist de auditoría desarrollada en el Laboratorio 07.

El propósito es asegurar que Copilot se utilice como asistente para organizar, resumir y redactar borradores, sin sustituir la evidencia objetiva, el criterio técnico, la aprobación formal ni las políticas corporativas de seguridad de la información.

## Objetivos de aprendizaje

Al finalizar el laboratorio, podrá:

- [ ] Identificar riesgos de calidad, privacidad, seguridad de la información, cumplimiento y trazabilidad asociados al uso de Copilot en auditorías internas.
- [ ] Construir una matriz de riesgos con evaluación inherente y residual, controles preventivos, detectivos y correctivos, responsables y evidencia verificable.
- [ ] Aplicar un esquema de validación humana para distinguir entre evidencia objetiva, hipótesis generadas y conclusiones aprobadas.
- [ ] Elaborar una guía de uso responsable de Copilot aplicable a hallazgos de auditoría y checklists de calidad.
- [ ] Identificar los puntos que requieren revisión o aprobación de Seguridad de la Información, Legal o Cumplimiento antes de su aplicación formal.

## Requisitos previos

### Conocimientos requeridos

- Finalización de los Laboratorios 06-00-01 y 07-00-01.
- Conocimiento básico de no conformidades, auditoría interna, controles internos y evaluación de riesgos.
- Comprensión de los conceptos de evidencia objetiva, hallazgo, acción correctiva, trazabilidad documental y aprobación controlada.
- Comprensión de que una salida de Copilot es un borrador o apoyo preliminar y no una fuente autónoma de verdad.
- Conocimiento básico de clasificación de información y protección de datos sensibles.

### Accesos y archivos requeridos

Verifique que cuenta con lo siguiente antes de iniciar:

- Cuenta corporativa de Microsoft Entra ID con licencia activa de Microsoft 365 Copilot.
- Acceso a Microsoft Excel y Microsoft Word con Copilot habilitado.
- Permisos de lectura y escritura en la biblioteca corporativa de SharePoint sincronizada con OneDrive.
- Archivo `L06_Hallazgo_Critico_v1.docx` disponible en la carpeta de trabajo.
- Archivo `L07_Checklist_Auditoria_Calidad_v1.xlsx` disponible en la carpeta de trabajo.
- Acceso al tenant corporativo autorizado; no utilice cuentas personales, almacenamiento personal, memorias USB ni servicios externos de IA.

## Entorno de laboratorio

### Hardware y conectividad

| Componente | Requisito mínimo |
|---|---|
| Equipo | Intel Core i5 de 10.ª generación, AMD Ryzen 5 4000 Series o equivalente |
| Memoria | 8 GB de RAM |
| Espacio disponible | 20 GB libres |
| Pantalla | Resolución mínima de 1920 × 1080 |
| Red corporativa | Al menos 10 Mbps de descarga y 5 Mbps de carga |
| Cuenta | Microsoft Entra ID corporativa con Microsoft 365 Copilot asignado |

### Software

| Software | Uso en el laboratorio |
|---|---|
| Microsoft Excel para Microsoft 365 | Elaboración de la matriz de riesgos y controles |
| Microsoft Word para Microsoft 365 | Elaboración de la guía de uso responsable |
| Microsoft 365 Copilot | Apoyo para estructurar riesgos, controles y texto de la guía |
| OneDrive for Business | Sincronización local con la biblioteca corporativa |
| SharePoint Online | Repositorio oficial de almacenamiento y control documental |

### Ubicación de trabajo

Utilice exclusivamente la ruta corporativa sincronizada:

```text
C:\Users\%USERNAME%\OneDrive - Organizacion\CopilotCalidad\Batch_01_Calidad_Mejora_Continua\
```

La biblioteca de SharePoint asociada es:

```text
/sites/CopilotCalidad/Documentos compartidos/Batch_01_Calidad_Mejora_Continua/
```

> **Control obligatorio:** no sobrescriba los archivos fuente del instructor ni los entregables de los Laboratorios 06 y 07. Cree archivos nuevos para este laboratorio.

### Archivos de salida

Cree y guarde los siguientes archivos en la carpeta de trabajo corporativa:

```text
08_Matriz_Control_Riesgos_Copilot.xlsx
08_Guia_Uso_Responsable_Copilot.docx
```

## Procedimiento paso a paso

### Paso 1. Revisar los artefactos de auditoría y delimitar el uso de Copilot

**Objetivo:** Identificar los puntos del hallazgo y de la checklist donde el uso de Copilot puede introducir riesgos de calidad, confidencialidad, trazabilidad o cumplimiento.

**Instrucciones:**

1. Abra el archivo `L06_Hallazgo_Critico_v1.docx` en Microsoft Word.
2. Revise el hallazgo formal y localice, como mínimo, los siguientes elementos:
   - Proceso auditado.
   - Criterio o requisito incumplido.
   - Evidencia objetiva registrada.
   - Riesgo o impacto del hallazgo.
   - Responsable o área involucrada.
   - Acciones requeridas o sugeridas.
3. Identifique si el hallazgo contiene información sensible, por ejemplo:
   - Nombres de empleados.
   - Identificadores de cliente, lote o proveedor.
   - Datos de desempeño individual.
   - Información contractual.
   - Información técnica confidencial.
   - Datos personales, disciplinarios o de salud.
4. Abra `L07_Checklist_Auditoria_Calidad_v1.xlsx`.
5. Revise la checklist e identifique los puntos donde Copilot podría utilizarse, por ejemplo:
   - Preparación de preguntas de auditoría.
   - Resumen de evidencias recolectadas.
   - Priorización preliminar de hallazgos.
   - Redacción de observaciones.
   - Generación de borradores de comunicaciones internas.
   - Organización de acciones de seguimiento.
6. Cree una nota breve en un documento temporal o en una hoja de Excel con dos columnas: `Uso previsto de Copilot` y `Riesgo potencial`.
7. Incluya al menos cinco usos previstos y sus riesgos asociados.
8. No copie datos personales ni información sensible en prompts durante esta revisión. Utilice descripciones anonimizadas, por ejemplo:
   - `Operador A`
   - `Cliente X`
   - `Lote L-2026-001`
   - `Área de ensamble`
   - `Supervisor de turno`

**Salida esperada:**

Una lista preliminar de usos de Copilot relacionados con el hallazgo de Lab 06 y la checklist de Lab 07, con riesgos potenciales asociados.

Ejemplo:

| Uso previsto de Copilot | Riesgo potencial |
|---|---|
| Resumir el hallazgo crítico | Omisión de evidencia o cambio no intencional del significado del hallazgo |
| Generar preguntas de auditoría | Inclusión de requisitos inexistentes o desactualizados |
| Priorizar hallazgos | Sesgo o simplificación excesiva del riesgo operacional |
| Redactar una comunicación | Envío a destinatarios no autorizados o divulgación de información sensible |
| Proponer acciones correctivas | Presentar hipótesis como causas raíz confirmadas |

**Verificación:**

- Confirme que ha revisado ambos archivos fuente sin modificarlos.
- Confirme que puede señalar cuáles datos del hallazgo o checklist requieren anonimización.
- Confirme que ha identificado explícitamente el riesgo de tratar una respuesta generada como evidencia objetiva.

---

### Paso 2. Crear la matriz de control de riesgos en Excel

**Objetivo:** Construir una matriz de riesgos trazable que cubra los riesgos mínimos definidos para el uso de Copilot en auditorías de calidad.

**Instrucciones:**

1. Abra Microsoft Excel y cree un libro nuevo.
2. Guárdelo inmediatamente con el nombre:

   ```text
   08_Matriz_Control_Riesgos_Copilot.xlsx
   ```

3. Cree una hoja denominada:

   ```text
   Matriz_Riesgos_Copilot
   ```

4. En la fila 1, cree las siguientes columnas, en este orden:

   | Columna | Encabezado |
   |---|---|
   | A | ID_Riesgo |
   | B | Artefacto_Relacionado |
   | C | Proceso_Afectado |
   | D | Evento_de_Riesgo |
   | E | Causa |
   | F | Consecuencia |
   | G | Probabilidad |
   | H | Impacto |
   | I | Nivel_Inherente |
   | J | Controles_Preventivos |
   | K | Controles_Detectivos |
   | L | Controles_Correctivos |
   | M | Responsable |
   | N | Evidencia_del_Control |
   | O | Nivel_Residual |
   | P | Criterio_de_Escalamiento |
   | Q | Estado_de_Validacion |
   | R | Observaciones |

5. Seleccione el rango de encabezados y conviértalo en tabla mediante **Insertar > Tabla**.
6. Asigne a la tabla el nombre:

   ```text
   tblRiesgosCopilot
   ```

7. Defina una escala consistente para `Probabilidad` e `Impacto`:

   | Valor | Probabilidad | Impacto |
   |---|---|---|
   | 1 | Rara | Menor |
   | 2 | Poco probable | Moderado |
   | 3 | Posible | Significativo |
   | 4 | Probable | Mayor |
   | 5 | Casi segura | Crítico |

8. En la columna `Nivel_Inherente`, utilice la siguiente fórmula para calcular el valor numérico:

   ```excel
   =[@Probabilidad]*[@Impacto]
   ```

9. Aplique formato condicional a `Nivel_Inherente`:
   - De 1 a 4: verde, riesgo bajo.
   - De 5 a 9: amarillo, riesgo medio.
   - De 10 a 16: naranja, riesgo alto.
   - De 17 a 25: rojo, riesgo crítico.

10. Cree una hoja adicional denominada:

   ```text
   Escala_y_Criterios
   ```

11. Documente en esa hoja los criterios de clasificación, las definiciones de bajo, medio, alto y crítico, y los criterios de escalamiento definidos por su organización o, si no están disponibles, por el escenario de este laboratorio.

12. Registre como mínimo los siete riesgos obligatorios de la siguiente tabla. Puede agregar riesgos adicionales si son pertinentes al contexto de auditoría.

| ID_Riesgo | Evento de riesgo mínimo |
|---|---|
| R-01 | Generación de información no sustentada o alucinación |
| R-02 | Uso de datos sensibles o personales en prompts |
| R-03 | Acceso inadecuado a archivos o información no autorizada |
| R-04 | Sesgo en la priorización o interpretación de hallazgos |
| R-05 | Pérdida de trazabilidad de evidencia y decisiones |
| R-06 | Envío erróneo de comunicaciones o divulgación no autorizada |
| R-07 | Aceptación automática de contenido generado por Copilot |

13. Relacione cada riesgo con `L06_Hallazgo_Critico_v1.docx`, `L07_Checklist_Auditoria_Calidad_v1.xlsx` o ambos.

14. Complete los campos de la matriz usando información real del escenario, pero sin incluir datos personales ni contenido confidencial no necesario.

15. Incluya como mínimo los controles siguientes, adaptados al riesgo correspondiente:
   - Revisión por responsable técnico competente.
   - Contraste con evidencia objetiva y registros controlados.
   - Anonimización o minimización de datos.
   - Uso exclusivo del tenant corporativo autorizado.
   - Verificación de permisos de acceso antes de utilizar archivos.
   - Registro de fuentes, versión y revisor.
   - Aprobación antes de enviar comunicaciones oficiales.
   - Escalamiento a Seguridad de la Información, Legal o Cumplimiento cuando corresponda.

16. En `Estado_de_Validacion`, utilice valores controlados como:
   - `Pendiente`
   - `Validado por Calidad`
   - `Requiere Seguridad de la Información`
   - `Requiere Legal`
   - `Requiere Cumplimiento`
   - `Aprobado para uso interno`

17. Use Copilot en Excel para obtener una propuesta de controles. Seleccione una celda de la tabla y utilice un prompt equivalente al siguiente:

   ```text
   Actúa como asistente de gestión de riesgos para auditorías internas de calidad.
   Analiza la matriz tblRiesgosCopilot y propone controles preventivos, detectivos y correctivos
   para los riesgos registrados. No inventes políticas corporativas, normas, requisitos legales
   ni evidencias. Distingue claramente entre propuesta y requisito confirmado. Da prioridad a:
   validación humana, evidencia objetiva, anonimización, control de acceso, trazabilidad y aprobación.
   ```

18. Revise las sugerencias de Copilot y acepte únicamente las que:
   - Sean coherentes con los procesos reales.
   - No contradigan políticas internas conocidas.
   - Puedan ser demostradas mediante evidencia.
   - Tengan un responsable definido.
   - No sustituyan una aprobación humana.

**Salida esperada:**

Un archivo de Excel con una tabla denominada `tblRiesgosCopilot`, que contenga al menos siete riesgos y todos los campos de evaluación y control requeridos.

Ejemplo de registro resumido:

| Campo | Ejemplo para R-01 |
|---|---|
| ID_Riesgo | R-01 |
| Artefacto_Relacionado | Hallazgo Lab 06 y Checklist Lab 07 |
| Proceso_Afectado | Preparación de hallazgos de auditoría |
| Evento_de_Riesgo | Copilot genera una conclusión no sustentada por evidencia |
| Causa | Prompt ambiguo, contexto incompleto o aceptación automática |
| Consecuencia | Hallazgo incorrecto, decisión deficiente o incumplimiento |
| Probabilidad | 3 |
| Impacto | 4 |
| Nivel_Inherente | 12 |
| Controles_Preventivos | Prompt con alcance limitado; prohibición de afirmar causas definitivas sin evidencia |
| Controles_Detectivos | Revisión técnica contra registros controlados y checklist |
| Controles_Correctivos | Corregir documento, registrar desviación y revalidar antes de emitir |
| Responsable | Auditor líder o responsable de calidad |
| Evidencia_del_Control | Registro de revisión, comentarios, versión aprobada y fuentes consultadas |
| Nivel_Residual | 4 |
| Criterio_de_Escalamiento | Escalar si afecta cumplimiento, seguridad, cliente o liberación de producto |
| Estado_de_Validacion | Pendiente |

**Verificación:**

- La tabla se denomina exactamente `tblRiesgosCopilot`.
- Existen al menos siete riesgos obligatorios.
- Cada riesgo tiene probabilidad, impacto, nivel inherente, controles, responsable, evidencia, nivel residual y criterio de escalamiento.
- Los riesgos R-01 a R-07 se relacionan con los artefactos de los Laboratorios 06 y 07.
- No se han registrado datos personales reales, secretos industriales ni información sensible innecesaria.

---

### Paso 3. Evaluar el riesgo inherente, residual y el escalamiento

**Objetivo:** Determinar qué riesgos requieren controles reforzados, aprobación adicional o escalamiento a funciones especializadas.

**Instrucciones:**

1. Revise los valores de `Nivel_Inherente` de cada riesgo.
2. Clasifique el riesgo inherente según la escala documentada:

   | Puntaje | Clasificación |
   |---|---|
   | 1 a 4 | Bajo |
   | 5 a 9 | Medio |
   | 10 a 16 | Alto |
   | 17 a 25 | Crítico |

3. Para cada riesgo, evalúe si los controles definidos reducen de manera razonable la probabilidad, el impacto o ambos.
4. Registre el `Nivel_Residual` utilizando el puntaje resultante después de considerar los controles. Puede utilizar una evaluación cualitativa o numérica, siempre que sea consistente y esté explicada en la hoja `Escala_y_Criterios`.
5. Establezca los criterios mínimos de escalamiento:
   - Escalar a **Seguridad de la Información** cuando exista posible acceso no autorizado, exposición de información confidencial, clasificación inadecuada de datos o dudas sobre permisos.
   - Escalar a **Legal** cuando el contenido incluya contratos, obligaciones con clientes, comunicaciones externas, responsabilidades individuales, propiedad intelectual o interpretación legal.
   - Escalar a **Cumplimiento** cuando exista posible incumplimiento normativo, requisito regulatorio, política corporativa o sistema de gestión certificado.
   - Escalar al **responsable de Calidad** cuando una salida de Copilot pueda afectar un hallazgo, una CAPA, la liberación de producto, una decisión de auditoría o una conclusión técnica.
6. Agregue una nota en la hoja `Escala_y_Criterios` con el siguiente principio:

   > Copilot puede proponer estructura, preguntas, resúmenes o hipótesis preliminares. Las conclusiones de auditoría, la determinación de causa raíz, la aprobación de acciones y la emisión de comunicaciones oficiales requieren validación y aprobación humana autorizada.

7. Utilice Copilot para revisar consistencia de la matriz con un prompt como el siguiente:

   ```text
   Revisa la consistencia de la tabla tblRiesgosCopilot.
   Identifica riesgos con nivel inherente alto o crítico que no tengan controles detectivos,
   responsable, evidencia de control o criterio de escalamiento.
   No modifiques la tabla automáticamente. Devuelve una lista de observaciones para revisión humana.
   ```

8. Revise manualmente las observaciones. Corrija únicamente las deficiencias verificadas.

**Salida esperada:**

Una matriz con niveles inherentes y residuales consistentes, controles suficientes y criterios claros de escalamiento para riesgos altos o críticos.

**Verificación:**

- Todos los riesgos altos o críticos incluyen al menos un control preventivo, uno detectivo y un responsable.
- Los riesgos relacionados con datos sensibles, accesos o comunicaciones incluyen escalamiento a Seguridad de la Información, Legal o Cumplimiento cuando corresponde.
- Los niveles residuales no se reducen sin una justificación basada en controles verificables.
- Las recomendaciones de Copilot han sido revisadas por una persona y no se han aceptado de forma automática.

---

### Paso 4. Elaborar la guía de uso corporativo responsable en Word

**Objetivo:** Crear una guía breve y operativa que indique cómo utilizar Copilot de manera segura y verificable durante auditorías internas de calidad.

**Instrucciones:**

1. Abra Microsoft Word y cree un documento nuevo.
2. Guarde el archivo con el nombre:

   ```text
   08_Guia_Uso_Responsable_Copilot.docx
   ```

3. Agregue el siguiente título:

   ```text
   Guía operativa para el uso responsable de Microsoft 365 Copilot en auditorías de calidad
   ```

4. Incluya una sección de propósito con una redacción equivalente a la siguiente:

   > Esta guía establece controles mínimos para utilizar Microsoft 365 Copilot como apoyo en la preparación, análisis preliminar, redacción y seguimiento de auditorías internas de calidad. Copilot no sustituye la evidencia objetiva, el juicio profesional, la investigación técnica ni la aprobación de las personas autorizadas.

5. Cree las siguientes secciones obligatorias:
   - Alcance.
   - Principios de uso responsable.
   - Información permitida.
   - Información que debe anonimizarse o evitarse.
   - Validación humana de resultados.
   - Gestión de evidencia y trazabilidad.
   - Escalamiento de dudas o incidentes.
   - Relación con los entregables de los Laboratorios 06 y 07.
   - Puntos pendientes de validación corporativa.

6. En la sección **Información permitida**, incluya ejemplos de información que puede utilizarse siempre que esté autorizada:
   - Datos de calidad agregados o anonimizados.
   - Identificadores internos no sensibles.
   - Requisitos de procedimientos internos vigentes a los que el usuario tenga acceso autorizado.
   - Plantillas aprobadas.
   - Evidencia objetiva previamente clasificada y permitida para el propósito.
   - Tendencias de indicadores sin datos personales o confidenciales innecesarios.

7. En la sección **Información que debe anonimizarse o evitarse**, indique que se debe minimizar, anonimizar o no incluir:
   - Nombres, correos, teléfonos, identificadores personales o evaluaciones individuales.
   - Información médica, disciplinaria, salarial o laboral sensible.
   - Información contractual o de clientes no autorizada.
   - Diseños, fórmulas, secretos industriales o información de propiedad intelectual.
   - Credenciales, contraseñas, claves, tokens o configuraciones de seguridad.
   - Información clasificada que no esté autorizada para el uso previsto.
   - Datos copiados desde fuentes que el usuario no tiene permiso de consultar o compartir.

8. En la sección **Validación humana de resultados**, incorpore una lista de verificación operativa:

   - Confirmar que el prompt no incluyó datos sensibles innecesarios.
   - Contrastar cifras, fechas, lotes, hechos y referencias contra registros controlados.
   - Distinguir hechos comprobados, hipótesis de Copilot y conclusiones aprobadas.
   - Verificar que no se hayan inventado requisitos, cláusulas, fuentes o evidencias.
   - Confirmar que las acciones propuestas abordan causas verificadas y no supuestos.
   - Revisar el impacto sobre cliente, producto, seguridad, cumplimiento y operación.
   - Obtener aprobación del rol autorizado antes de emitir o usar el documento como registro controlado.
   - Conservar evidencia de fuentes, revisión, cambios y aprobación.

9. En la sección **Gestión de evidencia y trazabilidad**, establezca que:
   - Las fuentes utilizadas deben poder identificarse.
   - El documento final debe indicar versión, fecha, autor, revisor y aprobador cuando aplique.
   - Las observaciones generadas por Copilot deben revisarse antes de incorporarse al documento.
   - La evidencia objetiva no debe confundirse con texto generado.
   - Los archivos se deben guardar en SharePoint Online o OneDrive for Business corporativo.
   - No se deben utilizar repositorios personales ni servicios externos no autorizados.

10. En la sección **Relación con los entregables de los Laboratorios 06 y 07**, incluya una tabla como la siguiente:

| Artefacto | Uso permitido de Copilot | Control obligatorio |
|---|---|---|
| `L06_Hallazgo_Critico_v1.docx` | Proponer estructura, mejorar claridad o resumir evidencia autorizada | Validar cada afirmación contra evidencia objetiva; no alterar el criterio, hecho o conclusión aprobada |
| `L07_Checklist_Auditoria_Calidad_v1.xlsx` | Proponer preguntas complementarias o agrupar criterios | Verificar que los requisitos existan, estén vigentes y sean aplicables |
| Matriz de riesgos Lab 08 | Sugerir controles o identificar campos incompletos | Revisar coherencia con políticas corporativas y responsables reales |
| Guía de uso responsable Lab 08 | Proponer redacción y estructura | Validar con Seguridad de la Información, Legal o Cumplimiento según corresponda |

11. En la sección **Puntos pendientes de validación corporativa**, agregue una tabla con los siguientes elementos:

| Tema | Área que debe validar | Estado inicial |
|---|---|---|
| Clasificación de información permitida en prompts | Seguridad de la Información | Pendiente |
| Retención de prompts, respuestas y evidencia de revisión | Cumplimiento / Gestión Documental | Pendiente |
| Uso de Copilot en comunicaciones externas a clientes | Legal / Calidad | Pendiente |
| Tratamiento de datos personales de empleados | Legal / Privacidad | Pendiente |
| Aprobación de contenido generado en documentos controlados | Calidad / Cumplimiento | Pendiente |

12. Use Copilot en Word para obtener una revisión de estructura, sin solicitar que invente políticas. Utilice un prompt como el siguiente:

   ```text
   Revisa este borrador de guía para uso responsable de Microsoft 365 Copilot
   en auditorías internas de calidad. Identifica vacíos respecto a validación humana,
   confidencialidad, trazabilidad, escalamiento y aprobación. No inventes políticas,
   requisitos legales ni normas corporativas. Marca las recomendaciones como propuestas
   sujetas a validación por Seguridad de la Información, Legal o Cumplimiento.
   ```

13. Revise las propuestas de Copilot y modifique el documento únicamente cuando la recomendación sea compatible con el material de la lección, los controles de la matriz y las políticas conocidas de la organización.
14. Agregue al final del documento una declaración de control:

   > Este documento es una guía operativa de apoyo y no reemplaza las políticas corporativas, los procedimientos aprobados, los requisitos legales ni las decisiones de las funciones autorizadas. Cualquier contradicción o duda debe escalarse antes de su uso formal.

**Salida esperada:**

Un documento Word breve, estructurado y aplicable que defina el uso responsable de Copilot en auditorías de calidad, con controles de datos, validación humana, trazabilidad y escalamiento.

**Verificación:**

- La guía incluye todas las secciones obligatorias.
- La guía indica claramente qué información puede utilizarse y qué información debe anonimizarse o evitarse.
- La guía exige revisión humana antes de utilizar contenido generado como hallazgo, evidencia, decisión o documento controlado.
- La guía establece puntos pendientes de validación por Seguridad de la Información, Legal o Cumplimiento.
- La guía relaciona los controles con el hallazgo de Lab 06 y la checklist de Lab 07.

---

### Paso 5. Realizar una revisión cruzada entre la matriz y la guía

**Objetivo:** Confirmar que los controles definidos en Excel estén reflejados en la guía operativa de Word y que no existan contradicciones.

**Instrucciones:**

1. Abra simultáneamente:
   - `08_Matriz_Control_Riesgos_Copilot.xlsx`
   - `08_Guia_Uso_Responsable_Copilot.docx`
2. Revise cada uno de los siete riesgos obligatorios de la matriz.
3. Confirme que la guía contiene una instrucción operativa asociada a cada riesgo:

| Riesgo | Elemento que debe aparecer en la guía |
|---|---|
| Información no sustentada | Contraste obligatorio con evidencia objetiva |
| Datos sensibles en prompts | Anonimización, minimización o prohibición de uso |
| Acceso inadecuado | Uso de archivos autorizados y verificación de permisos |
| Sesgo de priorización | Revisión por responsable competente y consulta a áreas involucradas |
| Pérdida de trazabilidad | Registro de fuentes, versiones, revisión y aprobación |
| Envío erróneo | Revisión de destinatarios y autorización antes de comunicaciones oficiales |
| Aceptación automática | Prohibición explícita de aprobar contenido sin validación humana |

4. Verifique que el nivel de rigor de la guía aumente para usos de mayor impacto.
5. Asegure que la guía clasifique como uso de alto riesgo, o equivalente, las siguientes situaciones:
   - Conclusiones de auditoría.
   - Determinación de causa raíz.
   - Decisiones de CAPA.
   - Liberación de producto.
   - Evaluación de seguridad.
   - Comunicaciones oficiales a clientes, autoridades o proveedores.
   - Interpretación legal, contractual o regulatoria.
6. Si identifica una contradicción, corrija primero la matriz o la guía según corresponda y registre la decisión en el campo `Observaciones` de la matriz.
7. Guarde ambos archivos y espere a que OneDrive indique que la sincronización se completó.

**Salida esperada:**

Dos entregables coherentes entre sí, donde la matriz define los riesgos y controles, y la guía explica cómo aplicar esos controles durante el trabajo de auditoría.

**Verificación:**

- Cada uno de los siete riesgos mínimos tiene una medida operativa correspondiente en la guía.
- La guía no presenta a Copilot como fuente de decisión, evidencia o aprobación autónoma.
- Los documentos no contienen referencias inventadas a políticas, normas o requisitos legales.
- Ambos archivos están almacenados en la ruta corporativa sincronizada.

## Validación y pruebas

Complete la siguiente validación final antes de considerar terminado el laboratorio.

### Prueba 1. Cobertura de riesgos

Verifique que `08_Matriz_Control_Riesgos_Copilot.xlsx` incluya, como mínimo, los riesgos R-01 a R-07:

- [ ] Generación de información no sustentada.
- [ ] Uso de datos sensibles en prompts.
- [ ] Acceso inadecuado a archivos.
- [ ] Sesgo en priorización o interpretación.
- [ ] Pérdida de trazabilidad.
- [ ] Envío erróneo de comunicaciones.
- [ ] Aceptación automática de contenido generado.

**Resultado esperado:** los siete riesgos están registrados con proceso afectado, causa, consecuencia, evaluación, controles, responsable, evidencia, nivel residual y escalamiento.

### Prueba 2. Trazabilidad de controles

Seleccione tres riesgos de nivel alto o crítico y compruebe que cada uno tenga:

- [ ] Control preventivo.
- [ ] Control detectivo.
- [ ] Control correctivo.
- [ ] Responsable asignado.
- [ ] Evidencia verificable del control.
- [ ] Criterio de escalamiento.

**Resultado esperado:** ningún riesgo alto o crítico depende únicamente de una recomendación de Copilot o de una revisión informal no documentada.

### Prueba 3. Validación de información sensible

Revise los prompts utilizados y el contenido de ambos entregables.

- [ ] No se incluyeron credenciales, contraseñas, tokens o información de seguridad.
- [ ] No se incluyeron nombres reales de empleados ni datos personales innecesarios.
- [ ] La información de clientes, proveedores o contratos fue anonimizada o excluida según el caso.
- [ ] Se utilizó únicamente el tenant corporativo autorizado y el repositorio corporativo.

**Resultado esperado:** los documentos son aptos para revisión interna sin exponer información sensible innecesaria.

### Prueba 4. Validación humana

Revise la guía en Word y confirme que establece explícitamente:

- [ ] Copilot produce borradores, hipótesis o propuestas, no conclusiones definitivas.
- [ ] Los hechos y cifras deben contrastarse con registros controlados.
- [ ] La evidencia objetiva debe diferenciarse del contenido generado.
- [ ] Los documentos controlados requieren revisión y aprobación humana.
- [ ] Las dudas de seguridad, privacidad, legalidad o cumplimiento deben escalarse.

**Resultado esperado:** la guía cumple el principio de que la responsabilidad final permanece en las personas autorizadas.

### Criterio de aprobación del laboratorio

El laboratorio se considera completado cuando:

1. Los dos archivos de salida existen en la carpeta corporativa.
2. La matriz contiene al menos los siete riesgos obligatorios.
3. La guía contiene controles de información, validación, trazabilidad y escalamiento.
4. Los controles están relacionados con el hallazgo de Lab 06 y la checklist de Lab 07.
5. No se han modificado ni sobrescrito los archivos fuente entregados por el instructor.

## Solución de problemas

### Problema 1: Copilot no aparece en Excel o Word, o muestra que no tiene acceso al contenido corporativo

**Síntomas:**

- El icono de Copilot no aparece en la cinta de opciones.
- Copilot solicita iniciar sesión repetidamente.
- Copilot indica que no puede acceder al archivo o que no hay licencia disponible.
- Las funciones de Copilot aparecen deshabilitadas.

**Causa probable:**

La aplicación no está conectada con la cuenta corporativa correcta, la licencia de Microsoft 365 Copilot no está asignada o sincronizada, el archivo no está guardado en una ubicación corporativa compatible, o existe una restricción temporal de red o políticas del tenant.

**Corrección:**

1. Confirme que inició sesión en Word y Excel con la cuenta corporativa de Microsoft Entra ID.
2. Verifique que el archivo esté guardado en OneDrive for Business o SharePoint corporativo, no en una carpeta personal.
3. Cierre y vuelva a abrir Word o Excel.
4. Compruebe el estado de sincronización de OneDrive y espere a que finalice.
5. Si el problema persiste, registre el mensaje mostrado y contacte al administrador de Microsoft 365 o a la mesa de servicio para validar licencia, políticas de Copilot y permisos del tenant.

### Problema 2: Copilot propone controles, requisitos o referencias que no se pueden comprobar

**Síntomas:**

- Copilot cita cláusulas, políticas o procedimientos que no existen en los documentos disponibles.
- Propone una causa raíz definitiva sin evidencia suficiente.
- Sugiere controles demasiado genéricos o no aplicables al proceso auditado.
- Confunde hipótesis con hechos o evidencia objetiva.

**Causa probable:**

El prompt fue demasiado amplio, el contexto proporcionado fue incompleto, Copilot generó contenido plausible no sustentado o se solicitó una conclusión en lugar de una propuesta preliminar.

**Corrección:**

1. No copie el contenido generado directamente a un documento controlado.
2. Reformule el prompt para limitar el alcance y exigir propuestas sujetas a validación.
3. Solicite que Copilot identifique preguntas, vacíos de información o controles posibles, en lugar de pedir conclusiones definitivas.
4. Contraste cada afirmación con el hallazgo de Lab 06, la checklist de Lab 07, registros controlados y políticas corporativas vigentes.
5. Marque las afirmaciones no verificables como `No confirmadas` y elimínelas o escálelas al responsable de Calidad, Seguridad de la Información, Legal o Cumplimiento según corresponda.

## Limpieza

1. Guarde los archivos finales:
   - `08_Matriz_Control_Riesgos_Copilot.xlsx`
   - `08_Guia_Uso_Responsable_Copilot.docx`
2. Confirme que ambos archivos se sincronizaron correctamente con OneDrive for Business y SharePoint Online.
3. Cierre los archivos fuente:
   - `L06_Hallazgo_Critico_v1.docx`
   - `L07_Checklist_Auditoria_Calidad_v1.xlsx`
4. Verifique que los archivos fuente no hayan sido modificados ni sobrescritos.
5. Elimine notas temporales locales que contengan información de trabajo no necesaria, siempre que no constituyan evidencia requerida por el procedimiento corporativo.
6. No elimine los dos entregables finales ni los documentos de los laboratorios previos.
7. Cierre Word y Excel si no se utilizarán para otra actividad del curso.

## Resumen

En este laboratorio se creó una matriz de control de riesgos para el uso de Microsoft 365 Copilot en auditorías internas de calidad y una guía operativa de uso responsable. La matriz documenta riesgos inherentes y residuales, controles preventivos, detectivos y correctivos, responsables, evidencias y criterios de escalamiento.

La guía establece que Copilot puede acelerar la organización, redacción y exploración preliminar de información, pero no sustituye la evidencia objetiva, el análisis técnico, la investigación de causas raíz ni las aprobaciones formales. El uso responsable exige minimizar datos sensibles, verificar permisos, contrastar resultados con registros controlados, diferenciar hipótesis de hechos y conservar trazabilidad de las decisiones.

### Recursos de consulta

- [ISO/IEC 42001:2023 — Sistemas de gestión de inteligencia artificial](https://www.iso.org/standard/81230.html)
- [NIST Artificial Intelligence Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [Principios de IA de la OCDE](https://oecd.ai/en/ai-principles)
- [Microsoft Responsible AI](https://www.microsoft.com/en-us/ai/responsible-ai)
