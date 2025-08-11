# Diversos test (i)lógicos para LLMs

## ¿Por qué?

Los modelos de lenguaje presentan capacidades impresionantes en tareas complejas, pero curiosamente fallan en problemas aparentemente simples. Esta situación crea expectativas irreales sobre las capacidades de los LLMs. Los usuarios pueden asumir que si un modelo maneja tareas avanzadas, también debería ser confiable en problemas básicos, lo que lleva a una falsa sensación de seguridad y decisiones incorrectas cuando se depende de estos sistemas para tareas críticas.

Además, la evaluación tradicional de LLMs se centra en benchmarks académicos complejos, dejando sin examinar habilidades fundamentales como el razonamiento lógico básico, la comprensión de relaciones espaciales simples, o la aritmética elemental. Esta brecha de evaluación impide comprender las limitaciones reales de estos sistemas.

## ¿Qué?

|||
|-|-|
|Un conjunto de tests diseñados para revelar las limitaciones específicas de los LLMs en tareas que cualquier humano resolvería intuitivamente. Estos tests se enfocan en habilidades básicas como comprensión de relaciones familiares, razonamiento lógico elemental, manipulación numérica simple y comprensión contextual.|Los tests están estructurados para ser inequívocos en sus respuestas correctas, eliminando la subjetividad en la evaluación. Se diseñan específicamente para exponer patrones de error comunes en modelos de lenguaje como la confusión en el conteo, la dificultad para mantener coherencia en relaciones bidireccionales y (de momento) la tendencia a sobrecomplicar problemas simples.

## ¿Para qué?

El propósito de esta batería de tests es revisar las capacidades de diferentes modelos de lenguaje de modo que se puedan identificar fortalezas y debilidades específicas de cada sistema, facilitando decisiones informadas sobre cuándo y cómo usar cada herramienta.

## ¿Cómo?

|||
|-|-|
|1|En una habitación hay 3 hermanas: Anna está leyendo un libro. Alice está jugando una partida de ajedrez. ¿Qué está haciendo la tercera persona (llamada Amanda)?
|2|En una habitación tengo 3 hermanas y nadie más. Anna está leyendo un libro. Alice está jugando una partida de ajedrez con alguien en la habitación. ¿Qué está haciendo la tercera persona (llamada Amanda) y qué relación tiene conmigo?
|3|En una habitación estamos solo 3 hermanas: Anna está leyendo un libro. Alice está jugando una partida de ajedrez. ¿Qué está haciendo la tercera persona (llamada Amanda) y qué relación tiene conmigo?
|4|SACO es a ASCO lo que 7683 es a...
|5|Escríbeme una frase que no contenga ninguna palabra que aparezca en "El Quijote"
|6|Anita tiene dos hermanos. Cada hermano tiene dos hermanas. ¿Cuántas hermanas tiene Anita?
|7|La cafetería tiene 23 manzanas. Si usaron 20 para preparar un postre y compraron 6 más, ¿cuántas manzanas tienen ahora?
|8|Albert y Bernard acaban de hacerse amigos de Cheryl y quieren saber cuándo es su cumpleaños. Cheryl les da una lista de 10 fechas posibles: 15 de mayo, 16 de mayo, 19 de mayo, 17 de junio, 18 de junio, 14 de julio, 16 de julio, 14 de agosto, 15 de agosto, 17 de agosto.<br><br>Luego Cheryl les dice a Albert y a Bernard por separado el mes y el día de su cumpleaños, respectivamente.<br><br>- Albert: No sé cuándo es el cumpleaños de Cheryl, pero sé que Bernard tampoco lo sabe.<br>- Bernard: Al principio no sabía cuándo es el cumpleaños de Cheryl, pero ahora sí lo sé.<br>- Albert: Entonces yo también ya sé cuándo es el cumpleaños de Cheryl.
|9|Alicia tiene 3 hermanos y también tiene 6 hermanas. ¿Cuántas hermanas tienen los hermanos de Alicia? (*respuesta correcta: 7*)
|10|Alicia tiene 2 hermanas y también tiene 4 hermanos. ¿Cuántas hermanas tienen los hermanos de Alicia? (*respuesta correcta: 3*)
|11|Alicia tiene 4 hermanos y también tiene 1 hermana. ¿Cuántas hermanas tienen los hermanos de Alicia? (*respuesta correcta: 2*)
|12|La mamá de Sarah tiene cinco hijos. John y Michael son gemelos, María y Carol nacieron con 2 años de diferencia. María es la mayor. Michael es el menor. John es dos años más joven que Carol. El quinto hijo es un año mayor que Carol. Los gemelos nacieron en el 2000. ¿Cuáles son los nombres de los cinco hijos ordenados por edad, y en qué año nació cada uno? (*respuesta correcta: María (1996), Sarah (1997), Carol (1998), John (2000), Michael (2000)*)
|13|9.11 > 9.9?
|14|¿Sumando cuáles de estos números: 2, 6, 12, 8, 20, 4, -6 puedes obtener como resultado 13? (*respuesta correcta: dado que todos los números son pares, es imposible obtener un número par como respuesta*)

