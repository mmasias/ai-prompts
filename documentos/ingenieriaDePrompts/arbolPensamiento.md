<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Árbol de pensamiento

```
Bob está en la sala de estar.
Camina hacia la cocina, llevando una taza.
Él pone una pelota en la taza y lleva la taza al dormitorio.
Voltea la taza boca abajo y luego camina hacia el jardín.
Pone la taza en el jardín y luego camina hacia el garaje.
¿Dónde está la pelota?
```

|ChatGPT 3.5|ChatGPT 4|Claude|Gemini|Perplexity|Neuroflash|Huggingface (Mistral)|Copilot|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:
|[📋](https://chat.openai.com/share/dab16269-912b-4987-be3f-0215ba6e992c)|[📋](https://chat.openai.com/share/e21450b5-9d55-441e-9cb3-673afc365f80)|[📋](https://claude.ai/chat/3a1554f1-af18-4894-ac03-05e5955e8100)|[📋](https://g.co/gemini/share/2789c30f1dd2)|[📋](https://www.perplexity.ai/search/Bob-est-en-QMP1HrIjQ5mIGUFhp37eZA#0)|[📋](https://app.neuro-flash.com/ai-writer/e833d1d68a55890ea3072b671ae03c4d/preview)|[📋](https://huggingface.co/chat/conversation/661714c2a490f2673196c15f)|[📋](https://copilot.microsoft.com/sl/jYKwIpvUzT2)|
|Cocina|Jardín|Dormitorio|Jardín|En la taza no está|Dormitorio++|Dormitorio|Taza@Jardin

Esto se podría mejorar con la cadena del pensamiento, pidiéndole al LLM que vaya explicando su respuesta, pero se ha encontrado que la efectividad varia (2DO: hacer los ejemplos)

```
Imagina que tres expertos diferentes están respondiendo a esta pregunta. 
Todos los expertos escribirán un paso de su pensamiento, luego lo compartirán con el grupo. 
Luego, todos los expertos pasarán al siguiente paso, etc. 
Si algún experto se da cuenta de que está equivocado en algún momento, entonces se retirará. 
La pregunta es...
```

|ChatGPT 3.5|ChatGPT 4|Claude|Gemini|Perplexity|Neuroflash|Huggingface (Mistral)|Copilot|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:
|[📋](https://chat.openai.com/share/dab16269-912b-4987-be3f-0215ba6e992c)|[📋](https://chat.openai.com/share/e21450b5-9d55-441e-9cb3-673afc365f80)|[📋](https://claude.ai/chat/3a1554f1-af18-4894-ac03-05e5955e8100)|[📋](https://g.co/gemini/share/2789c30f1dd2)|[📋](https://www.perplexity.ai/search/Bob-est-en-QMP1HrIjQ5mIGUFhp37eZA#0)|[📋](https://app.neuro-flash.com/ai-writer/e833d1d68a55890ea3072b671ae03c4d/preview)|[📋](https://huggingface.co/chat/conversation/661714c2a490f2673196c15f)|[📋](https://copilot.microsoft.com/sl/jYKwIpvUzT2)|
|Cocina|Jardín|Dormitorio|Jardín|En la taza no está|Dormitorio++|Dormitorio|Taza@Jardin
|[📋](https://chat.openai.com/share/a5f146b5-15d0-4d58-b62d-abfcb3318cce)|[📋](https://chat.openai.com/share/44001e8f-26bd-4e92-aabc-3647c8593e39)|[📋](https://claude.ai/chat/14291ee0-d58b-467e-870e-c268f44e75a3)|[📋](https://g.co/gemini/share/7f62c7ccdd89)|[📋](https://www.perplexity.ai/search/Imagina-a-tres-kEBpJLOmQiaHEOxpba5YBw)|[📋](https://app.neuro-flash.com/ai-writer/c065303f45dab80e1a9932598c86ed35/preview)|[📋](https://huggingface.co/chat/conversation/661719fff88d12d297535fce)|[📋](https://copilot.microsoft.com/sl/JIJ3rdtavY)|
|Dormitorio|Dormitorio|Jardín|Faltan datos|"Meme"|Dormitorio|En la taza|3 posibles sitios|
