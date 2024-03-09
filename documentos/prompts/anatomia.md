<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/documentos/prompts/README.md)|[Ingeniería de Prompts](/documentos/ingenieriaDePrompts/README.md)|[Patrones](/documentos/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/documentos/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Anatomía de un prompt

<div align=center>

| |
|:-:|
![](/documentos/imagenes/modelosUML/promptRecetaComponentesSimple.svg)

</div>

### Recetas, componentes y elementos

|[Componentes](componentes.md)|[Elementos](elementos.md)|[Recetas](recetas.md)|
|-|-|-|
Son las categorías fundamentales que definen un prompt.|Detalles específicos que existen dentro de los componentes.|Son combinaciones específicas y secuenciaciones de componentes (y por lo tanto, elementos) para lograr un resultado particular con el modelo de AI.
|- Tarea<br>- Instrucciones<br>- Contexto<br>- Parámetros/Configuraciones<br>- Entrada.|<br>- Temperatura (dentro de Parámetros)<br>- Rol (dentro de Contexto)<br>-  Tópico (dentro de Tarea)<br>- etc...|Similar a una receta de cocina: no sólo se trata de tener los ingredientes correctos (elementos), sino también de combinarlos de la manera correcta (componentes) y seguir un procedimiento específico (receta).
Cada componente tiene un papel específico en guiar o dar dirección al modelo de AI.|Los elementos dan detalles más granulares y específicos a los componentes para afinar el prompt.|Es la metodología aplicada para ensamblar componentes y elementos de una manera que optimice el resultado.

|Conexión entre los tres|
|-|
Imagine que está construyendo una casa (su resultado deseado del modelo AI).
**Los componentes** serían las categorías generales de materiales que necesita: cimientos, paredes, techo.
**Los elementos** serían las especificaciones y detalles de esos materiales: el tipo de concreto para los cimientos, el color y material de las paredes, el tipo de tejas para el techo.
**La receta** sería el plan arquitectónico que le dice en qué orden y cómo ensamblar esos materiales para construir la casa.

En la ingeniería de prompts, esta estructura jerárquica ayuda a descomponer y organizar la creación de prompts de manera que sean efectivos y generen el resultado deseado del modelo AI.
