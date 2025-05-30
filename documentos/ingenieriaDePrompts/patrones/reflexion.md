<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Patrón Reflexión

## Intención y Contexto

El objetivo de este patrón es pedir al modelo que explique automáticamente la justificación detrás de las respuestas dadas al usuario. El patrón permite a los usuarios evaluar mejor la validez de la salida, así como informar a los usuarios cómo un LLM llegó a una respuesta particular. La reflexión puede aclarar cualquier punto de confusión, descubrir supuestos subyacentes y revelar lagunas en el conocimiento o comprensión.

## Motivación

Los LLM pueden y cometen errores. Además, los usuarios pueden no entender por qué un LLM está produciendo una salida particular y cómo adaptar su indicación para resolver un problema con la salida. Al pedir al LLM que explique automáticamente la justificación detrás de sus respuestas, los usuarios pueden obtener una mejor comprensión de cómo el modelo está procesando la entrada, qué supuestos está haciendo y qué datos está utilizando. Los LLM pueden proporcionar respuestas incompletas, incorrectas o ambiguas. La reflexión es una ayuda para abordar estas deficiencias y garantizar que la información proporcionada por el LLM sea precisa. Otro beneficio del patrón es que puede ayudar a los usuarios a depurar sus indicaciones y determinar por qué no están obteniendo resultados que cumplan con las expectativas. Este patrón es particularmente efectivo para la exploración de temas que pueden confundirse con otros temas o que pueden tener interpretaciones matizadas y donde es importante conocer la interpretación precisa que el LLM utilizó.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Siempre que generes una respuesta,
Explica el razonamiento y las suposiciones detrás de tu respuesta.
(Opcional) ...para que pueda mejorar mi pregunta.

La primera declaración solicita que, después de generar una respuesta, el LLM debería explicar el razonamiento y las suposiciones detrás de la respuesta. Esta declaración ayuda al usuario a entender cómo el LLM llegó a la respuesta y puede ayudar a construir confianza en las respuestas del modelo. El prompt incluye la declaración de que el propósito de la explicación es para que el usuario refine su pregunta. Esta declaración adicional proporciona al LLM el contexto que necesita para adaptar mejor sus explicaciones al propósito específico de ayudar al usuario a producir preguntas de seguimiento.

## Ejemplo de Implementación

Este ejemplo adapta la indicación específicamente al dominio de proporcionar respuestas relacionadas con el código:

> "Cuando proporciones una respuesta, por favor explica el razonamiento y las suposiciones detrás de tu selección de marcos de software. Si es posible, utiliza ejemplos específicos o evidencia con muestras de código asociadas para respaldar tu respuesta de por qué el marco es la mejor selección para la tarea. Además, aborda cualquier ambigüedad potencial o limitaciones en tu respuesta, para proporcionar una respuesta más completa y precisa."

El patrón se personaliza aún más para instruir al LLM que debe justificar su selección de marcos de software, pero no necesariamente otros aspectos de la respuesta. Además, el usuario dicta que las muestras de código deben usarse para ayudar a explicar la motivación para seleccionar el marco de software específico.

## Consecuencias

Una consecuencia del patrón Reflexión es que puede no ser efectivo para los usuarios que no entienden el área temática de la discusión. Por ejemplo, una pregunta altamente técnica de un usuario no técnico puede resultar en una justificación compleja para la respuesta que el usuario no puede comprender. Al igual que con otros patrones de indicación, existe el riesgo de que la salida pueda incluir errores o supuestos inexactos incluidos en la explicación de la justificación que el usuario puede no ser capaz de detectar. Este patrón se puede combinar con la [Lista de Verificación de Hechos](listaVerificacionHechos.md) para ayudar a abordar este problema.
