<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Patrón Generador de Visualización

## Intención y Contexto

La intención de este patrón es utilizar la generación de texto para crear visualizaciones. Muchos conceptos son más fáciles de comprender en formato de diagrama o imagen. Este patrón permite la creación de visualizaciones generando entradas para otras herramientas de visualización conocidas que utilizan texto como entrada, como Graphviz Dot o DALL-E. Este patrón puede proporcionar una forma más completa y efectiva de comunicar información combinando las fortalezas de las herramientas de generación de texto y visualización.

## Motivación

Los LLM generalmente producen texto y no pueden producir imágenes. Por ejemplo, un LLM no puede dibujar un diagrama para describir un gráfico. El patrón del Generador de Visualización supera esta limitación generando entradas textuales en el formato correcto para conectar con otra herramienta que genera el diagrama correcto. La motivación detrás de este patrón es mejorar la salida del LLM y hacerla más visualmente atractiva y fácil de entender para los usuarios.

## Estructura e Ideas Clave

|Declaraciones contextuales
|-|
|Genera un X que pueda proporcionar a la herramienta Y para visualizarlo.

El objetivo de las declaraciones contextuales es indicar al LLM que la salida que va a producir, "X", va a ser una imagen. Dado que los LLM no pueden generar imágenes, la frase "que pueda proporcionar a la herramienta Y para visualizarlo" aclara que no se espera que el LLM genere una imagen, sino que se espera que produzca una descripción de la imagen consumible por la herramienta Y.

## Ejemplo de Implementación

> “Cada vez que te pida visualizar algo, crea un archivo Graphviz Dot o un prompt DALL-E que pueda usar para crear la visualización. Elige las herramientas adecuadas según lo que necesite ser visualizado.”

Este ejemplo del patrón añade una calificación de que el tipo de salida para la visualización puede ser para Graphviz o DALL-E. El LLM puede seleccionar la herramienta basada en las necesidades de la visualización y las capacidades de cada herramienta.

## Consecuencias

El patrón crea un canal de modo que la salida pueda ser utilizada para renderizar una visualización. El canal puede incluir generadores de IA, como DALL-E, que pueden producir visualizaciones ricas. El patrón permite al usuario expandir las capacidades expresivas de la salida al dominio visual.
