# Panorámica

| | | |
|-|-|-|
Inteligencia artificial (AI por sus siglas en inglés)|Término general que se refiere a un sistema informático que es capaz de sentir, razonar o actuar como un humano.|[Legg, A Collection of Definitions of Intelligence](https://www.researchgate.net/publication/1895883_A_Collection_of_Definitions_of_Intelligence)
Aprendizaje automático (ML por sus siglas en inglés)|Rama de la IA que utiliza algoritmos para aprender a partir de datos, identificar patrones y hacer predicciones o decisiones sin ser explícitamente programado.|[Google, “AI vs. Machine Learning: How Do They Differ?”](https://cloud.google.com/learn/artificial-intelligence-vs-machine-learning?hl=es)
**Modelo de lenguaje de gran escala (LLMs por sus siglas en inglés)**|Modelos avanzados de aprendizaje automático diseñados para procesar y generar texto, entrenados en grandes cantidades de datos textuales de modo que son capaces de entender y producir lenguaje similar al humano.|*Autocompletar*

> Las herramientas construidas en torno a los LLMs, como ChatGPT, Claude, Bard, etc. son una aplicación cada vez más importante del aprendizaje automático. Los LLMs generan *nuevo contenido*, convirtiéndolos en una forma de "IA generativa".

## Qué

<div align=center>

![](/imagenes/modelosUML/componentes.svg)

</div>

### Componentes principales

|Datos|Algoritmo|Aplicación|
|-|-|-|
Los datos son la base de cualquier solución de inteligencia artificial. Los sistemas de IA aprenden y hacen predicciones a partir de los datos. Esto puede incluir datos estructurados (como bases de datos) y datos no estructurados (como texto, imágenes, audio, etc.). En el aprendizaje supervisado, los datos de entrenamiento son etiquetados para que la IA pueda aprender de ellos. En el aprendizaje no supervisado, los datos no están etiquetados y la IA intenta encontrar patrones y relaciones en los datos por sí misma.|El algoritmo de IA es la lógica o las reglas que la máquina sigue para aprender de los datos y tomar decisiones. Existen diferentes tipos de algoritmos de IA, incluyendo algoritmos de aprendizaje supervisado, aprendizaje no supervisado, aprendizaje por refuerzo, entre otros. Los algoritmos procesan los datos de entrada, extraen patrones y aprenden de ellos para hacer predicciones o tomar decisiones.|La aplicación es el medio a través del cual los usuarios interactúan con la inteligencia artificial. Esto puede tomar la forma de una interfaz de usuario en una página web, una aplicación móvil, un chatbot, un asistente virtual, un software de análisis de datos, entre otros. La aplicación toma las entradas del usuario, las procesa a través del algoritmo de IA utilizando los datos disponibles, y luego presenta los resultados al usuario.

### Componentes "secundarios"

|Componente|Descripción
|-|-|
Infraestructura de computación|Los sistemas de IA a menudo requieren una cantidad significativa de recursos de computación para entrenar y ejecutar los algoritmos, lo que puede implicar el uso de hardware especializado, como unidades de procesamiento de gráficos (GPU), o servicios de computación en la nube.
Preprocesamiento y limpieza de datos|Los datos que alimentan los algoritmos de IA a menudo necesitan ser limpiados y preprocesados antes de ser utilizados, lo cual puede implicar la eliminación de errores, la normalización de formatos de datos, la imputación de valores faltantes, entre otros.
Seguridad y privacidad|Los sistemas de IA deben ser diseñados y operados de manera que protejan la privacidad y seguridad de los datos, cumpliendo con todas las leyes y regulaciones aplicables.
[Ética y sesgo](etica@AI.md)|Los sistemas de IA pueden ser susceptibles a sesgos, dependiendo de los datos con los que son entrenados. Por lo tanto, es crucial considerar cuestiones de equidad, transparencia y rendición de cuentas en el diseño y la implementación de estos sistemas.

## ¿Para qué?

### Horizontales
<!-- TODO #6 incluir las siguientes: Rask.ai
Captions
Wonder dinamic
24ai
Runway -->
#### Generar texto

- [ChatGPT](https://chat.openai.com/)
- [Bard](https://bard.google.com/)
- [Perplexity](https://www.perplexity.ai/)
- [Claude](https://claude.ai/chats)
- Ernie

#### Generar imágenes

- [Dall-e](https://pitch.com/v/DALL-E-prompt-book-v1-tmd33y/d959fd01-3eea-4b16-9472-e79ccb635e98)
- [MidJourney](https://docs.midjourney.com/docs/prompts)
- Stable Diffussion
- BlueWillow
- [VisualChatGPT](https://stablediffusionweb.com/Visual-ChatGPT#demo)
- Ideogramas: [Ideogram.ai](https://ideogram.ai/)


#### Generar música

- [Mubert](https://mubert.com/)

#### Generar vídeo

- XYZw <!-- TODO: #10 Prompt to Video -- >

#### Verticales

- Atención telefónica: [Jano](https://www.youtube.com/watch?v=fhoKnB6vwWg)
- Salud [Glass AI](https://glass.health/ai)
- Música & Composición [Moises](https://moises.ai/)
- Papers académicos [SCISPACE](https://typeset.io/)
- [Modelos 3D a partir de fotografías](https://research.nvidia.com/labs/dir/neuralangelo/)
- [Resumir vídeos de youtube](https://eightify.app/)
- [Creación de presentaciones](https://gamma.app/generate) - [Presentación creada con Gamma](https://gamma.app/public/Introduccion-a-la-IA-y-su-estado-actual-s2pfcebzfn8j7xt)
- [Human generator](https://generated.photos/human-generator)
- [Microsoft Designet](https://designer.microsoft.com/)
- [Durable, generador de sitios web](https://durable.co/)

#### Integraciones

 - https://app.integrately.com/
 - https://zapier.com/

#### Plugins

 - [GMail](https://www.aimails.dev/)
## ¿Cómo?

[Prompts](/prompts/README.md)
