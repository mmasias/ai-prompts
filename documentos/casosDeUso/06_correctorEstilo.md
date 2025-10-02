<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Caso de Uso > Corrector de Estilo

## ¿Por qué?

La calidad del contenido es esencial. ¿Cómo garantizamos que se cumpla con un manual de estilo específico en cada elemento creado?

## ¿Qué?

| | |
|-|-|
Los medios impresos, como los periódicos y las revistas, han confiado en lo que se conoce como "guías de estilo". Estas guías garantizan que la redacción se mantenga coherente en términos de tono, terminología, estructura y otros aspectos cruciales del contenido.|Tradicionalmente, el redactor jefe o editor principal ha sido el garante de que los contenidos cumplan con esta guía de estilo. Esta responsabilidad implica un análisis minucioso de cada pieza de contenido, lo que puede resultar en una tarea exhaustiva y sujeta a errores humanos.

El presente caso de uso plantea encontrar una solución que pueda evaluar automáticamente el contenido basándose en un conjunto predefinido de criterios estilísticos, abarcando desde la claridad hasta la estructuración y terminología.

## ¿Para qué?

| | |
|-|-|
Objetivo|Establecer una herramienta que garantice la uniformidad, coherencia y calidad de los artículos publicados, alineándolos con una guía de estilo preestablecida, emulando el papel del redactor jefe en un periódico tradicional.
Beneficio|Reducir tiempo y recursos humanos en la revisión y corrección, asegurando al mismo tiempo una estructura y estilo uniforme en todos los artículos.

## ¿Cómo?

### Transcripciones

|Motor|Comentario|
|-|-|
[ChatGPT](https://chat.openai.com/share/edf36184-6936-4741-847a-54ad7cda6fdc)
[Perplexity]
[Claude](https://claude.ai/chat/5f146ff5-8408-4f7a-9cea-a94c39d49bcd)|Al permitir adjuntar PDFs, se pudo adjuntar el manual de estilo oficial del periódico.
[Bard]
[NeuroFlash]

|Buenas prácticas|& Reflexiones
|-|-|
Instrucción inicial|La AI es informada desde el principio sobre cómo se desarrollará la tarea.
Lista claramente definida|Se da a la IA un conjunto claro y estructurado de criterios.
Protocolo de acción|Se establece un procedimiento específico que la IA debe seguir, incluido cómo y cuándo debe indicar que está lista, cómo evaluará y cómo indicará los resultados.
Descomposición de la tarea|Se divide la tarea en diferentes pasos, garantizando un flujo organizado y una evaluación estructurada.
Expectativas claras|Se le indica a la IA exactamente lo que se espera de ella y cómo debe comunicar sus resultados.

#### Antipatrón

*[:link:]() EJ_DE_ANTI_PATRON*

|Punto|Detalle|
|-|-|
