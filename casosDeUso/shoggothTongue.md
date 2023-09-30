<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/prompts/README.md)|[Ingeniería de Prompts](/ingenieriaDePrompts/README.md)|[Patrones](/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Caso de Uso > NombreCasoDeUso

## ¿Por qué?

La eficiencia en la comunicación con modelos de lenguaje es clave, especialmente cuando trabajamos con sistemas automatizados y límites en la cantidad de tokens.

Optimizar la longitud de los prompts sin perder información puede resultar en interacciones más rápidas y costes reducidos, especialmente en entornos de API.

## ¿Qué?

Estamos introduciendo la técnica de *shoggoth tongue*, que implica comprimir un prompt de forma que mantenga toda la información conceptual usando el mínimo número de tokens posibles.

Esta compresión no es para que un humano la interprete, sino para que la IA la recupere y actúe según las instrucciones iniciales.

## ¿Para qué?

| | |
|-|-|
Objetivo|Entender y practicar la creación de prompts comprimidos que permitan comunicarse con la IA de forma más eficiente, conservando la intención original del prompt.
Beneficio|Maximizar el número de interacciones con la IA dentro de un límite de tokens, resultando en un ahorro significativo en entornos de API y una mejora en la velocidad de respuesta.

## ¿Cómo?

### Transcripciones

|Motor|Comentario|
|-|-|
ChatGPT|[Definición](https://chat.openai.com/share/9b269f73-1bff-487c-bce8-24bd7d12860a) / [Uso](https://chat.openai.com/share/0891c589-c61d-42e8-be85-7463107f68a2)
[Perplexity]
[Claude]
[Bard]
[NeuroFlash]

|Buenas prácticas|& Reflexiones
|-|-|

#### Antipatrón

*[:link:]() EJ_DE_ANTI_PATRON*

|Punto|Detalle|
|-|-|
