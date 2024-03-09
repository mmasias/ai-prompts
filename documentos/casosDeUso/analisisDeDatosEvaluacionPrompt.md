<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/documentos/prompts/README.md)|[Ingeniería de Prompts](/documentos/ingenieriaDePrompts/README.md)|[Patrones](/documentos/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/documentos/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Evaluación del prompt

## Fortalezas:

- Claro y bien estructurado.
- Proporciona una descripción detallada de cada columna, lo cual es esencial para comprender los datos.
- Establece un objetivo inmediato al final, que es confirmar la correcta interpretación del documento.

## Áreas de mejora:

- Es posible hacerlo más conciso en la introducción, lo que podría permitir que el modelo se concentre más rápidamente en los datos.
- Una pequeña indicación sobre el objetivo final (además de la verificación inicial) podría guiar al modelo sobre el tipo de análisis que se espera.

## Prompt original vs Prompt propuesto

### Original

```
Vamos a analizar este documento, que es un resumen de la evolución académica de un conjunto de alumnos a lo largo de varios cursos de un grado universitario. Contiene las siguientes columnas, dónde creo que debo detallar algo te lo explico:

[...]

Empecemos por confirmar que se ha recibido adecuadamente el documento. Para esto, dime cuántos años académicos reconoces.
```

### Propuesto
```
Voy a proporcionarte datos académicos de un grado universitario para analizar tendencias a lo largo de varios cursos. La tabla contiene las siguientes columnas:

[...]
Por favor, confirma la recepción del documento indicando cuántos años académicos reconoces y, a continuación, proporciona un resumen estadístico inicial.
```
