<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

#  Caso de Uso > Ventana de contexto en LLMs

## ¿Por qué?

Comprender cómo la ventana de contexto cambia con la interacción e impacta en el rendimiento es crucial porque permite optimizar la precisión y eficiencia del modelo. 

## ¿Qué?

La ventana de contexto en un modelo de lenguaje se refiere al número de palabras o tokens que el modelo toma en cuenta desde el texto previo al generar la siguiente palabra. Los modelos de lenguaje, como GPT-4, utilizan esta ventana para analizar y entender el contexto en el cual se encuentra la palabra a predecir. La longitud de la ventana de contexto puede variar; por ejemplo, en modelos grandes, puede ser de cientos o miles de tokens.

## ¿Para qué?

Entender y experimentar con la ventana de contexto tiene múltiples aplicaciones prácticas:

1. **Optimización del rendimiento del modelo**: Permite ajustar el modelo para que procese de manera eficiente textos largos o cortos, dependiendo del caso de uso.
1. **Mejora en tareas específicas**: En traducción automática, un contexto más amplio puede mejorar la precisión de la traducción al entender mejor las frases idiomáticas y referencias.
1. **Reducción de recursos computacionales**: Ajustar la ventana de contexto puede ayudar a equilibrar entre precisión y uso de recursos, haciendo los modelos más eficientes.
1. **Desarrollo de aplicaciones avanzadas**: En generación de texto creativo, una ventana de contexto adecuada puede generar contenido más coherente y relevante.

## ¿Cómo?

Para comprobar y experimentar con el concepto de ventana de contexto en un modelo de lenguaje, podemos seguir estos pasos:

1. **Selección del modelo**: Escoger un modelo de lenguaje: Claude, Perplexity, Gemini, etc. (Por variar, se propone usar ChatGPT como segundo modelo)
1. **Diseño del experimento**:
   - Trabajar con el modelo de lenguaje la creación de un magazine compuesto por 7 u 8 artículos cada uno de 2000 palabras.
   - Ejecutar el experimento sobre uno o dos modelos de lenguaje. A medida que crece el documento, testear su precisión para absolver dudas. Puede seguir el guión propuesto en las trascripciones de ChatGPT.
1. **Análisis**:
   - Analizar cómo varían las respuestas del modelo a medida que crece la ventana de contexto.
   - Identificar la longitud óptima y fiable de valores de trabajo.
1. **Documentación y reporte**:
   - Entregar los enlaces de la interacción seguida con el modelo de lenguaje a través del CV.

### Transcripciones

|Motor|Comentario|
|-|-|
[ChatGPT](https://chatgpt.com/share/35492bb2-4252-4ab3-880c-b8792386ac51?oai-dm=1)
[Perplexity]
[Claude]
[Bard]
[NeuroFlash]
