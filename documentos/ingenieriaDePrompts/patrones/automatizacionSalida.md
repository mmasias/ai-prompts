<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Patrón Automatización de Salida

## Intención y Contexto

La intención de este patrón es que el LLM genere un script u otro artefacto de automatización que pueda realizar automáticamente cualquier paso que recomiende como parte de su salida. El objetivo es reducir el esfuerzo manual necesario para implementar las recomendaciones de salida del LLM.

## Motivación

La salida de un LLM suele ser una secuencia de pasos que el usuario debe seguir. Por ejemplo, al pedirle a un LLM que genere un script de configuración en Python, puede sugerir una serie de archivos a modificar y cambios a aplicar en cada archivo. Sin embargo, hacer que los usuarios realicen continuamente los pasos manuales dictados por la salida del LLM es tedioso y propenso a errores.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Siempre que produzcas una salida que tenga al menos un paso a seguir y las siguientes propiedades (alternativamente, siempre haz esto)
Crea un artefacto ejecutable del tipo X que automatice estos pasos.

La primera parte del patrón identifica las situaciones bajo las cuales se debe generar la automatización. Un enfoque simple es afirmar que la salida incluye al menos dos pasos a seguir y que se debe producir un artefacto de automatización. El alcance depende del usuario, pero ayuda a evitar producir scripts de automatización en casos donde ejecutar el script de automatización requerirá más esfuerzo del usuario que realizar los pasos originales producidos en la salida. El alcance puede limitarse a salidas que requieran más de un cierto número de pasos.

La siguiente parte de este patrón proporciona una declaración concreta del tipo de salida que el LLM debe producir para realizar la automatización. Por ejemplo, "crea un script en Python" le da al LLM una comprensión concreta para traducir los pasos generales en pasos equivalentes en Python.

## Ejemplo de Implementación

Una muestra de este patrón de prompt aplicado a fragmentos de código generados por el LLM ChatGPT se muestra a continuación:

> “A partir de ahora, siempre que generes código que abarque más de un archivo, genera un script en Python que pueda ejecutarse para crear automáticamente los archivos especificados o hacer cambios en archivos existentes para insertar el código generado.”

Este patrón es particularmente efectivo en ingeniería de software, ya que una tarea común para los ingenieros de software que usan LLMs es copiar/pegar las salidas en múltiples archivos. Algunas herramientas, como Copilot, insertan fragmentos limitados directamente en la sección de código con la que está trabajando el programador, pero herramientas, como ChatGPT, no ofrecen estas facilidades. Este truco de automatización también es efectivo para crear scripts para ejecutar comandos en una terminal, automatizar operaciones en la nube o reorganizar archivos en un sistema de archivos.

Este patrón es un complemento poderoso para cualquier sistema que pueda ser controlado por computadora. El LLM puede proporcionar un conjunto de pasos que deben tomarse en el sistema controlado por computadora y luego la salida se puede traducir en un script que permite que la computadora que controla el sistema tome automáticamente los pasos. Esta es una vía directa para permitir que los LLMs, como ChatGPT, integren calidad en, y controlen, nuevos sistemas informáticos que tienen una interfaz de scripting conocida.

## Consecuencias

Una consideración importante de uso de este patrón es que el artefacto de automatización debe definirse de manera concreta. Sin un significado concreto de cómo "automatizar" los pasos, el LLM a menudo afirma que "no puede automatizar cosas" ya que eso está más allá de sus capacidades. Los LLMs típicamente aceptan solicitudes para producir código, por lo que el objetivo es instruir al LLM para generar texto/código, que se pueda ejecutar para automatizar algo. Esta distinción sutil en el significado es importante para ayudar a un LLM a desambiguar el significado del prompt.

Una advertencia del patrón de Automatización de Salida es que el LLM necesita suficiente contexto conversacional para generar un artefacto de automatización que sea funcional en el contexto objetivo, como el sistema de archivos de un proyecto en una computadora Mac vs. Windows. Este patrón funciona mejor cuando el contexto completo necesario para la automatización está contenido dentro de la conversación. Alternativamente, secuencias de pasos autónomos funcionan bien, como "¿cómo encuentro la lista de puertos abiertos en mi computadora Mac?".

En algunos casos, el LLM puede producir una salida larga con múltiples pasos y no incluir un artefacto de automatización. Esta omisión puede surgir por varias razones, incluido el exceder la limitación de longitud de salida que el LLM admite. Una solución simple para esta situación es recordarle al LLM a través de un prompt de seguimiento, como "Pero no lo automatizaste", que proporciona el contexto de que se omitió el artefacto de automatización y debe generarse.

En este punto de la evolución de los LLMs, el patrón de Automatización de Salida es mejor empleado por usuarios que pueden leer y entender el artefacto de automatización generado. Los LLMs pueden (y lo hacen) producir inexactitudes en su salida, por lo que aceptar y ejecutar ciegamente un artefacto de automatización conlleva un riesgo significativo. Aunque este patrón puede aliviar al usuario de realizar ciertos pasos manuales, no alivia su responsabilidad de entender las acciones que realizan usando la salida. Por lo tanto, cuando los usuarios ejecutan scripts de automatización, asumen la responsabilidad de los resultados.
