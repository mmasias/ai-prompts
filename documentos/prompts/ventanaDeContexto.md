<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Ventana de contexto

## ¿Por qué?

Los modelos de lenguaje de gran escala no tienen una "memoria" en el sentido tradicional, es decir que no almacenan información de conversaciones pasadas o de instrucciones previas. Por lo tanto, la ventana de contexto es la única "vista" que el modelo tiene sobre la conversación en curso.

## ¿Qué?

La "Ventana de contexto" es un fragmento de texto que incluye las interacciones más recientes en una conversación con el modelo. Este fragmento es lo que el modelo utiliza para generar respuestas. 

<div align=center>
  
|Contexto|***PROMPT***|Respuesta|
|-|-|-|

</div>

En el caso de GPT-3 y GPT-4, [la ventana de contexto tiene un límite](https://platform.openai.com/docs/models/gpt-3-5) medido en [tokens](tokens.md), que son las unidades básicas de texto que el modelo puede entender.

<div align=center>

||Ventana de contexto<br>(*en tokens*)|
|-|:-:|
GPT-3|2049
GPT-3.5|4096
GPT-4| 8192<br>*32768 (?)*

</div>

Si una conversación supera este límite, se deben eliminar partes del texto para que quepa en la ventana de contexto.

### Tokens vs palabras

|Tokens vs palabras|
|-|
[@ChatGPT4](https://chat.openai.com/share/52db2723-48e5-49f1-a734-67b721920bf1)
[@ChatGPT3.5](https://chat.openai.com/share/b10b28f2-2b4c-4ccc-abe8-dd130e4b6990)
[@Copilot](https://sl.bing.net/oiXW58tqDY)

Los modelos de lenguaje no "ven" palabras, sino tokens.

|Frase|Frase tokenizada|
|-|-|
|Learning new things is fun!|Learning / new / things / is / fun / !|
|Prompting is a new powerful developer tool.|Prom / pt / ing / is / a / new / powerful / developer / tool / .|
|lollipop|l / oll / ipop|

Para el idioma inglés, 1 token es alrededor de 4 caracteres

> [Hablando de tokens](tokens.md)

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

- [Trabajar con documentos](/documentos/casosDeUso/examenTipoTest.md), una forma de "mitigar" el problema con la ventana de contexto

> ***Actualización:*** [Copilot ahora mantiene el contexto](https://copilot.microsoft.com/chats/FZif3PHfxRXSym3crGjsy) y lo [hace sorprendentemente bien!](https://drive.google.com/drive/folders/15NpyxP458Ct5b0pGa5f2Rx_6WEBHUmvP?usp=drive_link)

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[¿Qué son los prompts?](README.md)<br>Conceptos básicos|Fundamentos > Prompts > **Ventana de contexto**|[Tokens](tokens.md)<br>Unidades básicas de procesamiento
|[Modelos de lenguaje](../LLMs.md)<br>Funcionamiento de los LLMs||[Mejores prácticas](mejoresPracticas/README.md)<br>Optimización considerando limitaciones

<i>**Relacionado**: [Repaso conversaciones](mejoresPracticas/repasoDeVezEnCuando.md) - Gestión práctica de límites / [Resumen recursivo](mejoresPracticas/resumenDeResumen.md) - Técnica para documentos extensos / [Casos de uso](../casosDeUso/README.md) - Aplicaciones que consideran limitaciones</i>

</div>