<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Caso de Uso > Luego frente a Y al construir prompts

## ¿Por qué?

A veces, al hacer un prompt complejo con múltiples peticiones encadenadas mediante conjunciones como "y", es posible que no obtengamos la profundidad o el nivel de detalle deseado en las respuestas.

## ¿Qué?

Al utilizar conjunciones como "y" para encadenar peticiones, corremos el riesgo de que la IA trate de satisfacer ambas partes del prompt en un único esfuerzo, lo cual puede llevar a respuestas menos detalladas o a la omisión de ciertos puntos.

Usar transiciones claras como "luego" o dividir el prompt en oraciones o pasos distintos puede proporcionar una estructura más clara para la IA, permitiendo respuestas más precisas y detalladas.

## ¿Para qué?

- Mejora la precisión de las respuestas.
- Evita la sobrecarga informativa.
- Facilita la comprensión de la IA y la guía hacia respuestas más detalladas y organizadas.
- Minimiza la posibilidad de omitir aspectos clave en la respuesta.

## ¿Cómo?

### Transcripciones

|Motor|Comentario|
|-|-|
ChatGPT|[Usando **y**](https://chat.openai.com/share/de5d8a24-594a-45e1-a528-27fca6521fc6) / [Usando **luego**](https://chat.openai.com/share/17e92098-5a64-4655-873d-d78c4e27ed1b)
Perplexity
Claude|[Usando **y**](https://claude.ai/chat/3383413a-3cb3-4300-b84d-80aa48e9f1ab) / [Usando **luego**](https://claude.ai/chat/21a6e377-bef6-4d51-8893-aa4053ce28a1)
Bard|[Usando **y**](https://g.co/bard/share/51c34816dcce) / [Usando **luego**](https://g.co/bard/share/3510ac4a3752)
NeuroFlash|[Usando **y**](https://app.neuro-flash.com/ai-writer/fdfa5e4fe41ac1cc58f60b0cebfb9394/preview) / [Usando **luego**](https://app.neuro-flash.com/ai-writer/aee2abe0c0a632214d35598fd606944a/preview)
HuggingChat|[Usando **y**](https://hf.co/chat/r/u5AxJrm) / [Usando **luego**](https://hf.co/chat/r/yEhqIcx)

|Buenas prácticas|& Reflexiones
|-|-|
Descomposición de la solicitud|Se divide la petición original en dos partes distintas para obtener respuestas más específicas y detalladas.
Uso de transiciones claras|La transición "luego" actúa como una señal para la IA, indicando que se trata de una nueva solicitud que debe ser atendida después de la anterior.
Especificidad|Al pedir explícitamente comentarios sobre beneficios y luego sobre retos, estamos dando una guía clara sobre lo que esperamos en cada parte de la respuesta.

#### Antipatrón

