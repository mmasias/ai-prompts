# Ventana de contexto

## ¿Por qué?

Los modelos de lenguaje de gran escala no tienen una "memoria" en el sentido tradicional, es decir que no almacenan información de conversaciones pasadas o de instrucciones previas. Por lo tanto, la ventana de contexto es la única "vista" que el modelo tiene sobre la conversación en curso.

## ¿Qué?

La "Ventana de contexto" es un fragmento de texto que incluye las interacciones más recientes en una conversación con el modelo. Este fragmento es lo que el modelo utiliza para generar respuestas. 

En el caso de GPT-3 y GPT-4, la ventana de contexto tiene un límite de tokens, que son las unidades básicas de texto que el modelo puede entender.

||Ventana de contexto (*en tokens*)|
|-|:-:|
GPT-3|2049
GPT-3.5|4096
GPT-4| 8192<br>*32768 (?)*

Si una conversación supera este límite, se deben eliminar partes del texto para que quepa en la ventana de contexto.

## ¿Para qué?

|||
|-|-|
Coherencia|Ayuda al modelo a mantener la coherencia en una conversación al tener en cuenta las interacciones previas.
Contextualización|Permite que el modelo entienda preguntas o declaraciones que requieren conocimiento de declaraciones previas.
Personalización Temporal|Aunque el modelo no tiene memoria persistente, la ventana de contexto permite una forma de "personalización" durante la duración de la conversación.

## ¿Cómo?

Cuando se interactúa con un modelo como ChatGPT, cada entrada (pregunta, comentario, etc.) se añade a la ventana de contexto existente junto con la respuesta del modelo. Este contexto acumulado se utiliza para generar respuestas a futuras entradas.

Si se alcanza el límite de tokens, se recorta el texto más antiguo para hacer espacio para la nueva interacción.

## ¿Cuánto?

Un token en GPT-3 o GPT-4 puede ser tan pequeño como un solo carácter o tan grande como una palabra completa. Por ejemplo, "ChatGPT es genial" se descompondría en algo como ["Chat", "G", "PT", " es", " genial"], lo que sumaría 5 tokens.

Entonces, los tokens mencionados anteriormente equivaldrían, aproximadamente a:

||4096<br>GPT-3.5|8192<br>GPT-4|32768<br>GPT-4|
|-|-|-|-|
Páginas de texto en Word<br>*(con tamaño de fuente estándar y márgenes normales)*|8-10|16-20|65-80
Palabras|3500-4000|7000-8000|28000-32000
Tweets<br>*considerando que un tweet tiene un límite de 280 caracteres*|15-20|30-40|120-160

