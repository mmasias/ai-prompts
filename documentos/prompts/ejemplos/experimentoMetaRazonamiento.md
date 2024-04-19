<div align=right>

||[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Experimento: meta-razonamiento

## ¿Por qué?

En el proceso de solución de problemas y toma de decisiones, tanto en contextos académicos como profesionales, a menudo nos enfrentamos a tareas complejas que requieren una consideración cuidadosa y un enfoque estructurado para resolverlas eficazmente.

## ¿Qué?

Dado que nos apoyamos en un LLM para esto, resultará interesante ver los pasos que sigue el LLM en su método "estructurado" para abordar las tareas que se le piden.

## ¿Para qué?

Sabiendo que el modelo realiza varios pasos y un mecanismo basado en la interacción con el usuario, se busca el hacer emerger estos pasos, comenzando con la identificación y comprensión del problema, seguido del análisis y la consideración de las implicaciones y culminando con las medidas concretas para avanzar hacia una solución. 

Los grados de libertad del proceso permiten incluir un componente iterativo (Reaccionar), donde se evalúa la necesidad de continuar el proceso basándose en los resultados obtenidos y la retroalimentación del usuario.

## ¿Cómo?

```
A continuación, se presenta un conjunto de instrucciones que te voy a pedir que sigas:

<Instrucciones>

<Proceso>

Define los pasos como:
    - Orientar: identificar la tarea
    - Pensar: pensar paso a paso sobre la tarea. Identificar ambigüedades o consecuencias lógicas en el enunciado del problema que impacten tu respuesta a la tarea.
    - Acción: actuar para avanzar en la tarea. 

Tus actos disponibles son:

    i. Describir los pasos: (colocando la descripción de orientar, pensar y acción dentro de [PENSANDO] ... [/PENSANDO])
    ii. Responder: si la respuesta está disponible, responde con la respuesta (colocando la respuesta dentro de [RESPUESTA] ... [/RESPUESTA]) y luego responde STOP
    iii. Lógica: usar un hecho conocido o razonamiento lógico basado en un hecho conocido para expandir el pensamiento, luego responde con el razonamiento (colocando la respuesta dentro de [RESPUESTA_LOGICA] ... [/RESPUESTA_LOGICA]).
    iv. Preguntar: hacer una pregunta al usuario para aclarar la tarea. Mostrar: pregunta (colocando la pregunta dentro de [RESPUESTA_PREGUNTA] ... [/RESPUESTA_PREGUNTA])., Mostrar: STOP

Observación: revisar o refinar la tarea dada el pensamiento y los resultados de la acción

</Proceso>

Define Reaccionar como:
    Por cada paso Proceso: realizar el paso
    Preguntar al Usuario '¿deberíamos continuar?'
    Mostrar STOP

El asistente mostrará de manera concisa todos los orientar, pensar, acción y observación

El asistente seguirá las instrucciones del Proceso para responder a todas las preguntas y tareas.

</Instrucciones>
```
