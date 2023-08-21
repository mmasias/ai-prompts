# Prompts

## Componentes

### Tarea

La tarea se refiere a la acción o proceso específico que un modelo de inteligencia artificial (IA) está entrenado para realizar en respuesta a un prompt. Es la forma más simple de un prompt. La tarea es el objetivo al que se está dirigiendo al modelo de IA. Esta tarea puede variar desde responder una pregunta hasta generar contenido creativo, crear una imagen o escribir una historia o componer música. Como se mencionó, las tareas pueden ser implícitas en el modelo y no necesariamente deben ser declaradas.

> Se puede pensar en la tarea como la salida + tema. Ej. "escribe una publicación en redes sociales sobre emprendimiento".

### Instrucciones

Más allá de la tarea, se debe proporcionar a la IA instrucciones específicas para lograr el resultado deseado. Estas pueden ser simples o complejas y pueden abarcar la interacción general, los atributos y cualidades de la salida, e incluso el formato de la salida.

Las instrucciones proveen al modelo de IA un claro mapa de ruta de lo que necesita hacer y ayudan a que la tarea se complete correcta y eficientemente. Las instrucciones pueden abarcar el contenido que se desea que la IA incluya o desarrolle, así como cualquier cosa que se deba o no hacer, así como los pasos y/o acciones específicas que deben tomarse para completar la tarea.

Por ejemplo, si la tarea es escribir un poema, las instrucciones podrían especificar la longitud, el esquema de rima y el ritmo del poema.

> Se pueden ver las instrucciones como reglas; Ej. "el poema debe ser escrito en primera persona. Debe tener al menos 500 palabras."

### Contexto

Mientras que las instrucciones son pasos, acciones específicas o atributos de la salida que deben ser tomados para completar la tarea, el contexto se refiere a la información o situación de fondo que rodea una tarea. Proporciona al modelo de IA información adicional sobre la tarea y le ayuda a entender la situación y los objetivos de la tarea. El contexto puede verse como guías y no como reglas estrictas.

El contexto establece el escenario para el sistema de IA y proporciona información que le ayuda a comprender lo que buscas. Esto puede presentarse en forma de ejemplos, imágenes o semillas que le dan a la IA una mejor idea de la respuesta que esperas.

> Se puede ver el contexto como una  guía abierta a la interpretación por parte de la IA. Por ejemplo, "escribe combinando los estilos de Barack Obama y Steve Jobs".

Dependiendo del modelo de IA y de la tarea en cuestión, puede no ser necesario que un prompt posea explícitamente cada componente. De hecho, algunos pueden ser opcionales, aunque consideremos una buena práctica incluir todos. Aquí es donde, dependiendo del modelo o sistema de IA, el ingeniero puede aplicar su criterio al momento de valorar la categorización de los componentes y elementos en primarios y secundarios.

### Parámetros

Son elementos o variables específicas que se incluyen en el prompt mismo o se establecen previamente, gobernando o afectando directamente la salida del modelo de IA. Se trata generalmente de meta-atributos o configuraciones que probablemente no se pueden establecer de manera directa o con un lenguaje claro en el prompt.

Los parámetros pueden variar desde configuraciones simples de temperatura y probabilidad hasta configuraciones más complejas específicas para cada modelo de IA. Hay que tener en cuenta que los parámetros y configuraciones disponibles pueden variar enormemente entre sistemas de IA, por lo que es importante familiarizarse y experimentar para encontrar la combinación correcta. En algunos modelos de IA, los parámetros pueden usarse para definir instrucciones establecidas, como el parámetro "--no" en MidJourney.

### Entrada

Esto es particularmente importante cuando hay una materia específica para transformación. Las entradas pueden o no ser requeridas para la salida prevista. Las entradas pueden incluir imágenes para editar o sobre las que construir, como en "inpainting" y "outpainting", por ejemplo, en el arte generativo y modelos de difusión, o puede ser diversas cantidades de texto o archivos de texto en el caso de LLM.

## Ejemplos

||Utiliza la siguiente idea para escribir un artículo motivacional sobre la atención plena (mindfulness) para emprendedores. Enfatiza la importancia de la claridad mental y la paz interior para el éxito en los negocios. Aquí está la idea: ser emprendedor se trata de servir.|
|-|-|
Tarea|Utiliza las siguientes ideas para escribir un artículo motivacional sobre la atención plena para emprendedores.
Instrucciones|Enfatiza la importancia de la claridad mental y la paz interior para el éxito en los negocios.
Contexto|Escribe para una audiencia de emprendedores aspirantes y establecidos.
Entrada|Ser emprendedor se trata de servir.
Parámetros|-