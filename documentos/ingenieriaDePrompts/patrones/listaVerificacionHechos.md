<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/documentos/prompts/README.md)|[Ingeniería de Prompts](/documentos/ingenieriaDePrompts/README.md)|[Patrones](/documentos/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/documentos/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Patrón de Lista de verificación de hechos

## Intención y Contexto

La intención de este patrón es asegurarse de que el LLM produzca una lista de hechos que estén presentes en la salida y formen una parte importante de las declaraciones en la salida. Esta lista de hechos ayuda a informar al usuario sobre los hechos (o suposiciones) en los que se basa la salida. Luego, el usuario puede realizar la diligencia debida adecuada sobre estos hechos/suposiciones para validar la veracidad de la salida.

## Motivación

Una debilidad actual de los LLMs (incluido ChatGPT) es que a menudo generan rápidamente texto convincente que es factualmente incorrecto. Estos errores pueden adoptar diversas formas, desde estadísticas falsas hasta números de versión no válidos para dependencias de bibliotecas de software. Sin embargo, debido a la naturaleza convincente de este texto generado, los usuarios pueden no realizar la diligencia debida adecuada para determinar su precisión.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Genera un conjunto de hechos que están contenidos en la salida.
El conjunto de hechos debe insertarse en un punto específico en la salida.
El conjunto de hechos debe ser los hechos fundamentales que podrían socavar la veracidad de la salida si alguno de ellos es incorrecto.

Un punto de variación en este patrón es dónde se muestran los hechos. Dado que los hechos pueden ser términos con los que el usuario no esté familiarizado, es preferible que la lista de hechos aparezca después de la salida. Esta ordenación de presentación posterior permite al usuario leer y comprender las declaraciones antes de ver qué declaraciones deben ser verificadas. El usuario también puede determinar hechos adicionales antes de darse cuenta de que la lista de hechos al final debe ser verificada.

## Ejemplo de Implementación

Una redacción de muestra del Patrón de Lista de Verificación de Hechos se muestra a continuación:

> “De ahora en adelante, cuando generes una respuesta, crea un conjunto de hechos en los que se basa la respuesta que deben ser verificados y lista este conjunto de hechos al final de tu salida. Solo incluye hechos relacionados con la ciberseguridad.”

El usuario puede tener experiencia en algunos temas relacionados con la pregunta pero no en otros. La lista de verificación de hechos puede adaptarse a temas en los que el usuario no tiene tanta experiencia o donde hay más riesgo. Por ejemplo, en el indicativo anterior, el usuario está delimitando la lista de verificación de hechos a temas de seguridad, ya que estos son probablemente muy importantes desde una perspectiva de riesgo y pueden no ser bien comprendidos por el desarrollador. Dirigir los hechos también reduce la carga cognitiva en el usuario al listar potencialmente menos elementos para la investigación.

## Consecuencias

El patrón Lista de verificación de hechos debe emplearse siempre que los usuarios no sean expertos en el dominio para el cual están generando la salida. Por ejemplo, un desarrollador de software que revisa el código podría beneficiarse del patrón sugiriendo consideraciones de seguridad. En contraste, un experto en arquitectura de software probablemente identificará errores en las declaraciones sobre la estructura del software y no necesita ver una lista de verificación de hechos para estas salidas.

Los errores son potenciales en todas las salidas de LLM, por lo que la lista de verificación de hechos es un patrón efectivo para combinar con otros patrones, como al combinarlo con el [patrón de refinamiento de preguntas](refinamientoPreguntas.md). Un aspecto clave de este patrón es que los usuarios pueden verificarlo inherentemente contra la salida. En particular, los usuarios pueden comparar directamente la lista de verificación de hechos con la salida para verificar que los hechos enumerados en la lista de verificación de hechos realmente aparezcan en la salida. Los usuarios también pueden identificar cualquier omisión de la lista. Aunque la lista de verificación de hechos también puede tener errores, los usuarios a menudo tienen suficiente conocimiento y contexto para determinar su integridad y precisión en relación con la salida.

Una advertencia del patrón de lista de verificación de hechos es que solo se aplica cuando el tipo de salida es susceptible de verificación de hechos. Por ejemplo, el patrón funciona cuando se le pide a ChatGPT que genere un archivo "requirements.txt" de Python, ya que enumerará las versiones de las bibliotecas como hechos que deben ser verificados, lo cual es útil ya que las versiones comúnmente tienen errores. Sin embargo, ChatGPT se negará a generar una lista de verificación de hechos para una muestra de código e indicará que esto es algo que no puede verificar, aunque el código pueda tener errores.
