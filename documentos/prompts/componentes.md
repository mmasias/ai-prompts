<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Prompts

## Componentes

|![](/documentos/imagenes/modelosUML/promptRecetaComponentes.svg)
|-
Dependiendo del modelo de IA y de la tarea en cuestión, puede no ser necesario que un prompt posea explícitamente cada componente.
De hecho, algunos pueden ser opcionales, aunque es una buena práctica incluir todos, o al menos tomar consciencia de todos durante el diseño del prompt.
Aquí es donde, dependiendo del modelo o sistema de IA, el ingeniero puede aplicar su criterio al momento de valorar la categorización de los componentes y elementos en primarios y secundarios.

### Tarea

La tarea se refiere a la **acción o proceso específico que un modelo de inteligencia artificial (IA) está entrenado para realizar** en respuesta a un prompt. Es la forma más simple de un prompt. La tarea es el objetivo al que se está dirigiendo al modelo de IA. Esta tarea puede variar desde responder una pregunta hasta generar contenido creativo, crear una imagen o escribir una historia o componer música. Como se mencionó, las tareas pueden ser implícitas en el modelo y no necesariamente deben ser declaradas.

> Se puede pensar en la tarea como la salida + tema. Ej. "escribe una publicación en redes sociales sobre emprendimiento".

### Instrucciones

Más allá de la tarea, se debe proporcionar a la IA instrucciones específicas para lograr el resultado deseado. Estas pueden ser simples o complejas y pueden abarcar la interacción general, los atributos y cualidades de la salida, e incluso el formato de la salida.

Las instrucciones proveen al modelo de IA un claro **mapa de ruta de lo que necesita hacer** y ayudan a que la tarea se complete correcta y eficientemente. Las instrucciones pueden abarcar el contenido que se desea que la IA incluya o desarrolle, así como cualquier cosa que se deba o no hacer, así como los pasos y/o acciones específicas que deben tomarse para completar la tarea.

Por ejemplo, si la tarea es escribir un poema, las instrucciones podrían especificar la longitud, el esquema de rima y el ritmo del poema.

> Se pueden ver las instrucciones como reglas; Ej. "el poema debe ser escrito en primera persona. Debe tener al menos 500 palabras."

### Contexto

Mientras que las instrucciones son pasos, acciones específicas o atributos de la salida que deben ser tomados para completar la tarea, el contexto se refiere a la **información o situación de fondo que rodea una tarea**. Proporciona al modelo de IA información adicional sobre la tarea y le ayuda a entender la situación y los objetivos de la tarea. El contexto puede verse como guías y no como reglas estrictas.

El contexto establece el escenario para el sistema de IA y proporciona información que le ayuda a comprender lo que buscas. Esto puede presentarse en forma de ejemplos, imágenes o semillas que le dan a la IA una mejor idea de la respuesta que esperas.

> Se puede ver el contexto como una  guía abierta a la interpretación por parte de la IA. Por ejemplo, "escribe combinando los estilos de Barack Obama y Steve Jobs".

### Entrada

Esto es particularmente importante cuando hay una materia específica para transformación. Las entradas pueden o no ser requeridas para la salida prevista. Las entradas **puede ser diversas cantidades de texto o archivos de texto en el caso de LLM** o pueden tratarse de imágenes para editar o sobre las que construir, como en "inpainting" y "outpainting", por ejemplo, en el arte generativo y modelos de difusión.

### Parámetros

Son elementos o variables específicas que se incluyen en el prompt mismo o se establecen previamente, gobernando o afectando directamente la salida del modelo de IA. Se trata generalmente de meta-atributos o configuraciones que probablemente no se pueden establecer de manera directa o con un lenguaje claro en el prompt.

Los parámetros pueden variar desde configuraciones simples de temperatura y probabilidad hasta configuraciones más complejas específicas para cada modelo de IA. Hay que tener en cuenta que los parámetros y configuraciones disponibles pueden variar enormemente entre sistemas de IA, por lo que es importante familiarizarse y experimentar para encontrar la combinación correcta. En algunos modelos de IA, los parámetros pueden usarse para definir instrucciones establecidas, como el parámetro "--no" en MidJourney.

## Ejemplos

> *Un contable está revisando el estado de flujo de caja de una empresa y necesita ayuda para evaluar la salud financiera, identificando áreas de riesgo y oportunidades para mejorar la gestión de efectivo.*

