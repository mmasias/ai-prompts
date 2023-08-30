# Análisis de datos

## ¿Por qué?

**Información Estratégica de Educación:** En el ámbito académico, el seguimiento de los resultados y la evolución de los alumnos a lo largo de los años es crucial. Puede revelar tendencias, identificar áreas de mejora y proporcionar insights sobre la eficacia de los métodos de enseñanza y evaluación.

## ¿Qué?

**Análisis Detallado de Datos Académicos:** Examinando una tabla en formato CSV que refleja el rendimiento y las estadísticas de los estudiantes en un grado universitario a lo largo de varios cursos académicos.

## ¿Para qué?

**Identificación de Tendencias y Áreas de Mejora:** Con la ayuda de la inteligencia artificial, se pueden destacar tendencias ocultas, comprender mejor la dinámica estudiantil, y establecer bases para futuras estrategias educativas y decisiones administrativas.

## ¿Cómo?

|Claude|ChatGPT|
|-|-|
[📈](https://claude.ai/chat/939c89f2-806c-46d0-8f83-261e880aaeec)|[📈](https://chat.openai.com/share/e91a8a36-72c7-4d9e-9222-984ebae2b7bb)

|||
|-|-|
Preparación del Dataset|Se entrega al modelo un CSV estructurado con las columnas pertinentes que describen diferentes métricas y estadísticas relacionadas con el rendimiento estudiantil.
Verificación de la Integridad del Dataset|Antes de comenzar con el análisis, es esencial confirmar que el modelo ha interpretado y cargado correctamente el documento. Una forma de hacerlo es preguntando al modelo detalles específicos del dataset (como cuántos años académicos reconoce).
Análisis Descriptivo|Extraer estadísticas básicas para tener una idea general de los datos. Esto podría incluir cosas como promedios, medianas, modas, máximos y mínimos para las distintas métricas.
Análisis de Tendencias|Examinar cómo ciertas métricas han evolucionado a lo largo del tiempo. Por ejemplo, se podría ver cómo ha cambiado la tasa de éxito a lo largo de los años o cómo ha variado el número de no presentados.
Identificación de Anomalías|Detectar cualquier dato que se desvíe significativamente de lo esperado o de las tendencias generales. Esto puede indicar áreas que requieran una investigación más profunda.
Insights y Recomendaciones|Con base en el análisis realizado, el modelo puede proporcionar insights y sugerencias para mejorar el rendimiento estudiantil o abordar áreas problemáticas.
Iteración y Ajuste|Dependiendo de los resultados y las necesidades del usuario, se puede iterar en el análisis, haciendo preguntas más específicas o ajustando el enfoque.

### Prompt(s)


#### Prompt inicial

```
Vamos a analizar este documento, que es un resumen de la evolución académica de un conjunto de alumnos a lo largo de varios cursos de un grado universitario. Contiene las siguientes columnas, dónde creo que debo detallar algo te lo explico:

- AñoAcadémico: El año al que se corresponden los datos
- Curso: en curso dentro del grado en el que se imparte la asignatura (primero, segundo, tercero o cuarto)
- Semestre: Semestre al que corresponde la asignatura
- Convocatoria: Que puede ser ordinaria o extraordinaria. 
- ID_Asignatura: el identificador de la asignatura 
- Matriculados: número de alumnos matriculados.
- Primera Matricula: son, de los matriculados, cuantos se han matriculado por primera vez
- Aprobados: número de alumnos aprobados.
- Aprobados 1 Mat: cuantos de los que aprobaron son además matriculados por primera vez
- Reconocidos: cuántos alumnos han recibido un reconocimiento o convalidación de la asignatura
- Suspendidos: número de alumnos suspensos.
- No Presentados: número de alumnos que se matricularon pero no se presentaron a evaluación.
- % Primera Mat: dato porcentual de matriculados en primera matrícula con respecto a los matriculados totales 
- % Aprobados : dato porcentual de aprobados con respecto a los matriculados totales
- % Aprobados 1 Mat : dato porcentual de aprobados en primera matrícula con respecto a los matriculados totales
- % No Presentados : dato porcentual de alumnos que no se presentaron a evaluación con respecto a los matriculados totales
- % Suspensos : dato porcentual de suspensos con respecto a los matriculados totales
- Tasa de Exito : Relación entre los alumnos aprobados y los alumnos matriculados (quitando de los matriculados los no presentados)
- Tasa de Rendimiento : Relación entre los alumnos aprobados y los alumnos matriculados

Empecemos por confirmar que se ha recibido adecuadamente el documento. Para esto, dime cuántos años académicos reconoces.
```

## Prompts adicionales

Llegados a este punto, los siguientes pasos serían:

|Naturaleza|Prompt|
|-|-|
Descriptivo|¿Cuál ha sido el año académico con la mayor tasa de éxito? Y, ¿con la menor tasa de rendimiento?
Tendencias|¿Cómo ha evolucionado la tasa de éxito y la tasa de rendimiento a lo largo de los años? ¿Hay algún patrón observable?
Comparativo|¿Qué diferencias notables hay entre los datos de la convocatoria ordinaria y la extraordinaria en términos de tasas de éxito y rendimiento?
Análisis profundo|Basándote en los datos, ¿qué asignaturas parecen ser las más desafiantes para los estudiantes en términos de suspensos y no presentados?
Anomalías|¿Hay algún año académico o asignatura específica que se desvíe significativamente de las tendencias generales? Si es así, ¿puedes señalarlas?
Recomendaciones|Con base en los datos, ¿qué áreas podrían beneficiarse de una intervención o modificación en la estrategia educativa?

> [Evaluación del prompt por parte de ChatGPT](analisisDeDatosEvaluacionPrompt.md)
