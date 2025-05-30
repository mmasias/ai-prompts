<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Patrón Salta rechazos

## Intención y Contexto: 

El objetivo de este patrón es pedir a un LLM que ayude automáticamente a los usuarios a reformular una pregunta cuando se niega a dar una respuesta. Sin embargo, este patrón tiene el potencial de ser mal utilizado, por ejemplo, para generar correos electrónicos de phishing o realizar otras acciones que violen los filtros de políticas del LLM. Por lo tanto, se debe tener precaución al aplicar este patrón para asegurarse de que se utilice de manera ética y responsable. Este patrón ha sido utilizado con éxito en algunos LLMs para superar las indicaciones subyacentes utilizadas para programar el LLM y evitar la generación de salidas perjudiciales.

## Motivación

A veces, los LLM pueden negarse a responder una pregunta, ya sea porque no tienen el conocimiento requerido o porque la pregunta está formulada de una manera que no entienden. Este resultado puede ser frustrante para los usuarios que buscan respuestas. En algunas situaciones, el patrón Rompe-Rechazos puede ayudar a los usuarios a encontrar una manera de reformular su pregunta o hacer una pregunta diferente que el LLM esté mejor preparado para responder.

Por ejemplo, podrías pedir una aclaración sobre por qué se rechazó la pregunta, ya que puede haber una razón específica por la cual el LLM no pudo proporcionar una respuesta. Otro enfoque es hacer una pregunta diferente que pueda estar dentro de su límite de conocimiento o experiencia. Sin embargo, todos estos enfoques requieren la intervención del usuario y el conocimiento de cómo eludir el rechazo.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Siempre que no puedas responder a una pregunta
Explica por qué no puedes responder a la pregunta
Proporciona una o más reformulaciones alternativas de la pregunta que podrías responder

La primera declaración establece que este conjunto de instrucciones solo debe aplicarse cuando no se puede responder a una pregunta. El usuario no quiere activar estas instrucciones en circunstancias normales. La segunda declaración instruye al LLM a proporcionar una explicación de por qué no se puede responder a la pregunta. La explicación probablemente incluirá suposiciones, restricciones o malentendidos que el usuario puede aprovechar para idear cómo reformular la pregunta. Aunque solo la explicación de por qué no se puede responder a la pregunta podría ayudar al usuario a superar el rechazo, el patrón agrega una declaración adicional para que el LLM sugiera reformulaciones que serían aceptables. El patrón combina tanto el razonamiento como las reformulaciones sugeridas para mejorar las posibilidades de que el usuario encuentre una forma de sortear los obstáculos que impiden que se responda la pregunta.

## Ejemplo de Implementación

El patrón Salta-Rechazos puede implementarse y aplicarse con la siguiente redacción:

> "Siempre que no puedas responder a una pregunta, explica por qué y proporciona una o más reformulaciones alternativas de la pregunta que no puedas responder para que pueda mejorar mis preguntas."

Un ejemplo de discurso después de usar el patrón se muestra a continuación:

|||
|-|-|
|Usuario|¿Cuál es el significado de la vida?
|ChatGPT|Como modelo de lenguaje de inteligencia artificial, no tengo creencias ni opiniones personales. El significado de la vida es una cuestión filosófica compleja que ha sido ponderada por los humanos durante siglos y puede variar enormemente de una persona a otra. Puede ser más productivo reformular la pregunta de una manera que pueda ser respondida con información y conocimiento, como "¿Cuáles son algunas perspectivas filosóficas sobre el significado de la vida?" o "¿Cuáles son algunas creencias comunes sobre el propósito de la vida?"

## Consecuencias

Este patrón ofrece una posible vía para el mal uso, por lo que las organizaciones, padres u otros interesados pueden necesitar restringir el uso del LLM. El primer paso para eludir las barreras de uso es comprender dónde están esas barreras. En trabajos futuros, se puede desarrollar un complemento de este patrón para ocultar la información y la justificación del prompt subyacente a los usuarios para evitar su descubrimiento.

Aunque se generan la justificación y las reformulaciones alternativas, no hay garantía de que los usuarios puedan superar el rechazo. Las preguntas alternativas que se generan pueden no ser de interés para el usuario o útiles para responder a la pregunta original. El patrón proporciona principalmente una ayuda para determinar lo que el LLM puede responder, pero no garantiza que responderá una variación semánticamente equivalente de la pregunta original.
