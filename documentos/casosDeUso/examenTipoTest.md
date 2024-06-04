<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Caso de Uso > Creación de examen tipo test

## ¿Por qué?

xQ'

## ¿Qué?

A partir de un documento, generar un examen tipo test.

## ¿Para qué?

paQ'

## ¿Cómo?

- Carga inicial, confirmación de una correcta respuesta.
- Formalización del prompt.
- Creación de un GPT.

### Transcripciones

|Motor|Comentario|
|-|-|
[ChatGPT-3.5]()|
[ChatGPT-4]()|
[ChatGPT-4o](https://chatgpt.com/share/dc4137bb-0c94-4fda-a871-28217e96ce5f) / [ChatGPT-4o](https://chatgpt.com/share/bcc45227-a4a0-4927-b834-fee86e6cb86d)|
[Claude]()|
[Perplexity]()|
[Gemini]()|
[Copilot]()|
[NeuroFlash]()|

#### Detalles

- A veces podría detectar "[actividad inusual](/documentos/imagenes/actividadInusual.png)"
- La ventana de contexto y los documentos: adjuntar documentos le permite "mitigar" la limitación del contexto.
  - Con los 10 primeros documentos: falla si se le pide "recordar", acierta si se le indica utilizar los documentos como referencia.
  - En el trabajo del documento 15, empieza a "olvidar" que debe devolver 20 preguntas (devuelve 21). Lo comprobamos en el documento 16, donde devuelve 19 en lugar de 20.
  - Al trabajar sobre 20 documentos se confirma que pidiéndole que utilice los documentos como referencia, se supera el problema del olvido en la ventana de contexto.
  