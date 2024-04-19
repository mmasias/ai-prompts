<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Técnicas de Ingenieria de Prompts

## ¿Por qué?

Surgen con el objetivo de controlar y mejorar la generación de texto, de modo que seamos capaces de abordar desafíos específicos en la interacción con modelos de lenguaje y responder a las necesidades de los usuarios.

## ¿Qué?

- **Priming**: Se refiere al inicio o primer mensaje en una interacción con el modelo.
- **Chain of Thought**: Se relaciona con mantener una conversación coherente a lo largo de varios mensajes.
- **X-shot Prompting**: Implica proporcionar ejemplos o "disparos" al modelo antes de cada solicitud.

## ¿Para qué?

- [X-shot Prompting](xShotPrompting.md)
  - Surge para mejorar la capacidad de controlar y orientar al modelo en respuestas específicas y precisas.
  - Proporciona ejemplos específicos antes de cada solicitud para garantizar que el modelo comprenda y responda de acuerdo con las expectativas del usuario.
  - Ayuda a mitigar posibles respuestas erróneas o indeseadas al proporcionar orientación detallada.
- [Chain of Thought (Cadena de Pensamiento)](chainOfThought.md)
  - Surge para abordar la necesidad de mantener la coherencia y el contexto a lo largo de conversaciones largas o secuencias de interacciones.
  - Proporciona una forma de recordar y construir sobre mensajes y respuestas anteriores, lo que permite diálogos más fluidos y contextualmente coherentes.
  - Se utiliza para que el modelo pueda recordar y responder de manera apropiada a lo largo de una conversación.
- [Priming](priming.md)
  - Surge para establecer un contexto inicial y dirigir la generación de texto en una dirección específica desde el comienzo de una interacción.
  - Permite a los usuarios influir en el tono, el estilo y el tema de la respuesta del modelo desde el primer mensaje.
  - Ayuda a iniciar conversaciones de manera coherente y a transmitir expectativas iniciales al modelo.

## ¿Cómo?

|Concepto|Semejanzas|Diferencias
|-|-|-|
**X-shot Prompting**|Implica proporcionar ejemplos o "disparos" al modelo antes de cada solicitud.|- Cada "disparo" ilustra lo que se espera en términos de respuesta.<br> - Ayuda a guiar al modelo en la generación de respuestas precisas.<br> - Puede utilizarse en interacciones individuales, no necesariamente en una conversación continua.
**Chain of Thought**|Se relaciona con mantener una conversación coherente a lo largo de varios mensajes.|- Se basa en mensajes y respuestas anteriores, acumulando contexto.<br> - Permite una conversación más fluida y contextualmente coherente.<br> - Es adecuado para conversaciones largas o continuas.
**Priming**|Se refiere al inicio o primer mensaje en una interacción con el modelo.|- Se enfoca en el contexto inicial y establece el tono y el tema de la conversación.<br> - Puede influir en la coherencia y el estilo de la respuesta del modelo.<br> - No implica una secuencia continua de mensajes.