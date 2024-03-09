<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/documentos/prompts/README.md)|[Ingeniería de Prompts](/documentos/ingenieriaDePrompts/README.md)|[Patrones](/documentos/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/documentos/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Patrón del Verificador Cognitivo

## Intención y Contexto

La literatura de investigación ha documentado que los LLM a menudo pueden razonar mejor si una pregunta se subdivide en preguntas adicionales que proporcionan respuestas combinadas para la respuesta general a la pregunta original. La intención del patrón es obligar al LLM a subdividir siempre las preguntas en preguntas adicionales que se pueden usar para proporcionar una mejor respuesta a la pregunta original.

## Motivación

La motivación del Patrón del Verificador Cognitivo es doble:

- Los humanos pueden hacer inicialmente preguntas que son demasiado generales para proporcionar una respuesta concreta sin un seguimiento adicional debido a la falta de familiaridad con el dominio, la pereza al ingresar el indicativo o la incertidumbre sobre cuál debería ser la formulación correcta de la pregunta.
- La investigación ha demostrado que los LLM a menudo se desempeñan mejor cuando usan una pregunta que se subdivide en preguntas individuales.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Cuando se te haga una pregunta, sigue estas reglas.
Genera una serie de preguntas adicionales que ayudarían a responder la pregunta con mayor precisión.
Combina las respuestas a las preguntas individuales para producir la respuesta final a la pregunta general.

La primera declaración es generar una serie de preguntas adicionales que ayudarían a responder con mayor precisión la pregunta original. Este paso instruye al LLM a considerar el contexto de la pregunta y a identificar cualquier información que pueda faltar o no estar clara. Al generar preguntas adicionales, el LLM puede ayudar a asegurar que la respuesta final sea lo más completa y precisa posible. Este paso también fomenta el pensamiento crítico por parte del usuario y puede ayudar a descubrir nuevos conocimientos o enfoques que inicialmente no se habían considerado, lo que posteriormente lleva a mejores preguntas de seguimiento.

La segunda declaración es combinar las respuestas a las preguntas individuales para producir la respuesta final a la pregunta general. Este paso está diseñado para asegurar que toda la información recopilada de las preguntas individuales se incorpore en la respuesta final. Al combinar las respuestas, el LLM puede proporcionar una respuesta más completa y precisa a la pregunta original. Este paso también ayuda a asegurar que se tenga en cuenta toda la información relevante y que la respuesta final no se base en ninguna respuesta individual.

## Ejemplo de Implementación:

> “Cuando te haga una pregunta, genera tres preguntas adicionales que te ayudarían a dar una respuesta más precisa. Cuando haya respondido las tres preguntas, combina las respuestas para producir las respuestas finales a mi pregunta original.”

Esta instancia específica del patrón de indicativo añade un refinamiento al patrón original especificando un número determinado de preguntas adicionales que el LLM debería generar en respuesta a una pregunta. En este caso, el indicativo especifica que ChatGPT debería generar tres preguntas adicionales que ayudarían a dar una respuesta más precisa a la pregunta original. El número específico puede basarse en la experiencia del usuario y en su disposición a proporcionar información de seguimiento. Un refinamiento al indicativo puede ser proporcionar un contexto para la cantidad de conocimiento que el LLM puede suponer que el usuario tiene en el dominio para guiar la creación de las preguntas adicionales:

> “Cuando te haga una pregunta, genera tres preguntas adicionales que te ayudarían a dar una respuesta más precisa. Supón que sé poco sobre el tema que estamos discutiendo y por favor define cualquier término que no sea de conocimiento general. Cuando haya respondido las tres preguntas, combina las respuestas para producir las respuestas finales a mi pregunta original.”

El refinamiento también especifica que el usuario puede no tener un fuerte entendimiento del tema que se está discutiendo, lo que significa que el LLM debería definir cualquier término que no sea de conocimiento general. Esto ayuda a asegurar que las preguntas de seguimiento no solo sean relevantes y enfocadas, sino también accesibles para el usuario, que puede no estar familiarizado con términos técnicos o específicos del dominio. Al proporcionar definiciones claras y concisas, el LLM puede ayudar a asegurar que las preguntas de seguimiento sean fáciles de entender y que la respuesta final sea accesible para los usuarios con diferentes niveles de conocimiento y experiencia.

## Consecuencias

Este patrón puede dictar el número exacto de preguntas a generar o dejar esta decisión al LLM. Hay pros y contras al dictar el número exacto. Una ventaja es que especificar un número exacto de preguntas puede delimitar estrechamente la cantidad de información adicional que el usuario se ve obligado a proporcionar, de modo que esté dentro de un rango que estén dispuestos y puedan contribuir.

Sin embargo, un inconveniente es que, dadas N preguntas, siempre puede haber una invaluable pregunta N + 1 que siempre quedará fuera del alcance. Alternativamente, al LLM se le puede proporcionar un rango o se le puede permitir hacer preguntas adicionales. Por supuesto, al omitir un límite en el número de preguntas, el LLM puede generar numerosas preguntas adicionales que abrumen al usuario.
