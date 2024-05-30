<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# De esquemas a diagramas

## ¿Por qué?

En el ámbito del marketing y la publicidad, visualizar procesos y flujos es esencial para comprender y comunicar ideas complejas. Y aunque los LLMs que estamos trabajando no permiten dibujar directamente (las versiones libres), puede generar códigos que, al ser interpretados por herramientas específicas, producen visualizaciones claras y efectivas.

Utilizar herramientas como plantUML permite transformar instrucciones textuales en diagramas visuales, facilitando la comprensión y colaboración entre equipos.

## ¿Qué?

Se solicita que el LLM genere un código en plantUML para planificar reuniones con responsables de diversas áreas de una empresa de coches. Con esto se espera recibir código en formato plantUML que, al ser interpretado por una herramienta compatible, muestre un diagrama.

## ¿Para qué?

- **Claridad**: Transformar instrucciones o planificaciones textuales en diagramas visuales facilita la comprensión y reduce ambigüedades.
- **Eficiencia**: Generar códigos para producir visualizaciones ahorra tiempo y esfuerzo en comparación con dibujar manualmente.
- **Versatilidad**: El código generado puede ser modificado o adaptado fácilmente para diferentes necesidades o cambios en la planificación.

## ¿Cómo?

|||
|-|-|
Solicitud al Modelo|Presentar al LLM el escenario o la necesidad específica para la que se requiere una visualización.
Generación del Código|El LLM producirá un código en plantUML basado en la solicitud, código que puede utilizarse en sitios como el de [PlantText](https://www.planttext.com/) para generar la imagen.
Interpretación del Código|Utilizar una herramienta o plataforma que soporte plantUML para interpretar el código y generar el diagrama de flujo visual.
Modificación (si es necesario)|Si se requieren cambios o adaptaciones, el código puede ser modificado directamente y luego reinterpretado para obtener una nueva visualización.

*"Soy publicista y necesito planificar un conjunto de reuniones. Haz una planificación de una serie de reuniones con responsables de diversas áres de una empresa de comercialización de coches, para recabar requisitos para una campaña de lanzamiento de un producto. Preséntame la planificación en formato de código  plantUML que puedo utilizar para generar un diagrama de flujo dónde se vea la secuencia de reuniones que deben realizarse"*

|[ChatGPT](https://chat.openai.com/)|[Claude](https://claude.ai/chats)|[Gemini](https://gemini.google.com/app)<br>[Bard](https://bard.google.com/)|[Perplexity](https://www.perplexity.ai/)|[Neuroflash](https://app.neuro-flash.com/aiWriter)|[Huggingface](https://huggingface.co/chat)|[Copilot](https://copilot.microsoft.com/)
|:-:|:-:|:-:|:-:|:-:|:-:|:-:
|👍🏻|👍🏻|👎🏻👎🏻|🤔|👍🏻|🤔|👎🏻


### Diagrama generado

#### Creando el proceso

|||
|-|-|
[ChatGPT](https://chat.openai.com/share/07c15419-e600-421c-906a-8a3d9a87a81b)|![](/documentos/imagenes/modelosUML/esquemaDiagramasChatGPT.svg)|
[Claude](https://claude.ai/chat/e82eecd2-9833-4c0e-b634-2156e35e3750)|![](/documentos/imagenes/modelosUML/esquemaDiagramasClaude.svg)


#### Sintetizando y proponiendo mejoras a un proceso existente

*Fuente: https://filestage.io/es/blog/flujos-de-trabajo-de-marketing/*

|||
|-|-|
[ChatGPT](https://chat.openai.com/share/a28277fc-807a-4227-967a-cf1ad92cd288)|![](/documentos/imagenes/modelosUML/esquemaDiagramas002ChatGPT.svg)
||![](/documentos/imagenes/modelosUML/esquemaDiagramas002MejoradoChatGPT.png)|
