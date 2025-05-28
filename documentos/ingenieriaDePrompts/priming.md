<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Ingeniería de Prompts](README.md)<br>Base metodológica necesaria|Metodología > Ingeniería de Prompts > **Priming**|[Árbol de pensamiento](arbolPensamiento.md)<br>Estructuras complejas
|[Contexto en prompts](../prompts/componentes.md)<br>Componente clave para priming||[Chain of Thought](chainOfThought.md)<br>Razonamiento guiado

<i>**Relacionado**: [0-Shot Prompting](0ShotPrompting.md) - Otra forma de guiar sin ejemplos / [x-Shot Prompting](xShotPrompting.md) - Contraste con ejemplos / [Acrónimo](../casosDeUso/acronimo.md) - Caso práctico de priming</i>

</div>

# Ingeniería de Prompts > Priming

> *[Efecto relacionado con la memoria implícita por el cual la exposición a determinados estímulos influye en la respuesta que se da a estímulos presentados con posterioridad.](https://es.wikipedia.org/wiki/Primado_(psicolog%C3%ADa))*

## ¿Por qué?

- Los modelos de lenguaje vienen pre entrenados, pueden dar respuestas.
- Algunas veces estas respuestas son excesivamente generales y ambiguas.
- Además, la manera que tenemos para comunicar también puede ser ambigua.
- Hace falta reducir y afinar por ambos lados, de modo que queden más claras las intenciones del usuario y se guíen a los modelos de lenguaje para proporcionar respuestas más precisas y contextuales.

## ¿Qué?

Proceso de alimentar a un sistema de inteligencia artificial con información que oriente sus respuestas. 

En el caso de la ingeniería de prompts, nos referimos a las indicaciones o comandos iniciales que se proporcionan a un modelo de lenguaje para que genere respuestas o contenido de texto.

Esta podría ser cualquier cosa: desde la definición de un término, la descripción de una situación, o la aclaración de la intención de la pregunta.

## ¿Para qué?

Para comprender mejor la intención del usuario y generar respuestas más adecuadas.

|Respuestas 
|-|
Definir la precisión
Afinar la intención de coherencia
Más enfocadas a la intención de la pregunta

Por ejemplo, si estamos pidiendo a la IA que genere un poema, podríamos usar el priming para especificar el tono (alegre, triste), el tema (amor, naturaleza), y el estilo (haiku, soneto) que queremos.

## ¿Cómo?

- [Acrónimo](/documentos/casosDeUso/acronimo.md)
- 
