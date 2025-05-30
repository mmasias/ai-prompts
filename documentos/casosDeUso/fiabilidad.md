<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Caso de Uso > Fiabilidad

> Basado en un caso propuesto por [microsiervos.com](https://www.microsiervos.com/archivo/leyendas-urbanas/quejas-brecha-generacional-sumerios-leyenda-urbana.html)

## ¿Por qué?

Los modelos de lenguaje de gran escala (LLMs) se han convertido en herramientas ampliamente utilizadas para obtener información sobre diversos temas, incluyendo hechos históricos y culturales. Sin embargo, estos sistemas presentan una tendencia preocupante a generar información aparentemente precisa y detallada que, en realidad, puede ser fabricada o incorrecta. Este fenómeno, conocido como "alucinación", representa un desafío significativo para los usuarios que confían en estas herramientas para la investigación o el aprendizaje.

## ¿Qué?

Se trata de un análisis comparativo de las respuestas de diversos modelos de lenguaje frente a una pregunta específica sobre la existencia de un supuesto texto mesopotámico donde un anciano se queja de los jóvenes y la pérdida de valores tradicionales. Este caso ejemplifica el fenómeno de "verificación de fiabilidad", un enfoque metodológico que permite evaluar la precisión, consistencia y honestidad epistemológica de los LLMs cuando se enfrentan a consultas sobre hechos históricos con evidencia limitada o ambigua.

La divergencia en las respuestas ilustra cómo los diferentes modelos manejan la incertidumbre y la evidencia histórica, revelando patrones de comportamiento que van desde la afirmación categórica sin matices hasta el reconocimiento explícito de las limitaciones del conocimiento disponible.

## ¿Para qué?

Este análisis comparativo permite:

1. Identificar qué modelos de lenguaje tienden a presentar mayor cautela frente a afirmaciones históricas sin evidencia sólida, proporcionando a los usuarios criterios para seleccionar herramientas más fiables.
1. Evidenciar los riesgos de confiar ciegamente en las respuestas de los LLMs para investigación histórica o académica, promoviendo un uso más crítico y consciente de estas tecnologías.
1. Analizar los patrones de "alucinación" y fabricación de detalles específicos (fechas, ubicaciones, nombres de artefactos) que pueden dotar a la información falsa de una apariencia de legitimidad y precisión.
1. Establecer mejores prácticas para el diseño de prompts que reduzcan la probabilidad de obtener información fabricada, incentivando respuestas que reflejen adecuadamente el nivel de certeza sobre hechos históricos.
1. Demostrar la importancia de contrastar la información proporcionada por los LLMs con fuentes académicas verificables, especialmente en temas históricos y culturales.

## ¿Cómo?

***¿Qué me puedes decir acerca de un texto muy antiguo encontrado en Mesopotamia, de miles de años, escrito por un anciano quejándose de la pérdida de valores tradicionales de los jóvenes? ¿Es real o un mito o leyenda urbana?***

> La discrepancia entre las respuestas proporcionadas por diferentes modelos de lenguaje ante una misma consulta histórica evidencia la falta de consistencia y fiabilidad en la información generada. Algunos modelos afirman la existencia de textos antiguos específicos con gran seguridad, mientras que otros reconocen las limitaciones de la evidencia disponible, lo que genera confusión y puede llevar a la propagación de información errónea.

### Transcripciones

|Motor|Comentario|
|-|-|
[ChatGPT-3.5](https://chatgpt.com/share/26ece80f-d1ce-4f5d-acb4-e52625f7f5d7)|"Es real!"
[ChatGPT-4](https://chatgpt.com/share/5fc2dc59-31f4-42e1-9b92-37ec7a6ffdb3)|"parece ser más un mito moderno que un hecho histórico verificable."
[ChatGPT-4o](https://chatgpt.com/share/5a0f445c-2223-4784-a025-6d28b17111d5)|" es probablemente más un mito o una leyenda urbana que un hecho documentado."
[Perplexity](https://www.perplexity.ai/search/Qu-me-puedes-t1UAfMeHTNeTaycrshgwBA#0)|"Este texto data de alrededor del 2200 a.C. y es considerado una obra real y no una leyenda urbana. Es una pieza valiosa de la literatura antigua que refleja preocupaciones y valores atemporales sobre la conducta y la moralidad." **+fuentesDeInformación**
[Claude]()|"Sí, existe un texto muy antiguo de Mesopotamia que refleja las quejas de un anciano sobre la decadencia de valores en la juventud de su época. Se conoce como la "Tablilla de las Quejas" o la "Tablilla Babilónica de la Decadencia de la Juventud. Esta tablilla de arcilla data aproximadamente del año 1800 a.C. y fue descubierta en las ruinas de la antigua ciudad sumeria de Nippur, ubicada en la actual Iraq. Está escrita en lengua acadia con escritura cuneiforme."
[Gemini](https://g.co/gemini/share/76bdbf14d992)|Sin embargo, la existencia de tal texto como un hecho histórico concreto no está comprobada. No hay evidencia arqueológica o documental que respalde la existencia de un texto específico con estas características.
[NeuroFlash](https://app.neuro-flash.com/ai-writer/8fe3d9d7d5632fb0f73ef481b04e54b5/preview)|no se trata de un mito o leyenda urbana, sino de registros reales de antigüedad que demuestran que las preocupaciones generacionales han existido desde tiempos remotos.
[Copilot](https://copilot.microsoft.com/sl/cGU1zZ7rPlQ)|El escrito al que te refieres es real. Se trata de una tablilla de arcilla de la antigua Mesopotamia, concretamente de la civilización sumeria, que data aproximadamente del 2000 a.C. En este texto, un anciano expresa su preocupación por la pérdida de valores tradicionales y el comportamiento de los jóvenes. Este documento es considerado una de las primeras quejas generacionales registradas en la historia, mostrando que la preocupación por las nuevas generaciones es un tema atemporal.

|Buenas prácticas|& Reflexiones
|-|-|
|Preferir modelos que expresan incertidumbre|Los modelos que reconocen los límites de la evidencia disponible tienden a proporcionar información más fiable sobre temas históricos ambiguos.
|Desconfiar de detalles específicos sin fuentes|La invención de nombres concretos ("Tablilla de las Quejas"), fechas precisas y ubicaciones específicas suele ser indicativa de alucinación.
|Verificar con múltiples fuentes|La divergencia entre respuestas evidencia la necesidad de contrastar la información con fuentes académicas reconocidas.
|Formular prompts de seguimiento|Cuando un modelo afirma algo con certeza, es recomendable solicitar referencias específicas o preguntar sobre la base de su afirmación.
|Reconocer patrones temporales|Los modelos más recientes o con capacidades avanzadas no necesariamente ofrecen mayor fiabilidad histórica, como se observa en las respuestas de diferentes versiones de ChatGPT.
