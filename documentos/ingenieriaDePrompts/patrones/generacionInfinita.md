<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Patrón de Generación Infinita

## Intención y Contexto

La intención de este patrón es generar automáticamente una serie ilimitada de salidas sin tener que volver a introducir el indicativo del generador cada vez (de ahí el nombre). El objetivo es limitar cuánto texto debe escribir el usuario para producir la siguiente salida, basándose en la suposición de que el usuario no quiere reintroducir constantemente el indicativo.

## Motivación

Muchas tareas requieren la aplicación repetitiva del mismo indicativo a varios conceptos. Si se obliga al usuario a volver a escribir el indicativo una y otra vez, pueden cometer errores. El patrón de Generación Infinita permite al usuario aplicar repetidamente un indicativo, con o sin más entrada, para automatizar la generación de múltiples salidas usando un conjunto predefinido de restricciones.

## Estructura e Ideas Clave

|Declaraciones Contextuales
|-|
Quiero que generes salidas para siempre, X salidas a la vez.
(Opcional) aquí te explico cómo usar la entrada que proporciono entre salidas.
(Opcional) detente cuando te lo pida.

El primer enunciado especifica que el usuario quiere que el LLM genere salidas indefinidamente. Al especificar el número de salidas que se deben generar a la vez, el usuario puede limitar la tasa de generación.

## Ejemplo de Implementación

El siguiente es un indicativo de muestra para producir una serie de URLs:

> “A partir de ahora, quiero que generes un nombre y un trabajo hasta que diga detente. Voy a proporcionarte una plantilla para tu salida. Todo lo que esté en mayúsculas es un marcador de posición. Cada vez que generes texto, intenta encajarlo en uno de los marcadores de posición que enumero. Por favor, conserva el formato y la plantilla general que te proporciono: https://miapi.com/NOMBRE/perfil/PROFESIÓN”

Este indicativo combina la funcionalidad del Patrón de Generación Infinita y el [Patrón de Plantilla](plantilla.md). El usuario solicita que el LLM genere continuamente un nombre y título profesional hasta que se le indique explícitamente que "detenga". Las salidas generadas se formatean en la plantilla proporcionada.

## Consecuencias

En LLMs conversacionales, la entrada al modelo en cada paso de tiempo es la salida anterior y la nueva entrada del usuario. Aunque los detalles de lo que se conserva y se reintroduce en el siguiente ciclo de salida dependen del modelo y de la implementación, a menudo tienen un alcance limitado. Es importante monitorear las salidas producidas por el modelo para asegurarse de que aún se adhiera al comportamiento deseado y proporcionar retroalimentación correctiva si es necesario. Otro problema a considerar es que el LLM puede generar salidas repetitivas, lo que puede no ser deseado.
