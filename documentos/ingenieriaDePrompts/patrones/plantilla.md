<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Patrón Plantilla

## Intención y Contexto

La intención de este patrón es asegurarse de que la salida del LLM siga una plantilla precisa en términos de estructura. Por ejemplo, el usuario podría necesitar generar una URL que inserte información generada en posiciones específicas dentro de la ruta de la URL. Este patrón permite al usuario instruir al LLM para producir su salida en un formato que normalmente no usaría para el tipo específico de contenido que se está generando.

## Motivación

En algunos casos, la salida debe producirse en un formato preciso que es específico de la aplicación o del caso de uso y que el LLM desconoce. Dado que el LLM no conoce la estructura de la plantilla, debe ser instruido sobre cuál es el formato y dónde deben ir las diferentes partes de su salida.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Voy a proporcionar una plantilla para tu salida.
X es mi marcador de posición para el contenido.
Intenta ajustar la salida en uno o más de los marcadores de posición que enumero.
Por favor, conserva el formato y la plantilla general que proporciono.
Esta es la plantilla: PATRÓN con MARCADORES DE POSICIÓN.

El primer enunciado dirige al LLM a seguir una plantilla específica para su salida. La plantilla se utilizará para intentar hacer que las respuestas del LLM se ajusten a una estructura que sea coherente con las necesidades de formato del usuario.

## Ejemplo de Implementación

Una muestra de plantilla para generar URLs donde la salida se coloca en lugares específicos en la plantilla se muestra a continuación:

> “Voy a proporcionarte una plantilla para tu salida. Todo lo que esté en mayúsculas es un marcador de posición. Cada vez que generes texto, intenta encajarlo en uno de los marcadores de posición que enumero. Por favor, conserva el formato y la plantilla general que te proporciono en https://miapi.com/NOMBRE/perfil/PROFESIÓN”

Una interacción de muestra después de proporcionar el indicativo sería:

|||
|-|-|
Usuario|“Genera un nombre y título profesional para una persona”
ChatGPT|“https://miapi.com/Emily Parker/perfil/Ingeniera de Software”

## Consecuencias

Una consecuencia de aplicar el Patrón de Plantilla es que filtra la salida del LLM, lo que puede eliminar otras salidas que el LLM habría proporcionado y que podrían ser útiles para el usuario. En muchos casos, el LLM puede proporcionar descripciones útiles de código, toma de decisiones u otros detalles que este patrón eliminará efectivamente de la salida. Por lo tanto, los usuarios deben sopesar los pros y contras de filtrar esta información adicional.

Además, el filtrado puede dificultar la combinación de este patrón con otros patrones de la categoría de Personalización de Salida. El Patrón de Plantilla efectivamente restringe el formato de salida, por lo que puede no ser compatible con la generación de ciertos otros tipos de salida. Por ejemplo, en la plantilla proporcionada anteriormente para una URL, no sería fácil (o probablemente posible) combinarla con el Patrón de Receta, que necesita generar una lista de pasos.
