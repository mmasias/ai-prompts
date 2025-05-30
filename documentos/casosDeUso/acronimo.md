<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Caso de Uso > Creación de un acrónimo

## ¿Por qué?

Me gusta crear acrónimos. Es una buena manera de fijar en la memoria un concepto y crear una identificación con una idea, un producto, una marca, etc.

## ¿Qué?

|SIGLA|Significado|Uso|
|-|-|-|
|PANAL|**P**uerta de **A**cceso **N**ormalizada a **A**plicaciones **L**MS|Frontend campus virtual|
|COLMENA|**CO**mponentes **L**igeros para el **M**odelado de **E**RPs de **N**aturaleza **A**cadémica|Framework de desarrollo|
|GUIAA|**G**estión **U**nificada de **I**nvestigación, **A**dministración y **A**cademia|ERP construido con COLMENA|
|AGORA|**A**plicación de **G**estión y **OR**denamiento **A**cadémico|ERP construido con COLMENA|

## ¿Para qué?

Dado que para el seminario de inteligencia artificial estoy preparando algunos ejemplos, vamos a darle nombre a un ejemplo que he creado ad-hoc.

Además, así al resolverlo veremos de poner en práctica buenas prácticas de ingenieria de prompts. 

Adicionalmente, vemos que contesta cada una de las IAs

## ¿Cómo?

### Transcripciones 

|Motor|Comentario|
|-|-|
[ChatGPT](https://chat.openai.com/share/57e396ef-1732-4321-94c8-a143267c0b01)
[Perplexity](https://www.perplexity.ai/search/aeadc97e-3f6b-43f9-8a6c-d6305889b7ea?s=c)
[Claude](https://claude.ai/chat/65ccee63-fdde-460a-8f31-7646a677e473)|*No está en abierto*
[Bard](/documentos/imagenes/acronimos.bard.png)
[Gemini](https://g.co/gemini/share/5d49ef77f41f)
[NeuroFlash](https://app.neuro-flash.com/ai-writer/ac997dc2a342a98ff857177183efff15/preview)|😂 y actualizado para incluir el enlace.
[Copilot](https://sl.bing.net/f3rft2X0xBQ)|Parece que pilla la sutileza del reuso del término PANAL y abejas

|Buenas prácticas|& Reflexiones
|-|-|
[Priming](/ingenieriaDePrompts/priming.md)
[Divide y vencerás](/ingenieriaDePrompts/divideVenceras.md)
Contextualización|Al proporcionar acrónimos anteriores con sus respectivas descripciones, el prompt establece claramente el tipo de respuesta que busca.
Especificidad|Se detallan funciones muy concretas del sistema para el cual se necesita el acrónimo, orientando la generación hacia algo pertinente.
Invocación de creatividad|La solicitud de un acrónimo "ingenioso y divertido" invita al modelo a ir más allá de una respuesta genérica o estándar.
Anclaje|Se utiliza un tono coloquial y se presentan ejemplos previos como anclas para que el modelo comprenda el tipo de acrónimo que se busca.

#### Antipatrón

*[:link:](https://chat.openai.com/share/1523390e-f288-4507-ba1e-179c086c86a4) Me gustan los acrónimos. Hice uno hace años. Tengo un proyecto de IA. Se trata de un formulario y hace cosas con las respuestas. ¿Tienes alguna idea para un acrónimo?*

|Punto|Detalle|
|-|-|
Ambigüedad|A diferencia del prompt original, este antiejemplo carece de detalles específicos. Menciona "hacer cosas con las respuestas", lo que es demasiado vago para que se pueda generar un acrónimo coherente y significativo.
Falta de Contexto|Aunque indica que al usuario le gustan los acrónimos y que creó uno en el pasado, no proporciona ejemplos de esos acrónimos ni la lógica detrás de ellos, lo que podría haber ayudado al modelo a entender mejor las expectativas.
Generalidad|Se menciona un "proyecto de IA" pero no se define qué aspecto de la inteligencia artificial se está abordando o cómo se relaciona con el formulario.
Demasiado breve|Si bien ser conciso puede ser útil en algunos contextos, en este caso, la brevedad resulta en falta de información esencial para una respuesta adecuada.
