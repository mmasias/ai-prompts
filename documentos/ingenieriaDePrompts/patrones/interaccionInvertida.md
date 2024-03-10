<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Patrón de Interacción Invertida

## Intención y Contexto

Se busca que el LLM haga preguntas para obtener la información que necesita para realizar algunas tareas. En lugar de que el usuario dirija la conversación, se hace que el LLM tome la iniciativa en la conversación para centrarla en lograr un objetivo específico. Por ejemplo, es posible que desees que el LLM te proporcione un cuestionario rápido o que haga preguntas automáticamente hasta que tenga suficiente información para generar un script de despliegue para tu aplicación en un entorno en la nube específico.

## Motivación

En lugar de que el usuario dirija una conversación, un LLM a menudo tiene conocimientos que puede usar para obtener información del usuario de manera más precisa. El objetivo del Patrón de Interacción Invertida es cambiar el flujo de interacción para que el LLM haga preguntas al usuario con el fin de lograr un objetivo deseado. El LLM a menudo puede seleccionar mejor el formato, número y contenido de las interacciones para garantizar que el objetivo se alcance más rápidamente, con mayor precisión y/o utilizando conocimientos que el usuario podría no poseer (inicialmente).

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Quiero que me hagas preguntas para lograr X.
Debes hacer preguntas hasta que se cumpla esta condición o para lograr este objetivo (o alternativamente, indefinidamente).
(Opcional) Házme las preguntas una a una, dos a la vez, etc.

Un indicativo para una interacción invertida siempre debe especificar el objetivo de la interacción. La primera idea (es decir, deseas que el LLM haga preguntas para lograr un objetivo) comunica este objetivo al LLM. Es igualmente importante que las preguntas se centren en un tema o resultado particular. Al proporcionar el objetivo, el LLM puede entender lo que está tratando de lograr a través de la interacción y adaptar sus preguntas en consecuencia. Esta "inversión de control" permite una interacción más centrada y eficiente, ya que el LLM solo hará preguntas que considere relevantes para lograr el objetivo especificado.

La segunda idea proporciona el contexto de cuánto tiempo debe durar la interacción. Una interacción invertida puede terminarse con una respuesta como "deja de hacer preguntas". Sin embargo, a menudo es mejor delimitar la interacción a una duración razonable o solo hasta que se alcance el objetivo. Este objetivo puede ser sorprendentemente abierto y el LLM continuará trabajando hacia el objetivo haciendo preguntas, como en el ejemplo de "hasta que tengas suficiente información para generar un script en Python".

Por defecto, es probable que el LLM genere múltiples preguntas por iteración. La tercera idea es completamente opcional, pero puede mejorar la usabilidad limitando (o ampliando) el número de preguntas que el LLM genera por ciclo. Si no se especifica un número/formato preciso para el cuestionamiento, el cuestionamiento será semi-aleatorio y puede llevar a preguntas una a una o diez a la vez. El indicativo, por lo tanto, puede adaptarse para incluir el número de preguntas hechas a la vez, el orden de las preguntas y cualquier otra consideración de formato/orden para facilitar la interacción del usuario.

## Ejemplo de Implementación

A continuación se muestra un ejemplo de indicativo para una interacción invertida:

> "A partir de ahora, quiero que me hagas preguntas para desplegar una aplicación en Python en AWS. Cuando tengas suficiente información para desplegar la aplicación, crea un script en Python para automatizar el despliegue."

En general, cuanto más específico sea el indicativo con respecto a las restricciones y la información a recopilar, mejor será el resultado. Por ejemplo, el indicativo anterior podría proporcionar un menú de posibles servicios de AWS (como Lambda, EC2, etc.) con los cuales desplegar la aplicación. En otros casos, se puede permitir que el LLM simplemente tome decisiones adecuadas por sí mismo sobre cosas sobre las que el usuario no toma decisiones explícitamente. Una limitación de este indicativo es que, una vez que se proporciona otra información contextual sobre la tarea, puede requerir experimentación con la redacción precisa para que el LLM haga las preguntas en el número y flujo adecuados para adaptarse mejor a la tarea, como hacer múltiples preguntas a la vez versus una pregunta a la vez.

## Consecuencias

Una consideración al diseñar el indicativo es cuánto dictar al LLM sobre qué información recopilar antes de terminar. En el ejemplo anterior, la interacción invertida es abierta y puede variar significativamente en el artefacto generado finalmente. Esta apertura hace que el indicativo sea genérico y reutilizable, pero podría hacer preguntas adicionales que podrían omitirse si se da más contexto.

Si se conocen requisitos específicos con antelación, es mejor inyectarlos en el indicativo en lugar de esperar que el LLM obtenga la información necesaria. De lo contrario, el LLM decidirá de manera no determinista si solicitar al usuario la información o hacer una suposición educada sobre un valor adecuado.

Por ejemplo, el usuario puede indicar que le gustaría desplegar una aplicación en Amazon AWS EC2, en lugar de simplemente decir "la nube" y requerir múltiples interacciones para reducir el objetivo de despliegue. Cuanto más precisa sea la información inicial, mejor podrá el LLM usar las preguntas limitadas que es probable que un usuario esté dispuesto a responder para obtener información y mejorar su salida.

Al desarrollar indicativos para interacciones invertidas, es importante considerar el nivel de conocimiento, compromiso y control del usuario. Si el objetivo es lograr el objetivo con la menor interacción del usuario posible (control mínimo), eso debe indicarse explícitamente. Por el contrario, si el objetivo es asegurarse de que el usuario esté al tanto de todas las decisiones clave y las confirme (compromiso máximo), eso también debe indicarse explícitamente. Del mismo modo, si se espera que el usuario tenga un conocimiento mínimo y las preguntas deben estar dirigidas a su nivel de experiencia, esta información debe incorporarse en el indicativo.