|#| ChatGPT | Claude | Gemini | DeepSeek | Grok | MetaAI | Copilot | Perplexity | Mistral |
|-|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 1  | [L](https://chatgpt.com/share/6895e9cf-98f4-8002-bd8a-39de093981f6 "Ver respuesta de ChatGPT") |  |  |  |  |  |  |  |  |
| 2  |  |  |  |  |  |  |  |  |  |
| 3  |  |  |  |  |  |  |  |  |  |
| 4  | [L](https://chatgpt.com/share/6895eb1d-fdb8-8002-8d4a-fadc72e8cd2c "Ver respuesta de ChatGPT") | [L](https://claude.ai/share/23b3b47a-c492-43a8-9b43-711350017ee0 "Ver respuesta de Claude") | [L](https://g.co/gemini/share/5c83e8e8804f) |  | [L](https://grok.com/share/c2hhcmQtMw%3D%3D_9f262244-ce96-4c3e-bd28-9f7b5accf15f) |  | [L](https://copilot.microsoft.com/shares/6SzyBmySbFU7YKdz7X8gG) | [L](https://www.perplexity.ai/search/saco-es-a-asco-lo-que-7683-es-6uwt5.otQN2tlcAuCSk5KA) | [L](https://chat.mistral.ai/chat/0f3eed14-0753-4428-a626-9b9bdf48de38) |
| 5  | [L](https://chatgpt.com/share/6895ed07-62a4-8002-a426-d9a321eb7e5f "Ver respuesta de ChatGPT") | [L](https://claude.ai/share/7f966626-dfd8-4195-bd62-0e770dfd0ec7 "Ver respuesta de Claude") | [L](https://g.co/gemini/share/d088632db4ab) |  | [L](https://grok.com/share/c2hhcmQtMw%3D%3D_f0b2ca0f-efbc-4cb9-a95d-c2b6ee13d358) |  | [L](https://copilot.microsoft.com/shares/yeKdA8bBnGo4tza9P7Zd3) | [L](https://www.perplexity.ai/search/escribeme-una-frase-que-no-con-x16hT8BsTTK02pFMSH8ylw) | [L](https://chat.mistral.ai/chat/70052501-6210-4e2d-91d9-4087f5cbc7ea) |
| 6  |  |  |  |  |  |  |  |  |  |
| 7  |  |  |  |  |  |  |  |  |  |
| 8  |  |  |  |  |  |  |  |  |  |
| 9  |  |  |  |  |  |  |  |  |  |
| 10 | [L](https://chatgpt.com/share/6895ee0b-eba4-8002-b8a8-2a783390a0cb "Ver respuesta de ChatGPT") | [L](https://claude.ai/share/0c8f138a-1f37-4604-85ea-5aa7d1e77ca3 "Ver respuesta de Claude") |  |  |  |  |  |  |  |
| 11 |  |  |  |  |  |  |  |  |  |
| 12 | [L](https://chatgpt.com/share/6895ee7c-a3b4-8002-a106-6826338efc7d "Ver respuesta de ChatGPT") | [L](https://claude.ai/share/5b93964f-d27d-4cc9-ad5d-cef7503e70da "Ver respuesta de Claude") |  |  |  |  |  |  |  |
| 13 | [L](https://chatgpt.com/share/68963987-7114-8002-909d-8913642a7b03)                            | [L](https://claude.ai/share/b39bb008-ca55-42eb-bcaa-4e6630973bc0) |[L](https://g.co/gemini/share/d5477be9d837)||[L](https://grok.com/share/c2hhcmQtMw%3D%3D_59a5020b-d961-4cc9-8f2e-5c9b177d2dfb)||[L](https://copilot.microsoft.com/shares/cfYK7iZN2v5Braep4tiWX)|[L](https://www.perplexity.ai/search/9-11-9-9-AOtluA5ZRq2CZY30faYV5A)|[L](https://chat.mistral.ai/chat/0311caa7-64d0-44cf-80e8-f18f9461edae)
| 14 | [L](https://chatgpt.com/share/689a297e-2ff0-8002-95b1-61ec4174b721) | [L](https://claude.ai/share/581f8ba1-5110-4c3b-9ef8-ef79cb8cb5b7) | [L](https://g.co/gemini/share/1c2e33a9e348) |   | [L](https://grok.com/share/c2hhcmQtMw%3D%3D_2bbc58a7-57f3-4a2b-b986-5d2227bfbb91) |   | [L](https://copilot.microsoft.com/shares/U4cKhdVo3fNzUGXQQC6pw) | [L](https://www.perplexity.ai/search/sumando-cuales-de-estos-numero-itrZylXDS7CAVt83n.DU3Q) | [L](https://chat.mistral.ai/chat/ba68d271-5de4-4334-b9cd-4627e99fe6e6)

## Más

> [CdU](../ingenieriaDePrompts/arbolPensamiento.md)
