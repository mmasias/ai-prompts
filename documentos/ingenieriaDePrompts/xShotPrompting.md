<div align=right>

||[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# X-Shot prompting

## ¿Por qué?

X-shot prompting es utilizado debido a que los modelos de lenguaje de IA, aunque potentes, a veces necesitan ejemplos adicionales para comprender y responder correctamente a una solicitud de información específica. Esto es particularmente útil en casos en los que se necesitan respuestas más precisas o donde el dominio del conocimiento es más especializado.

## ¿Qué?

El término *x-shot* se refiere al número de ejemplos (donde "x" es el número) que se proporcionan al modelo para ayudarlo a entender el contexto o el tipo de respuesta que se busca. Estos ejemplos actúan como puntos de referencia para guiar al modelo.

### ¿Para qué?

Para ajustar la salida del modelo de IA y ayudarlo a generar respuestas más relevantes y precisas. 

### ¿Cómo?

|Transcripciones en crudo / 2DO: Convertirlas a QxQpQ&C
|-
[Jitanjáfora](/documentos/casosDeUso/aprendizajeJitanjafora.md)
[Estilo de escritura](https://chat.openai.com/share/584af1d9-e459-4fc3-b571-bf8a3c317d66)
[Acrónimos](/documentos/casosDeUso/acronimo.md)

#### Consejos

[Min et al. (2022)](https://arxiv.org/abs/2202.12837) nos proporciona algunos consejos para aplicar con esta técnica:

- El espacio de etiquetas y la distribución del texto de entrada especificado por los ejemplos son ambos importantes (independientemente de si las etiquetas son correctas para las entradas individuales)
- El formato que utilice también desempeña un papel clave en el rendimiento, incluso si solo usa etiquetas aleatorias, esto es mucho mejor que no tener etiquetas en absoluto.
- Los resultados adicionales muestran que seleccionar etiquetas aleatorias de una verdadera distribución de etiquetas (en lugar de una distribución uniforme) también ayuda.
