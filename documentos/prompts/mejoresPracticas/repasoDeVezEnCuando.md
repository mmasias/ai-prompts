<div align=right>

||[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Para aplicaciones de diálogo que requieren conversaciones muy largas, resuma o filtre el diálogo anterior

> Bloque: Divide y vencerás

## ¿Por qué?

Dado que los modelos GPT tienen un límite en la cantidad de tokens o palabras que pueden procesar en una sola entrada, las conversaciones extensas pueden exceder esta capacidad. Al resumir o filtrar diálogos anteriores, se garantiza que la información más relevante esté presente, optimizando la coherencia y relevancia de la respuesta del modelo sin perder el contexto esencial.

## ¿Qué?

Consiste en sintetizar, seleccionar o condensar partes anteriores de una conversación para conservar solo la información más pertinente, garantizando así que el modelo pueda responder adecuadamente en diálogos prolongados.

## ¿Para qué?

- Para mantener la relevancia y coherencia en aplicaciones de diálogo extensas.
- Para asegurar que la información crucial no quede fuera debido a las restricciones de longitud del modelo.
- Para prevenir redundancias y repetición innecesaria de información.

## ¿Cómo?

|||Ejempo|
|-|-|-|
Identifique puntos clave|Al revisar un diálogo, seleccione las partes más cruciales o relevantes que deben conservarse para el contexto.|En una conversación sobre estrategias de marketing, mantenga las menciones específicas de las técnicas discutidas pero omita saludos o interacciones genéricas.
|Sintetice la información|En lugar de mantener largas cadenas de texto, reformule la información para que sea más concisa sin perder su esencia.|Cambiar "El usuario preguntó sobre las mejores estrategias de marketing y el modelo respondió con cinco técnicas diferentes" a "Se discutieron cinco estrategias de marketing".
Use marcadores o delimitadores|Al presentar el diálogo resumido o filtrado, utilice marcadores para señalar el inicio y el final del contexto relevante.|"[Inicio de resumen] Se discutieron cinco estrategias de marketing. [Fin de resumen]".
||Ejemplo|[Una conversación larga, con pinceladas de contextualización](https://chat.openai.com/share/b175c472-3421-4be3-b270-aa8df5172557)

Al resumir o filtrar diálogos anteriores en aplicaciones que requieren conversaciones extensas, se mantiene el foco en la información más esencial, permitiendo que el modelo genere respuestas más precisas y contextualizadas.