| | |
|-|-|
**Prompt** | Ayúdame a analizar un estado de flujo de caja para identificar posibles problemas de liquidez y oportunidades de optimización de efectivo.
**Tarea** | Ayúdame a analizar un estado de flujo de caja.
**Instrucciones** | Identifica posibles problemas de liquidez y sugiere oportunidades para optimizar el flujo de efectivo.
**Contexto** | 
**Entrada** | Estado de flujo de caja de la empresa.
**Parámetros** | -

> *Un gestor de proyectos está iniciando la redacción de un proyecto de investigación y necesita una introducción que establezca el objetivo y la relevancia del estudio en el contexto de la sostenibilidad.*

| | |
|-|-|
**Prompt** | Ayúdame a redactar una introducción clara y persuasiva para un proyecto de investigación sobre sostenibilidad en la industria alimentaria.
**Tarea** | Ayúdame a redactar una introducción para un proyecto de investigación.
**Instrucciones** | Debe ser clara, persuasiva y enfocada en la sostenibilidad en la industria alimentaria.
**Contexto** | 
**Entrada** | -
**Parámetros** | -

> *Empresarios que necesitan entender cómo se están posicionando las empresas competidoras en el mercado de servicios de logística para ajustar sus propias estrategias de negocio y detectar oportunidades de mejora.*

| | |
|-|-|
**Prompt** | Proporcióname un análisis de la competencia en el sector de servicios de logística, enfocándote en las estrategias de precios, servicios diferenciados y presencia digital de las principales empresas.
**Tarea** | Proporcióname un análisis de la competencia en el sector de servicios de logística.
**Instrucciones** | Enfócate en las estrategias de precios, servicios diferenciados y la presencia digital de las principales empresas del sector.
**Contexto** | 
**Entrada** | Datos de mercado, informes de competencia, sitios web de competidores.
**Parámetros** | -


