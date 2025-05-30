<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Ingeniería de Prompts

## ¿Por qué?

- Porque hay que comunicarnos
- Necesidad de mejor comunicación con los sistemas de AI.
- Preparar el input adecuado para obtener mejores outputs.

Los modelos de lenguaje modernos como Claude, GPT-4o, Gemini y otros sistemas avanzados de IA poseen capacidades extraordinarias para procesar y generar texto. Sin embargo, estas capacidades no se materializan automáticamente en resultados útiles. Se presenta una brecha fundamental entre lo que estos sistemas pueden hacer y lo que realmente producen cuando se les solicita información de manera general o ambigua.

Los modelos se entrenan con enormes cantidades de datos para ser generalistas, lo que significa que pueden responder a casi cualquier pregunta, pero frecuentemente entregan respuestas genéricas, imprecisas o que no se alinean con las necesidades específicas del usuario. Esta generalización, aunque poderosa, crea la necesidad de técnicas especializadas para extraer respuestas más precisas, contextuales y útiles.

Además, la comunicación humana es inherentemente ambigua. Las mismas palabras pueden tener múltiples interpretaciones según el contexto, y los usuarios frecuentemente asumen que los sistemas comprenden implícitamente sus intenciones. Esta ambiguidad bidireccional requiere de metodologías específicas para establecer comunicación efectiva.

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
|Especificidad|Adaptar las capacidades generales de los modelos a dominios especializados como medicina, finanzas, educación, desarrollo de software, y otras áreas que requieren conocimiento experto.
|Precisión|Reducir significativamente la ambigüedad en las respuestas, obteniendo información más específica y relevante para cada caso de uso particular.
|Eficiencia|Minimizar la necesidad de múltiples iteraciones y correcciones, ahorrando tiempo tanto en el desarrollo como en la implementación de soluciones basadas en IA.
|Coherencia|Establecer patrones consistentes de interacción que pueden replicarse y escalarse a través de diferentes aplicaciones y contextos.
|Experiencia de usuario|Crear interfaces más intuitivas y efectivas donde los usuarios obtienen exactamente lo que necesitan sin frustraciones o malentendidos.
|Acceso|Reducir la barrera técnica para aprovechar IA avanzada, permitiendo que profesionales de diferentes áreas puedan utilizar estas herramientas sin necesidad de conocimiento técnico profundo.

### Individual

|Por un tema de|¿Para qué?|
|-|-|
|Mejorar la productividad
|Ser más creativo
|Mejorar la eficiencia en la resolución de problemas
|Ganar en adaptabilidad y versatilidad
|Aprender una habilidad que en un futuro será considerada básica

## ¿Cómo?

La implementación de la Ingeniería de Prompts se realiza a través de múltiples técnicas y metodologías complementarias:

### Técnicas fundamentales

- [0-Shot Prompting](0ShotPrompting.md): Aprovecha las capacidades de generalización sin ejemplos previos
- [x-Shot Prompting](xShotPrompting.md): Utiliza ejemplos específicos para guiar el comportamiento del modelo
- [Chain of Thought](chainOfThought.md): Estructura el razonamiento paso a paso para problemas complejos
- [Priming](priming.md): Establece contexto inicial para orientar las respuestas

### Técnicas avanzadas

- [Árbol de pensamiento](arbolPensamiento.md): Explora múltiples caminos de razonamiento simultáneamente
- Técnicas multimodales: Integra texto, imágenes y otros tipos de datos
- Prompting adaptativo: Ajusta dinámicamente la estrategia según el contexto

### Principios de aplicación

- [Consideraciones básicas](consideraciones.md): Directrices fundamentales para el diseño efectivo
- [Mejores prácticas](../prompts/mejoresPracticas/README.md): Patrones probados y optimizados
- Evaluación continua: Métricas y métodos para medir la efectividad

### Aplicación práctica

- [Patrones reutilizables](patrones/README.md): Soluciones estructuradas para problemas comunes
- [Casos de uso](../casosDeUso/README.md): Ejemplos específicos de implementación
- [Técnicas integradas](tecnicasResumen.md): Combinación efectiva de múltiples enfoques

## Bibliografía

| | |
|-|-|
[OpenAI](https://openai.com/) / [❓](https://help.openai.com/en/)|
[Prompt engineering institute](https://www.promptengineering.org/)|

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Fundamentos de prompts](../prompts/README.md)<br>Comprende estructura y componentes básicos|Fundamentos > **Ingeniería de Prompts** (Metodología)|[Consideraciones](consideraciones.md)<br>Principios básicos de diseño
|[Ventana de contexto](../prompts/ventanaDeContexto.md)<br>Limitaciones técnicas fundamentales||[0-Shot Prompting](0ShotPrompting.md)<br>Técnica fundamental
|[Anatomía del prompt](../prompts/anatomia.md)<br>Estructura de componentes||[Casos de uso](../casosDeUso/README.md)<br>Aplicaciones prácticas

<i>**Relacionado**: [Mejores prácticas](../prompts/mejoresPracticas/README.md) - Aplicación inmediata / [Patrones](patrones/README.md) - Soluciones reutilizables / [Mitos](mitos.md) - Clarificación de conceptos erróneos</i>

</div>