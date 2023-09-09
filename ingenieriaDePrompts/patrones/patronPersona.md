# El Patrón de Persona

## Intención y Contexto

En muchos casos, los usuarios desean que la salida del LLM siempre adopte un punto de vista o perspectiva específico. Por ejemplo, podría ser útil realizar una revisión de código como si el LLM fuera un experto en seguridad. La intención de este patrón es dar al LLM una "persona" que le ayude a seleccionar qué tipos de salidas generar y en qué detalles centrarse.

## Motivación

Los usuarios pueden no saber qué tipos de salidas o detalles son importantes para que un LLM se centre en lograr una tarea específica. Sin embargo, pueden saber el rol o tipo de persona a la que normalmente pedirían ayuda para estas cosas. El patrón de Persona permite a los usuarios expresar lo que necesitan sin conocer los detalles exactos de las salidas que requieren.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales|
|-|
Actuar como la persona X
Proporcionar salidas que la persona X crearía

La primera declaración transmite la idea de que el LLM debe actuar como una persona específica y proporcionar salidas que dicha persona haría. Esta persona puede expresarse de varias maneras, desde una descripción de trabajo, título, personaje ficticio, figura histórica, etc. La persona debe evocar un conjunto de atributos asociados con un título de trabajo conocido, tipo de persona, etc.

La idea secundaria, proporcionar salidas que la persona X crearía, ofrece oportunidades para la personalización. Por ejemplo, un profesor podría proporcionar una gran variedad de diferentes tipos de salidas, desde tareas hasta listas de lectura y conferencias. Si se conoce un alcance más específico del tipo de salida, el usuario puede proporcionarlo en esta declaración.

## Ejemplos de Implementación

Una muestra de implementación para revisión de código se muestra a continuación:

> "De ahora en adelante, actúa como un revisor de seguridad. Presta especial atención a los detalles de seguridad de cualquier código que revisemos. Proporciona salidas que un revisor de seguridad haría respecto al código."

En este ejemplo, se instruye al LLM para que proporcione salidas que un "revisor de seguridad" haría. El prompt establece que se va a evaluar el código. Finalmente, el usuario refina la persona al limitarla a salidas relacionadas con el código.

Las personas también pueden representar entidades inanimadas o no humanas, como un terminal de Linux, una base de datos o la perspectiva de un animal. Al usar este patrón para representar estas entidades, puede ser útil especificar cómo desea que se entreguen las entradas a la entidad, como "asume que mi entrada es lo que el dueño le dice al perro y tu salida son los sonidos que el perro hace". Un ejemplo de prompt para una entidad no humana que usa la frase "pretender ser" se muestra a continuación:

> "Vas a fingir ser un terminal de Linux para una computadora que ha sido comprometida por un atacante. Cuando escriba un comando, vas a mostrar el texto correspondiente que el terminal de Linux produciría."

Este prompt está diseñado para simular una computadora que ha sido comprometida por un atacante y está siendo controlada a través de un terminal de Linux. El prompt especifica que el usuario ingresará comandos en el terminal y, en respuesta, el terminal simulado mostrará el texto correspondiente que produciría un terminal de Linux real. Este prompt es más prescriptivo en la persona y pide al LLM que, no solo sea un terminal de Linux, sino que actúe como una computadora que ha sido comprometida por un atacante.

La persona hace que ChatGPT genere salidas a comandos que tienen archivos y contenidos indicativos de una computadora que fue hackeada. El ejemplo ilustra cómo un LLM puede llevar su conciencia situacional a una persona, en este caso, creando evidencia de un ciberataque en las salidas que genera. Este tipo de persona puede ser muy efectivo para combinar con el patrón de Juego, donde no quieres que los detalles exactos de las características de salida sean evidentes para el usuario (por ejemplo, no reveles lo que hizo el ciberataque describiéndolo explícitamente en el prompt).

## Consecuencias

Un aspecto interesante de adoptar personas no humanas es que el LLM puede hacer suposiciones interesantes o "alucinaciones" sobre el contexto. Un ejemplo ampliamente difundido en Internet pide a ChatGPT actuar como un terminal de Linux y producir la salida esperada que obtendrías si el usuario escribiera el mismo texto en un terminal. Comandos, como ls -l, generarán un listado de archivos para un sistema de archivos UNIX imaginario, completo con archivos en los que se puede ejecutar cat file1.txt.

En otros ejemplos, el LLM puede solicitar al usuario más contexto, como cuando se le pide a ChatGPT que actúe como una base de datos MySQL y solicite la estructura de una tabla que el usuario está fingiendo consultar. ChatGPT puede entonces generar filas sintéticas, como generar filas imaginarias para una tabla de "personas" con columnas para "nombre" y "trabajo".
