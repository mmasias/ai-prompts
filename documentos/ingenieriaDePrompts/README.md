<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

<div align=right><font size=-2>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Prompts](../prompts/README.md)<br>Fundamentos de prompts necesarios|Metodología > **Ingeniería de Prompts** (Introducción)|[Chain of Thought](chainOfThought.md)<br>Técnica de razonamiento paso a paso
|[Anatomía de prompts](../prompts/anatomia.md)<br>Comprende componentes y estructura||[0-Shot Prompting](0ShotPrompting.md)<br>Generalización sin ejemplos
|||[x-Shot Prompting](xShotPrompting.md)<br>Aprendizaje con ejemplos

<i>**Relacionado**: [Patrones](patrones/README.md) - Aplicaciones estructuradas / [Mejores prácticas](../prompts/mejoresPracticas/README.md) - Principios fundamentales / [Casos de uso](../casosDeUso/README.md) - Implementaciones prácticas</i>

</font></div>

# Ingeniería de Prompts

## ¿Por qué?

- Porque hay que comunicarnos
- Necesidad de mejor comunicación con los sistemas de AI.
- Preparar el input adecuado para obtener mejores outputs.

|Ingeniería de Prompts|
|-|
La Ingeniería de Prompts se utiliza para optimizar la forma en que interactuamos con los modelos de lenguaje como GPT-3 o GPT-4. Aunque estos modelos son increíblemente potentes, no siempre entregan los resultados esperados debido a su entrenamiento generalizado. Por ello, aprender a diseñar "prompts" efectivos puede ayudar a obtener respuestas más útiles y específicas.

## ¿Qué?

||
|-|
***La Ingeniería de Prompts se refiere a la técnica de diseñar y formular preguntas o comandos (prompts) de manera eficiente para guiar a un modelo de lenguaje a entregar la respuesta deseada. Esto puede involucrar la experimentación con diferentes formas de formular una pregunta, agregar más contexto o especificar el formato de la respuesta deseada.***

Un ingeniero de prompts es un profesional especializado en diseñar, optimizar y perfeccionar indicaciones o entradas para sistemas de IA, especialmente modelos generativos, para obtener respuestas precisas, relevantes y deseadas. 

Los ingenieros de prompts poseen un profundo conocimiento de los modelos de IA, sus limitaciones y las estrategias necesarias para optimizar su rendimiento. Al diseñar y perfeccionar cuidadosamente las indicaciones, cubren la brecha entre los sistemas de IA y los usuarios humanos, permitiendo una interacción fluida y mejorando la efectividad general de las aplicaciones impulsadas por IA en diversos campos e industrias.

Los ingenieros de prompts resuelven el problema de guiar de manera efectiva a los sistemas de IA, especialmente los modelos generativos, para que produzcan respuestas precisas, relevantes y apropiadas al contexto. Al diseñar y perfeccionar las indicaciones y las estructuras de entrada, los ingenieros de prompts optimizan la comunicación entre los seres humanos y los sistemas de IA, asegurando que estos sistemas generen salidas deseadas minimizando errores y consecuencias no deseadas. Desempeñan un papel crucial en hacer que los sistemas de IA sean más útiles, eficientes y fáciles de usar en diversos ámbitos y aplicaciones.

## ¿Para qué?

***La Ingeniería de Prompts es útil para extraer el máximo valor de los modelos de lenguaje. Puede permitirnos obtener respuestas más precisas, generar texto más relevante, mejorar la coherencia de las respuestas y reducir la cantidad de información incorrecta o inútil. Esto es especialmente importante en aplicaciones como los chatbots, donde se necesita una interacción eficiente y precisa.***

|Por un tema de|¿Para qué?|
|-|-|
Rendimiento|Los ingenieros de prompts ayudan a las empresas a obtener resultados óptimos de los sistemas de IA al diseñar indicaciones efectivas y refinar las estructuras de entrada. Esto asegura que los sistemas de IA generen respuestas relevantes, precisas y apropiadas al contexto para diversas aplicaciones.
Experiencia de usuario|Los ingenieros de prompts colaboran con diseñadores de UX/UI para integrar los componentes de IA de manera fluida en aplicaciones y servicios, garantizando una experiencia de usuario suave e intuitiva que cumpla con las expectativas del cliente.
Eficiencia|Al crear y mantener bibliotecas de prompts, los ingenieros de prompts permiten a las empresas aprovechar indicaciones preexistentes y optimizadas, ahorrando tiempo y esfuerzo en crear nuevas indicaciones desde cero y aumentando la eficiencia de las soluciones impulsadas por IA.
Nuevos modelos de IA|Los ingenieros de prompts se mantienen actualizados sobre los últimos avances en modelos de IA y modelos de lenguaje, asegurando que las aplicaciones impulsadas por IA de la empresa sigan siendo competitivas y efectivas, incluso a medida que surgen nuevas tecnologías.
Seguridad|Los ingenieros de prompts contribuyen a la seguridad y la integridad de los sistemas de IA al manejar indicaciones potencialmente maliciosas o perjudiciales, implementar validaciones de entrada y desarrollar planes de respuesta para incidentes de seguridad.
Mejora continua|Los ingenieros de prompts monitorean el rendimiento del sistema de IA, los comentarios de los usuarios y las tendencias de la industria, realizando los ajustes y actualizaciones necesarias en las indicaciones y los componentes de IA para garantizar una mejora continua y adaptación a los cambiantes requisitos de los usuarios y los objetivos empresariales.
Aplicaciones interdisciplinares|Los ingenieros de prompts pueden aplicar su experiencia en diversas industrias y áreas, como medicina, finanzas, educación, derecho, marketing y diseño, lo que permite a las empresas implementar soluciones de IA en áreas diversas y aprovechar nuevas oportunidades.


### Individual

|Por un tema de|¿Para qué?|
|-|-|
Mejorar la productividad
Ser más creativo
Mejorar la eficiencia en la resolución de problemas
Ganar en adaptabilidad y versatilidad
Aprender una habilidad que en un futuro será considerada básica

## ¿Cómo?

- Con lo que ya sabemos de [Prompts](/documentos/prompts/README.md)
- [Técnicas y conceptos](tecnicasResumen.md)
  - [Prompt sin entrenamiento previo](0ShotPrompting.md)
  - [x-Shot prompting](xShotPrompting.md)
  - [Cadena de pensamiento (CoT)](chainOfThought.md)
  - [Priming](priming.md)
  - [Árbol de pensamiento](arbolPensamiento.md)

## Bibliografía

| | |
|-|-|
[OpenAI](https://openai.com/) / [❓](https://help.openai.com/en/)|
[Prompt engineering institute](https://www.promptengineering.org/)|