|[💬🤖](https://chat.openai.com/share/07120d38-6bd2-4e00-a0dd-5c407e4fbde8)|Redacción de un artículo|
|-|-|
|**Prompt**|Utiliza la siguiente idea para escribir un artículo motivacional sobre la atención plena (mindfulness) para emprendedores. Enfatiza la importancia de la claridad mental y la paz interior para el éxito en los negocios. Aquí está la idea: ser emprendedor se trata de servir.|
Tarea|Utiliza las siguientes ideas para escribir un artículo motivacional sobre la atención plena para emprendedores.
Instrucciones|Enfatiza la importancia de la claridad mental y la paz interior para el éxito en los negocios.
Contexto|Escribe para una audiencia de emprendedores aspirantes y establecidos.
Entrada|Ser emprendedor se trata de servir.
Parámetros|-

> [🤔@ChatGPT](https://chat.openai.com/share/1a7ea22d-f6e8-4822-9aa0-7a4038ebe01b)

|[💬🤖](https://chat.openai.com/share/a2631470-7997-4b3a-b157-9ad8815761f4)|Lista y consejos
|-|-|
**Prompt**|Crea una lista de consejos prácticos para emprendedores aspirantes usando la siguiente cita. Enfatiza la importancia de servir a los demás y causar un impacto positivo. Escribe para una audiencia de millennials que están pasando por dificultades y están interesados en iniciar un negocio. Aquí está la cita: Convierte tu pasión en un negocio exitoso poniendo siempre las necesidades de los demás primero.
Tarea|Crea una lista de consejos prácticos para emprendedores aspirantes.
Instrucciones|Enfatiza la importancia de servir a los demás y causar un impacto positivo.
Contexto|Escribe para una audiencia de millennials en dificultades interesados en iniciar un negocio.
Entrada|Convierte tu pasión en un negocio exitoso poniendo siempre las necesidades de los demás primero.
Parámetros|-

|[💬🤖](https://chat.openai.com/share/3d3d928f-29e2-47af-bb65-57717d4cffb4)|Ayuda con fórmulas|
|-|-|
**Prompt**|Proponme fórmulas de Google Sheets que permita copiar todas las filas de la "hoja1" donde la columna “A” contenga la palabra “iPhone”.
Tarea|Proponme fórmulas de Google Sheets
Instrucciones|que permitan copiar todas las filas de la "hoja1" donde la columna “A” contenga la palabra “iPhone”.
Contexto|-
Entrada|-
Parámetros|-

|[💬🤖](https://chat.openai.com/share/182ff90a-6c31-46c0-b069-25e93553303f)|Ideas|
|-|-|
**Prompt**|Propón ideas novedosas para un artículo sobre *Ingeniería de Prompts de IA - el trabajo del futuro* en un tono emocionante, optimista y esperanzador. Los objetivos potenciales para esta publicación podrían ser:<br>- Abrir los ojos de las personas demostrando que el status quo está equivocado.<br>- Compartir una solución a un problema difícil.<br>- Destilar un tema abrumador en algo accesible.<br>- Contar una historia emocionante y emocional que imparta una lección.<br>- Articular algo en lo que todos están pensando pero nadie está diciendo. Atravesar el ruido.<br>- Identificar tendencias clave sobre un tema.<br>- Luego usarlas para predecir el futuro.<br>- Aportar percepciones originales a un campo a través de la investigación y experimentación.|
Tarea|Propón ideas novedosas para un artículo sobre Ingeniería de Prompts de IA - el trabajo del futuro.
Instrucciones|En un tono emocionante, optimista y esperanzador.
Contexto|Los objetivos potenciales para esta publicación podrían ser:<br>- Abrir los ojos de las personas demostrando que el status quo está equivocado.<br>- Compartir una solución a un problema difícil.<br>- Destilar un tema abrumador en algo accesible.<br>- Contar una historia emocionante y emocional que imparta una lección.<br>- Articular algo en lo que todos están pensando pero nadie está diciendo. Atravesar el ruido.<br>- Identificar tendencias clave sobre un tema.<br>- Luego usarlas para predecir el futuro.<br>- Aportar percepciones originales a un campo a través de la investigación y experimentación.
Entrada|-
Parámetros|-

|[💬🤖](https://chat.openai.com/share/95ef598c-f241-4826-af8c-cd5f913322f2)|Redacción de un artículo, II
|-|-|
**Prompt**|Escribe un artículo de blog sobre la vida sostenible en el siglo XXI. El artículo debe tener al menos 2500 palabras. Cada punto debe estar claramente indicado con encabezados y los puntos deben fluir lógicamente. El artículo debe estar escrito en un tono amigable, inspirador, usando lenguaje natural y en tono conversacional. Menciona el uso de energía alternativa y energía nuclear. No uses jerga. No uses términos demasiado técnicos. Escribe desde la perspectiva de un ecologista. Este artículo se publicará en Readers Digest. La audiencia del artículo son madres liberales. Escribe para el arquetipo de marca ***[El Amante](https://scribalo.com/scribablog/arquetipos-jung-personalidad-marca/)***: forma relaciones sensuales, espirituales y de compañía, y crea momentos íntimos para su audiencia. La escritura debe ser apasionada, sensual e íntima. Utiliza un lenguaje emotivo que promueva el romance, el deseo y la conexión emocional.|
Tarea|Escribe un artículo de blog sobre la vida sostenible en el siglo XXI.
Instrucciones|El artículo debe tener al menos 2500 palabras. Cada punto debe estar claramente indicado con encabezados y los puntos deben fluir lógicamente. El artículo debe estar escrito en un tono amigable, inspirador, usando lenguaje natural y en tono conversacional. Menciona el uso de energía alternativa y energía nuclear. No uses jerga. No uses términos demasiado técnicos.
Contexto|Escribe desde la perspectiva de un ecologista. Este artículo se publicará en Readers Digest. La audiencia del artículo son madres liberales. Escribe para el arquetipo de marca El Amante: forma relaciones sensuales, espirituales y de compañía, y crea momentos íntimos para su audiencia. La escritura debe ser apasionada, sensual e íntima. Utiliza un lenguaje emotivo que promueva el romance, el deseo y la conexión emocional.
Entrada|-
Parámetros|-

||Imágenes
|-|-|
**Prompt**|La oscuridad primordial personificando a un dios griego, Erebus vistiendo ropa antigua griega, galaxia con sistema solar como fondo, [iluminación de estudio suave, contraluz, fondo oscuro] --ar 2:3 --upbeta --q 2 --v 4|
Tarea|Crear una imagen (implícita)
Instrucciones|iluminación de estudio suave, contraluz, fondo oscuro
Contexto|La oscuridad primordial personificando a un dios griego, Erebus vistiendo ropa antigua griega, galaxia con sistema solar como fondo,
Entrada|-
[Parámetros](https://docs.midjourney.com/docs/parameter-list)| --ar 2:3 --upbeta --q 2 --v 4
<!-- TODO: #22 promptear esto en midjourney o en bluewillow -->
