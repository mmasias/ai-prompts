<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/prompts/README.md)|[Ingeniería de Prompts](/ingenieriaDePrompts/README.md)|[Patrones](/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Ventana de contexto

## ¿Por qué?

Los modelos de lenguaje de gran escala no tienen una "memoria" en el sentido tradicional, es decir que no almacenan información de conversaciones pasadas o de instrucciones previas. Por lo tanto, la ventana de contexto es la única "vista" que el modelo tiene sobre la conversación en curso.

## ¿Qué?

La "Ventana de contexto" es un fragmento de texto que incluye las interacciones más recientes en una conversación con el modelo. Este fragmento es lo que el modelo utiliza para generar respuestas. 

En el caso de GPT-3 y GPT-4, [la ventana de contexto tiene un límite de tokens](https://platform.openai.com/docs/models/gpt-3-5), que son las unidades básicas de texto que el modelo puede entender.

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
|-|:-:|:-:|:-:|
Páginas de texto en Word<br>*(con tamaño de fuente estándar y márgenes normales)*|8-10|16-20|65-80
Palabras|3500-4000|7000-8000|28000-32000
Tweets<br>*considerando que un tweet tiene un límite de 280 caracteres*|15-20|30-40|120-160
[📁](https://drive.google.com/drive/folders/1sHecgUKJyLfwhFBehn15R5bIXQTJ_sgs?usp=sharing) ***Pruebas de stress***|[😵](https://chat.openai.com/share/6a42b7fd-59b4-475c-a818-af69c0fc5c61) <br/> [😵😵](https://chat.openai.com/share/e43be7f4-3e87-4ddd-800d-7606996eb203) <br/> [😵😵😵](https://chat.openai.com/share/4396fda0-fe7f-43fc-8a43-28dc9e9d7d21) <br/> [😵😵😵😵](https://chat.openai.com/share/35492bb2-4252-4ab3-880c-b8792386ac51)|[😵](https://chat.openai.com/share/b5fbcb0a-f57e-472f-99c6-8b831fbfb870)<br><br><br>[😵😵😵😵](https://chat.openai.com/share/88efa50b-4c05-40b0-9c83-da7d6f477650)
|||¿*consciente* de limitaciones?
