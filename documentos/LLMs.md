<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# LLMs

| | | |
|-|-|-|
Inteligencia artificial (AI por sus siglas en inglés)|Término general que se refiere a un sistema informático que es capaz de sentir, razonar o actuar como un humano.|[Legg, A Collection of Definitions of Intelligence](https://www.researchgate.net/publication/1895883_A_Collection_of_Definitions_of_Intelligence)
Aprendizaje automático (ML por sus siglas en inglés)|Rama de la IA que utiliza algoritmos para aprender a partir de datos, identificar patrones y hacer predicciones o decisiones sin ser explícitamente programado.|[Google, “AI vs. Machine Learning: How Do They Differ?”](https://cloud.google.com/learn/artificial-intelligence-vs-machine-learning?hl=es)
**Modelo de lenguaje de gran escala (LLMs por sus siglas en inglés)**|Modelos avanzados de aprendizaje automático diseñados para procesar y generar texto, entrenados en grandes cantidades de datos textuales de modo que son capaces de entender y producir lenguaje similar al humano.|<big>*Autocompletar*</big>

> Las herramientas construidas en torno a los LLMs, como ChatGPT, Claude, Gemini, etc. son una aplicación cada vez más importante del aprendizaje automático. Los LLMs generan *nuevo contenido*, convirtiéndolos en una forma de "IA generativa".

## Cronología

|![](/documentos/imagenes/timelineLLMs.png)|![](/documentos/imagenes/timelineChatGPT.png)|
|-|-|

- Pero ya un año antes (el 2018) [Google presentaba esto!!!](https://www.youtube.com/watch?v=l9BTMWOupGM)

## ¿Qué?

### Componentes principales

<div align=center>

|![](/documentos/imagenes/modelosUML/componentes.svg)|
|-|

</div>

|Datos|Algoritmo|Aplicación|
|-|-|-|
Los datos son la base de cualquier solución de inteligencia artificial. Los sistemas de IA aprenden y hacen predicciones a partir de los datos.|El algoritmo de IA es la lógica o las reglas que la máquina sigue para aprender de los datos y tomar decisiones. |La aplicación es el medio a través del cual los usuarios interactúan con la inteligencia artificial. 
Esto puede incluir datos estructurados (como bases de datos) y datos no estructurados (como texto, imágenes, audio, etc.). En el aprendizaje supervisado, los datos de entrenamiento son etiquetados para que la IA pueda aprender de ellos. En el aprendizaje no supervisado, los datos no están etiquetados y la IA intenta encontrar patrones y relaciones en los datos por sí misma.|Existen diferentes tipos de algoritmos de IA, incluyendo algoritmos de aprendizaje supervisado, aprendizaje no supervisado, aprendizaje por refuerzo, entre otros. Los algoritmos procesan los datos de entrada, extraen patrones y aprenden de ellos para hacer predicciones o tomar decisiones.|Esto puede tomar la forma de una interfaz de usuario en una página web, una aplicación móvil, un chatbot, un asistente virtual, un software de análisis de datos, entre otros. La aplicación toma las entradas del usuario, las procesa a través del algoritmo de IA utilizando los datos disponibles, y luego presenta los resultados al usuario.

### Componentes "*secundarios*"

|Componente|Descripción
|-|-|
Infraestructura de computación|Los sistemas de IA a menudo requieren una cantidad significativa de recursos de computación para entrenar y ejecutar los algoritmos, lo que puede implicar el uso de hardware especializado, como unidades de procesamiento de gráficos (GPU), o servicios de computación en la nube.
Preprocesamiento y limpieza de datos|Los datos que alimentan los algoritmos de IA a menudo necesitan ser limpiados y preprocesados antes de ser utilizados, lo cual puede implicar la eliminación de errores, la normalización de formatos de datos, la imputación de valores faltantes, entre otros.
**Seguridad y privacidad**|Los sistemas de IA deben ser diseñados y operados de manera que protejan la privacidad y seguridad de los datos, cumpliendo con todas las leyes y regulaciones aplicables.
[**Ética y sesgo**](etica@AI.md)|Los sistemas de IA pueden ser susceptibles a sesgos, dependiendo de los datos con los que son entrenados. Por lo tanto, es crucial considerar cuestiones de equidad, transparencia y rendición de cuentas en el diseño y la implementación de estos sistemas.

## ¿Para qué?

<div align=center>

|![](/documentos/imagenes/modelosUML/componentes2.svg)|
|:-:|
<big>[**PANORÁMICA**](Panoramica.md)</big>

</div>

### La app

<div align=center>

![](/documentos/imagenes/modelosUML/plataformaServicioHerramienta.svg)

||Herramienta|Servicio|Plataforma|
|-|-|-|-|
|**Def.:**|Recurso o aplicación diseñada para realizar una función o conjunto de funciones específicas, generalmente con un enfoque más limitado que una plataforma. Las herramientas pueden ser parte de una plataforma o estar disponibles de manera independiente.|Solución ofrecida a través de internet que permite a los usuarios acceder a funcionalidades específicas o realizar tareas concretas sin necesidad de instalar o mantener software adicional.|Conjunto de herramientas y servicios interconectados, diseñado para facilitar y gestionar una amplia gama de actividades y procesos específicos de una o varias áreas de trabajo.
|**Ej.:**|Un editor de imágenes en línea que permite modificar fotos a través del navegador.|Un servicio de almacenamiento en la nube que permite a los usuarios guardar, compartir y acceder a archivos desde cualquier lugar.|Una plataforma de desarrollo de software que integra herramientas de codificación, pruebas y despliegue.

</div>

## ¿Cómo?

- [Prompts](prompts/README.md)



## Bibliografía

- Cronología de los LLMs existentes en los últimos años - [A survey of large language models](https://arxiv.org/pdf/2303.18223v12.pdf)
- Evolución técnica de GPT - [A survey of large language models](https://arxiv.org/pdf/2303.18223v12.pdf)
