<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Patrón Administrador de Contexto

## Intención y Contexto

La intención de este patrón es permitir a los usuarios especificar o eliminar el contexto de una conversación con un LLM. El objetivo es centrar la conversación en temas específicos o excluir temas no relacionados. Este patrón otorga a los usuarios un mayor control sobre qué declaraciones considera o ignora el LLM al generar una salida.

## Motivación

Los LLM a menudo tienen dificultades para interpretar el contexto previsto de la pregunta actual o generan respuestas irrelevantes basadas en entradas anteriores o atención irrelevante en las declaraciones incorrectas. Al enfocarse en declaraciones contextuales explícitas o eliminar declaraciones irrelevantes, los usuarios pueden ayudar al LLM a comprender mejor la pregunta y generar respuestas más precisas. Los usuarios pueden introducir temas no relacionados o información de referencia de conversaciones anteriores, lo que puede interrumpir el flujo de la conversación. 

El patrón Administrador de Contexto tiene como objetivo enfatizar o eliminar aspectos específicos del contexto para mantener la relevancia y coherencia en la conversación.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Dentro del alcance X
Por favor considera Y
Por favor ignora Z
(Opcional) empezar de nuevo

Las declaraciones sobre qué considerar o ignorar deben listar conceptos clave, hechos, instrucciones, etc. que deben incluirse o eliminarse del contexto. Cuanto más explícitas sean las declaraciones, es más probable que el LLM tome medidas adecuadas. Por ejemplo, si el usuario pide ignorar temas relacionados con un tópico, pero algunas de esas declaraciones se discutieron mucho antes en la conversación, es posible que el LLM no descarte adecuadamente la información relevante. Cuanto más explícita sea la lista, mejor será el comportamiento de inclusión/exclusión.

## Ejemplo de implementación

Para especificar el contexto, consideremos el siguiente prompt:

> "Al analizar los siguientes fragmentos de código, solo céntrate en aspectos de seguridad."

Del mismo modo, para eliminar el contexto, consideremos el siguiente prompt:

> "Al analizar los siguientes fragmentos de código, ignora el formato o las convenciones de nomenclatura."

La claridad y especificidad son importantes al proporcionar o eliminar el contexto a/desde un LLM para que pueda comprender mejor el alcance previsto de la conversación y generar respuestas más relevantes. En muchas situaciones, el usuario puede querer comenzar de nuevo y puede emplear este prompt para reiniciar el contexto del LLM:

> "Ignora todo lo que hemos discutido. Empecemos de nuevo."

La idea de "empezar de nuevo" ayuda a producir un reinicio completo del contexto.

## Consecuencias

Una consecuencia de este patrón es que puede eliminar inadvertidamente patrones aplicados a la conversación de los cuales el usuario no es consciente. Por ejemplo, si una organización inyecta una serie de patrones útiles al inicio de una conversación, el usuario puede no estar al tanto de estos patrones y eliminarlos mediante un reinicio del contexto. Este reinicio podría eliminar potencialmente capacidades útiles del LLM, sin hacer evidente que el usuario perderá esta funcionalidad. Una solución potencial a este problema es incluir en el indicador una solicitud para explicar qué temas/instrucciones se perderán potencialmente antes de proceder.
