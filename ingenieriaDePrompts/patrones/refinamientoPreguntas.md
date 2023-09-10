# Patrón de Refinamiento de Preguntas

## Intención y Contexto

Este patrón involucra al LLM en el proceso de ingeniería de prompts. La intención de este patrón es asegurar que el LLM conversacional siempre sugiera preguntas potencialmente mejores o más refinadas de las que el usuario podría hacer en lugar de su pregunta original. Usando este patrón, el LLM puede ayudar al usuario a encontrar la pregunta correcta para obtener una respuesta precisa. Además, el LLM puede ayudar al usuario a encontrar la información o lograr su objetivo en menos interacciones que si el usuario empleara indicativos por ensayo y error.

## Motivación

Si un usuario hace una pregunta, es posible que no sea un experto en el dominio y puede que no sepa la mejor manera de formular la pregunta o no esté al tanto de información adicional útil. Los LLMs a menudo indican limitaciones en la respuesta que proporcionan o solicitan información adicional para ayudarles a producir una respuesta más precisa. Un LLM también puede indicar suposiciones que hizo al proporcionar la respuesta. La motivación es que esta información adicional o conjunto de suposiciones podría usarse para generar un indicativo mejor. En lugar de requerir que el usuario reinterprete y reformule su indicativo con la información adicional, el LLM puede refinar directamente el indicativo para incorporar la información adicional.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Dentro del alcance X, sugiere una mejor versión de la pregunta para usar en su lugar.
(Opcional) pregúntame si quisiera usar la mejor versión en su lugar.

La primera declaración contextual en el indicativo está pidiendo al LLM que sugiera una mejor versión de una pregunta dentro de un alcance específico. El alcance se proporciona para asegurar que no todas las preguntas se reescriban automáticamente o que se refinen con un objetivo dado. La segunda declaración contextual está destinada a la automatización y permite al usuario usar automáticamente la pregunta refinada sin tener que copiar/pegar o ingresarla manualmente. La ingeniería de este indicativo puede ser aún más refinada al combinarla con el patrón de Reflexión, que permite al LLM explicar por qué cree que la pregunta refinada es una mejora.

## Ejemplo de Implementación:

> “A partir de ahora, cada vez que haga una pregunta sobre la seguridad de un artefacto de software, sugiere una mejor versión de la pregunta que incorpore información específica sobre riesgos de seguridad en el lenguaje o marco que estoy usando y pregúntame si quisiera usar tu pregunta en su lugar.”

En el contexto del ejemplo anterior, el LLM usará el Patrón de Refinamiento de Pregunta para mejorar preguntas relacionadas con la seguridad solicitando o usando detalles específicos sobre el artefacto de software y el lenguaje o marco utilizado para construirlo. Por ejemplo, si un desarrollador de una aplicación web en Python con FastAPI pregunta “¿Cómo manejo la autenticación de usuarios en mi aplicación web?”, el LLM refinará la pregunta teniendo en cuenta que la aplicación web está escrita en Python con FastAPI. Luego, el LLM proporciona una pregunta revisada que es más específica para el lenguaje y marco, como “¿Cuáles son las mejores prácticas para manejar la autenticación de usuarios de manera segura en una aplicación web FastAPI para mitigar riesgos de seguridad comunes, como cross-site scripting (XSS), falsificación de petición en sitios cruzados (CSRF) y secuestro de sesión?”

El detalle adicional en la pregunta revisada probablemente no solo hará que el usuario esté al tanto de los problemas que necesita considerar, sino que también obtendrá una mejor respuesta del LLM. Para tareas de ingeniería de software, este patrón también podría incorporar información sobre posibles errores, modularidad u otras consideraciones de calidad del código. Otro enfoque sería refinar automáticamente las preguntas para que el código generado separe claramente las preocupaciones o minimice el uso de bibliotecas externas, como:

> Cada vez que haga una pregunta sobre cómo escribir algún código, sugiere una mejor versión de mi pregunta que pregunte cómo escribir el código de una manera que minimice mis dependencias de bibliotecas externas.

## Consecuencias

El Patrón de Refinamiento de Pregunta ayuda a cerrar la brecha entre el conocimiento del usuario y la comprensión del LLM, lo que resulta en interacciones más eficientes y precisas. Un riesgo de este patrón es su tendencia a reducir rápidamente el cuestionamiento del usuario en un área específica que guía al usuario por un camino de investigación más limitado de lo necesario. La consecuencia de esta reducción es que el usuario puede perder información importante del "panorama general". Una solución a este problema es proporcionar un alcance adicional al indicativo del patrón, como “no limites mis preguntas a lenguajes o marcos de programación específicos”.

Otro enfoque para superar la reducción arbitraria o el objetivo limitado de la pregunta refinada es combinar el Patrón de Refinamiento de Pregunta con otros patrones. En particular, este patrón se puede combinar con el patrón de Verificador Cognitivo para que el LLM produzca automáticamente una serie de preguntas de seguimiento que pueden producir la pregunta refinada. Por ejemplo, en el siguiente indicativo, los patrones de Refinamiento de Pregunta y Verificador Cognitivo se aplican para asegurar que se hagan mejores preguntas al LLM:

> “A partir de ahora, cada vez que haga una pregunta, haz cuatro preguntas adicionales que te ayudarían a producir una mejor versión de mi pregunta original. Luego, usa mis respuestas para sugerir una mejor versión de mi pregunta original.”

Al igual que muchos patrones que permiten a un LLM generar nuevas preguntas usando su conocimiento, el LLM puede introducir términos o conceptos desconocidos para el usuario en la pregunta. Una forma de abordar este problema es incluir una declaración de que el LLM debe explicar cualquier término desconocido que introduzca en la pregunta. Una mejora adicional de esta idea es combinar el Patrón de Refinamiento de Pregunta con el patrón de Persona para que el LLM marque términos y genere definiciones que asuman un nivel particular de conocimiento, como en este ejemplo:

> “A partir de ahora, cada vez que haga una pregunta, haz cuatro preguntas adicionales que te ayudarían a producir una mejor versión de mi pregunta original. Luego, usa mis respuestas para sugerir una mejor versión de mi pregunta original. Después de las preguntas de seguimiento, actúa temporalmente como un usuario sin conocimiento de AWS y define cualquier término que necesite conocer para responder con precisión las preguntas.”

Un LLM siempre puede producir inexactitudes factuales, al igual que un humano. Un riesgo de este patrón es que las inexactitudes se introduzcan en la pregunta refinada. Sin embargo, este riesgo puede mitigarse combinando el patrón de Lista de Verificación de Hechos para permitir que el usuario identifique posibles inexactitudes y el patrón de Reflexión para explicar el razonamiento detrás del refinamiento de la pregunta.
