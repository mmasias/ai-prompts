# Anatomía de un prompt

## Básica

### Elementos

|Elemento|Descripción|
|-|-|
Input - Entrada|La conversación
Output - Salida|La respuesta
Parámetros|El ecualizador

#### Parámetros

- **Temperatura**, que gobierna la creatividad
- **Max tokens**, que gobierna la longitud de la respuesta

## Avanzada

| |
|:-:|
![](/imagenes/modelosUML/promptRecetaComponentes.svg)


### Recetas, componentes y elementos

|Componentes|Elementos|Recetas|
|-|-|-|
Son las categorías fundamentales que definen un prompt.|Detalles específicos que existen dentro de los componentes.|Son combinaciones específicas y secuenciaciones de componentes (y por lo tanto, elementos) para lograr un resultado particular con el modelo de AI.
Ejemplos: Tarea, Instrucciones, Contexto, Parámetros/Configuraciones, Entrada.|Ejemplos: Temperatura (dentro de Parámetros), Rol (dentro de Contexto), Tópico (dentro de Tarea).|Similar a una receta de cocina: no sólo se trata de tener los ingredientes correctos (elementos), sino también de combinarlos de la manera correcta (componentes) y seguir un procedimiento específico (receta).
Cada componente tiene un papel específico en guiar o dar dirección al modelo de AI.|Los elementos dan detalles más granulares y específicos a los componentes para afinar el prompt.|Es la metodología aplicada para ensamblar componentes y elementos de una manera que optimice el resultado.
[Ver más](componentes.md)|[Ver más](elementos.md)|[Ver más](recetas.md)

|Conexión entre los tres|
|-|
Imagine que está construyendo una casa (su resultado deseado del modelo AI).
**Los componentes** serían las categorías generales de materiales que necesita: cimientos, paredes, techo.
**Los elementos** serían las especificaciones y detalles de esos materiales: el tipo de concreto para los cimientos, el color y material de las paredes, el tipo de tejas para el techo.
**La receta** sería el plan arquitectónico que le dice en qué orden y cómo ensamblar esos materiales para construir la casa.

En la ingeniería de prompts, esta estructura jerárquica ayuda a descomponer y organizar la creación de prompts de manera que sean efectivos y generen el resultado deseado del modelo AI.