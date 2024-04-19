<div align=right>

||[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# El Patrón Creación de Meta Lenguaje

## Intención y Contexto

Durante una conversación con un LLM, el usuario podría querer crear el prompt a través de un lenguaje alternativo, como una notación abreviada textual para gráficos, una descripción de estados y transiciones de estado para una máquina de estados, un conjunto de comandos para automatización de prompts, etc. La intención de este patrón es explicar la semántica de este lenguaje alternativo al LLM para que el usuario pueda escribir futuros prompts usando este nuevo lenguaje y su semántica.

## Motivación

Muchos problemas, estructuras u otras ideas comunicadas en un prompt pueden expresarse de manera más concisa, sin ambigüedades o claramente en un lenguaje distinto al inglés (o cualquier lenguaje humano convencional utilizado para interactuar con un LLM). Sin embargo, para producir una salida basada en un lenguaje alternativo, un LLM necesita entender la semántica del lenguaje.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Cuando digo X, quiero decir Y (o quiero que hagas Y)

La estructura clave de este patrón implica explicar el significado de uno o más símbolos, palabras o declaraciones al LLM para que utilice la semántica proporcionada en la conversación subsiguiente. Esta descripción puede tomar la forma de una simple traducción, como "X" significa "Y". La descripción también puede tomar formas más complejas que definen una serie de comandos y su semántica, como "cuando digo X, quiero que hagas ".

## Ejemplo de Implementación

La clave para usar con éxito el patrón de Creación de Meta Lenguaje es desarrollar una notación o abreviatura no ambigua, como la siguiente:

> "De ahora en adelante, siempre que escriba dos identificadores separados por un “→”, estoy describiendo un gráfico. Por ejemplo, “a → b” describe un gráfico con nodos “a” y “b” y un borde entre ellos. Si separo identificadores por “-[w:2, z:3]→”, estoy añadiendo propiedades del borde, como un peso o etiqueta.”

Este ejemplo del patrón de Creación de Meta Lenguaje establece una notación estandarizada para describir gráficos definiendo una convención para representar nodos y bordes. Siempre que el autor escriba dos identificadores separados por un símbolo “→”, es una indicación de que se está describiendo un gráfico. Además, el prompt especifica que se puede proporcionar información adicional sobre los bordes usando la sintaxis “-[w:2, z:3]→”.

## Consecuencias

Aunque este patrón proporciona un medio poderoso para personalizar la interacción de un usuario con un LLM, puede crear el potencial de confusión dentro del LLM. Es tan importante definir claramente la semántica del lenguaje como asegurarse de que el lenguaje en sí no introduzca ambigüedades que degraden el rendimiento o precisión del LLM. Por ejemplo, el prompt "siempre que separe dos cosas con comas, significa que la primera cosa precede a la segunda" probablemente creará un potencial significativo para la ambigüedad y generará el potencial de semánticas inesperadas si se utiliza puntuación con comas en el prompt.

Para mostrar el potencial de confusión, ChatGPT advertirá al usuario y potencialmente no podrá realizar una asignación específica de un símbolo o término a un nuevo significado. Por ejemplo, si se da el siguiente prompt a ChatGPT: 

> "Cuando digo “a”, me refiero a Marie Antoinette"

responderá que este prompt crea demasiada confusión ya que “a” es un artículo indefinido y se usa comúnmente, como se muestra a continuación:

> "Referirse a Marie Antoinette usando “a” podría causar confusión, ya que “a” es un artículo indefinido comúnmente utilizado para referirse a un sustantivo que no ha sido mencionado antes. Podría ser más claro usar su nombre, “Marie Antoinette”, o un pronombre como “ella” para referirse a ella. Además, usar contexto para establecer a quién te refieres también puede ayudar a evitar confusiones en la conversación."

En general, un LLM funcionará mejor con datos en los que fue entrenado. Por lo tanto, cuando una notación existente está disponible, pero quizás no sea el significado dominante, el Patrón de Creación de Meta Lenguaje puede proporcionar contexto para delimitar el significado del símbolo y mejorar la precisión y utilidad de la salida. Por ejemplo, el símbolo “→” transmite información ligeramente diferente en gráficos y en lógica proposicional. La declaración “p → q, q → p” puede tener sentido, pero solo si al LLM se le da el contexto adecuado a través de un prompt de Creación de Meta Lenguaje.

Aunque la Creación de Meta Lenguaje es un patrón poderoso, debe usarse con cuidado, particularmente al describir conceptos que de otro modo podrían ser difíciles de describir con precisión o de manera concisa. Estos tipos de prompts son, por lo tanto, mejor utilizados en sesiones de conversación completamente nuevas. Usar un solo meta-lenguaje por sesión de conversación también puede ser una mejor práctica, ya que evita el potencial de semánticas conflictivas o inesperadas aplicadas a la conversación con el tiempo.