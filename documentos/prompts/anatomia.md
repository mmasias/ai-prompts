<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

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
