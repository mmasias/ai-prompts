<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Mejores prácticas

<div align=right>

> [*Sí, pero...*](consideraciones.md)

</div>

<div align=center>
  
`C·c³ = Creatividad × (claro × concreto × conciso)`

*[Manifiesto de las virtudes del prompting](8virtudesDelPrompting.md)*

</div>

|C³|Claro|Concreto|Conciso|
|-|-|-|-|
|**Definición**|Sin ambigüedades ni confusiones|Específico y bien delimitado|Breve y directo|
|**Ejemplo malo**|"Haz algo creativo"|"Escribe sobre animales"|"Analiza exhaustivamente todos los aspectos posibles de la economía mundial"|
|**Ejemplo bueno**|"Escribe un poema"|"Escribe un haiku sobre un gato siamés"|"Resume en 3 puntos las causas de la inflación en 2023"|
|**Por qué funciona**|El modelo sabe exactamente qué tipo de contenido crear|El modelo tiene parámetros precisos para trabajar|El modelo tiene un alcance definido y manejable|

## Instrucciones claras

La precisión en la interacción con los modelos GPT es esencial. Si busca concisión, especifique la longitud deseada de la respuesta. Si busca profundidad, pida una explicación detallada. Proporcione ejemplos para contextualizar sus consultas y no dude en delinear claramente las etapas o pasos si lo que busca es un proceso. 

Recuerde: los GPT trabajan mejor cuando las instrucciones son claras y específicas. Cuanto más directo y preciso sea al formular su consulta, más acertada y ajustada será la respuesta del modelo.

|Tácticas|En un ejemplo|
|-|-|
[Incluya detalles en su consulta para obtener respuestas más relevantes.](incluyaDetalles.md)|En lugar de "¿Cómo puedo incrementar la visibilidad de mi marca?", pregunte "¿Cómo puedo incrementar la visibilidad de mi marca de cosméticos naturales en redes sociales?".
[Pídale al modelo que adopte una personalidad.](adoptarPersonalidad.md)|En lugar de "Necesito consejos sobre presentaciones", pregunte "Necesito consejos sobre cómo hacer presentaciones para ejecutivos senior".
[Utilice delimitadores para indicar claramente distintas partes de la entrada.](useDelimitadores.md)|"Explica: a) el concepto de branding, b) su importancia en el mercado actual, y c) ejemplos de marcas exitosas".
[Especificar los pasos necesarios para completar una tarea.](especificarPasos.md)|En lugar de "¿Cómo puedo implementar una campaña de marketing?", pregunte "¿Cuáles son los pasos detallados para planificar, ejecutar y evaluar una campaña de marketing para un producto nuevo?".
[Proporcione ejemplos.](proporcioneEjemplos.md)|En lugar de "¿Qué es el branding?", pregunte "¿Qué es el branding? Por ejemplo, cómo Coca-Cola ha construido su marca a lo largo del tiempo".
[Especifique la longitud deseada de la salida.](expliciteLongitudRespuesta.md)|"Describe las tendencias actuales en publicidad digital en un párrafo apto para incluir en una presentación"

## Proporcionar texto de referencia

Al interactuar con modelos GPT, es crucial ser conscientes de su capacidad para generar respuestas basadas en patrones de datos, lo que podría derivar en respuestas inventadas. Al igual que un estudiante puede beneficiarse de una hoja de apuntes para afinar sus respuestas en un examen, proporcionar un texto de referencia al GPT no solo canaliza la respuesta hacia una fuente específica, sino que también puede aumentar la precisión y autenticidad de la información obtenida.

|Tácticas|En un ejemplo|
|-|-|
[Indique al modelo que responda utilizando un texto de referencia.](usoTextoReferencia.md)|"Basándote en el siguiente artículo sobre tendencias de marketing digital: [texto del artículo], ¿cuáles son los puntos clave destacados?"
[Indique al modelo que responda con citas de un texto de referencia.](pideReferencias.md)|"Analiza la percepción del público sobre la inteligencia artificial según el siguiente artículo: [texto del artículo]. Asegúrate de incluir citas que respalden tus puntos".

## ¡Divide y vencerás!

En la ingeniería, ya sea de software o de prompts, la modularidad es clave. Desglosar un problema o tarea compleja en componentes más manejables no solo simplifica el proceso sino que también mejora la precisión. Al igual que un sistema complejo se beneficia al ser dividido en módulos, las consultas dirigidas a modelos GPT muestran una mayor eficacia cuando se descomponen y estructuran. Las tareas simplificadas suelen tener menores tasas de error y, al encadenar adecuadamente estas tareas menores, se puede construir un flujo coherente que produzca respuestas más precisas y contextualizadas.

|Tácticas|En un ejemplo|
|-|-|
[Utilice la clasificación de intenciones para identificar las instrucciones más relevantes para una consulta de usuario.](clasificacionIntenciones.md)|[📓](https://chat.openai.com/share/4d93a838-8197-484e-8d19-59a2e14426ec)
[Para aplicaciones de diálogo que requieren conversaciones muy largas, resuma o filtre el diálogo anterior](repasoDeVezEnCuando.md)|[Una conversación larga, con pinceladas de contextualización](https://chat.openai.com/share/b175c472-3421-4be3-b270-aa8df5172557)
[Resuma documentos extensos por partes y construya un resumen completo de forma recursiva](resumenDeResumen.md)|

## Ayúda(le) a pensar

En la toma de decisiones y el análisis dentro de contextos especializados, es esencial aplicar un enfoque metódico y reflexivo para garantizar resultados óptimos. Por ejemplo, al diseñar una estrategia de marketing para un producto emergente, es fundamental un análisis riguroso y deliberado. Esta metodología cuidadosa no es exclusiva de los seres humanos; también es aplicable a los modelos de lenguaje como GPT. Dirigir a estos modelos hacia un proceso de razonamiento sistemático y solicitarles que reconsideren sus respuestas puede potenciar la precisión de sus contribuciones, especialmente en dominios especializados como el empresarial.

|Tácticas|En un ejemplo|
|-|-|
[Indique al modelo que encuentre su propia solución antes de apresurarse a llegar a una conclusión.](piensaGPT.md)|
[Utilice un monólogo interno o una secuencia de consultas para ocultar el proceso de razonamiento del modelo.](razonaGPT.md)|
[Pregúntele al modelo si se perdió algo en pasadas anteriores.](repasaGPT.md)|
[**Use el modo estudio para aprendizaje guiado y constructivo.**](../../casosDeUso/modoEstudio.md)|En lugar de pedir respuestas directas, solicite que la IA actúe como tutor: "Guíame para entender X, haz preguntas que me ayuden a descubrir la respuesta"|

## Bibliografía

- Basado y adaptado del artículo de OpenAI [gpt-best-practices](https://platform.openai.com/docs/guides/gpt-best-practices) 

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Ejemplos prácticos](../ejemplos.md)<br>Aplicación de conceptos|Fundamentos > Prompts > **Mejores prácticas**|[8 virtudes del prompting](8virtudesDelPrompting.md)<br>Principios fundamentales
|[Anatomía de un prompt](../anatomia.md)<br>Estructura y componentes||[Instrucciones claras](incluyaDetalles.md)<br>Técnicas específicas
|[Recetas](../recetas.md)<br>Metodología de combinación|||

<i>**Relacionado**: [Ingeniería de Prompts](../../ingenieriaDePrompts/README.md) - Técnicas avanzadas / [Casos de uso](../../casosDeUso/README.md) - Aplicaciones específicas / [Tokens](../tokens.md) - Optimización técnica</i>

</div>