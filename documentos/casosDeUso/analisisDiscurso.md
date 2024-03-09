<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/documentos/prompts/README.md)|[Ingeniería de Prompts](/documentos/ingenieriaDePrompts/README.md)|[Patrones](/documentos/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/documentos/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Caso de Uso > Transcripción y análisis de un discurso

## ¿Por qué?

En la era digital, contamos con una cantidad inmensa de información en forma de discursos, entrevistas, conferencias y demás.

La necesidad de sintetizar rápidamente esta información y obtener puntos clave se vuelve esencial para decisiones, investigación y divulgación.

Buscamos que una IA pueda asistirnos en este proceso.

## ¿Qué?

Estamos considerando un prompt que busca la capacidad de la IA para procesar una transcripción de un discurso. La intención es que, después de recibir la transcripción, la IA pueda brindar un resumen esquemático identificando los puntos clave.

## ¿Para qué?

| | |
|-|-|
Objetivo|Transformar un discurso largo y posiblemente complejo en un resumen conciso y estructurado que destaque las ideas centrales.
Beneficio|Facilita la comprensión rápida de contenidos extensos, ahorrando tiempo y esfuerzo en la digestión de la información.<br><br>Esta síntesis puede ser esencial para profesionales, investigadores, periodistas, y cualquier persona que requiera entender rápidamente el núcleo de un discurso.

## ¿Cómo?

| | |
|-|-|
Conversión de Audio a Texto|Antes de interactuar con la IA, se utiliza una herramienta para convertir el discurso grabado en audio a texto. [Hay una buena cantidad de herramientas que actualmente permiten esto](https://www.google.com/search?q=online+speech+to+text+as+a+service).
Interacción con la IA|Se introduce el prompt a la IA, pegando la transcripción del discurso en el lugar indicado.
Procesamiento|La IA analiza el contenido de la transcripción para identificar las ideas centrales y puntos clave.
Obtención de Resultados|La IA devuelve un resumen esquemático del discurso basado en su análisis.

### Transcripciones
<!-- TODO #7 En las interacciones que incluyen varios pasos, considerar el incluir una tabla con una comparativa de como fueron comportándose los motores -->

|Motor|Comentario|
|-|-|
[ChatGPT](https://chat.openai.com/share/417e6c5b-5cf4-406b-b3a0-9c63a8ef3cf2)
[Perplexity](https://www.perplexity.ai/search/82dd1b33-948f-40f0-9f75-2f021e2e0dc1?s=c)|Hubo que dividir el discurso en tres partes
[Claude](https://claude.ai/chat/a5a567a8-0d81-423e-bf8f-13f75faa6c05)|Adelanta opinión
[Bard](https://g.co/bard/share/a59606402338)|Adelanta opinión
[NeuroFlash](https://app.neuro-flash.com/ai-writer/a2cf5f861a3fd51eb7d166d92ce5653f/preview)|Adelanta opinión

|Buenas prácticas|& Reflexiones
|-|-|
Instrucciones Claras|Se especifica claramente lo que se quiere obtener: un "resumen esquemático" y los "puntos clave".
Contextualización|Se le brinda a la IA un contexto claro sobre el contenido al mencionar que es un "discurso de apertura y presentación de unas jornadas dedicadas a inteligencia artificial y chatgpt".
Espacio para Input|Se deja un espacio claro ("AQUI LA TRANSCRIPCION DEL DISCURSO") para que el usuario introduzca la transcripción del discurso.

#### Antipatrón

*[:link:](https://chat.openai.com/share/f0bf24ea-3fd0-46e9-8479-c519318a282e) Revisa lo que sigue y dime qué piensas: [TEXTO]*

|Punto|Detalle|
|-|-|
Ambigüedad|No está claro qué se espera de la IA con "dime qué piensas". ¿Un resumen? ¿Una opinión? ¿Una corrección? La falta de claridad puede llevar a resultados no deseados.
Falta de contexto|La frase "AQUI PEGO ALGO" es demasiado vaga. Si bien en el prompt original se especificaba que se pegaría una "transcripción de un discurso", aquí no hay información sobre la naturaleza del contenido. Esto puede afectar la calidad y relevancia de la respuesta.
Instrucciones no detalladas|En el prompt original se solicitaba un "resumen esquemático" y se proporcionaba contexto sobre el discurso. En este antipatrón, las instrucciones son demasiado generales, lo que puede dar lugar a interpretaciones erróneas o respuestas inesperadas.

Estos elementos del antipatrón ilustran cómo la falta de claridad y especificidad en un prompt puede afectar la eficacia de la respuesta de una IA. Por lo tanto, incluso en los escenarios más "básicos", es crucial ser consciente de estos potenciales escollos.
