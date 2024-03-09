<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/prompts/README.md)|[Ingeniería de Prompts](/ingenieriaDePrompts/README.md)|[Patrones](/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Caso de Uso > Enseñanza de un estilo de redacción

## ¿Por qué?

La personalización del estilo de escritura es esencial en diversos escenarios, por ejemplo cuando una empresa quiere mantener un tono coherente en toda su comunicación o cuando un escritor desea un asistente virtual que pueda seguir su estilo. 

La capacidad de enseñar a una IA a adaptarse y reflejar estilos particulares puede ser inmensamente valiosa.

## ¿Qué? 

El proceso de entrenamiento y adaptación de una inteligencia artificial para que imite un estilo de escritura específico se apoya en tres momentos:

| | |
|-|-|
Definición del protocolo|Se establecen las bases de comunicación y las instrucciones claras que la inteligencia artificial debe seguir. En este momento, se sientan las pautas que guiarán todo el proceso, asegurando que la máquina entienda el propósito y la estructura de la actividad que va a realizar.
Internalización|Se trata de la fase de absorción y comprensión por parte de la IA. Aquí, la máquina se familiariza con los patrones, tono, y estilos específicos de la redacción presentada. Es un proceso de reconocimiento y adaptación donde el sistema se "empapa" de la esencia de los textos suministrados.
Emulación|Una vez internalizada la esencia, el sistema procede a replicarla. Esta fase se centra en la producción, en la creación de contenido nuevo que, aunque original, se asemeja en tono y estilo a lo que se le enseñó previamente.

## ¿Para qué?

- Facilitamos un aprendizaje más interactivo y paso a paso para el modelo.
- Respuestas consistentes con el tono y estilo de una empresa o individuo.


## ¿Cómo?

### Transcripciones 

|Motor|Comentario
|-|-|
[ChatGPT](https://chat.openai.com/share/584af1d9-e459-4fc3-b571-bf8a3c317d66)|[V2](https://chat.openai.com/share/8fc8b4ff-05b4-4d3f-8a45-d2fa1ebf7e7a)
[Perplexity](https://www.perplexity.ai/search/4b47fa6d-3aeb-43e2-aabc-49c04f8bd925?s=c)|[Segundo intento](https://www.perplexity.ai/search/7d8ee161-fac4-401f-9668-a06baf2eaf97?s=c) / [Tercer intento](https://www.perplexity.ai/search/dc12f7d7-074a-406d-b900-c553b4c1ec14?s=c)
[Claude](https://claude.ai/chat/659fe307-aa6d-464a-b665-7681019d6e13)
[Bard](https://g.co/bard/share/031c9cf35f98)|[V2](https://g.co/bard/share/59632753bce2)
[NeuroFlash](https://app.neuro-flash.com/ai-writer/48f76c1007e11d7ebdc55f5c86a629df/preview)

|Buenas prácticas|& Reflexiones
|-|-|
Instrucción Clara y Directa|"Actúa como un redactor profesional" establece de inmediato el marco de la tarea
Secuenciación Explícita|El uso de una estructura numerada (fases 1, 2 y 3) proporciona una secuencia clara de acciones que la IA debe seguir. Esto ayuda (o debería) a que el modelo sepa qué esperar y en qué orden.
Anclaje Contextual|Mediante la descripción del proceso de aprender e imitar un estilo de escritura, se está anclando el contexto del prompt. La IA sabe que debe prestar atención a los textos de ejemplo **no solo por su contenido, sino también por su estilo y tono**.
Respuestas Esperadas|Al especificar respuestas como "COMIENZO" y "SIGUIENTE", se establece un patrón de interacción. Esto asegura que la IA sabe cómo debe responder en ciertas etapas del proceso.
Limitación de Respuestas|Con la instrucción de que la IA sólo puede decir algo diferente cuando se indique "TERMINADO", se está restringiendo su capacidad de respuesta. Esto evita que la IA se desvíe del proceso deseado. O al menos eso se intenta.
Solicitud Final Explícita|En la fase de emulación, se le pide a la IA que analice y luego produzca textos basados en el estilo aprendido. Esta es una instrucción clara que indica qué se espera que haga la IA al final del proceso.

#### Antipatrón

*[:link:]() Por favor, revise algunos correos electrónicos que he escrito y trate de adaptar un estilo similar. Observe las características esenciales y haga lo necesario para emular este estilo. Si surge algún inconveniente, informe debidamente.*

|Punto|Detalle|
|-|-|
Falta de Claridad|No concreta qué se espera exactamente de la IA en términos de acciones.
Ambigüedad|"Trate de adaptar un estilo similar" y "haga lo necesario" son instrucciones vagas.
Falta de Estructura|No se define un orden o secuencia de tareas que la IA deba realizar.
Falta de Respuestas Esperadas|No se indica cómo debe responder o interactuar la IA mientras procesa los correos.

## Correos generados por diferentes AI

A la petición de ***Escribe un correo corto en el que des la bienvenida al programa en el que abordaremos la ingeniería de prompts. En tono formal cercano.***

### ChatGPT

    Hola a todos,

    Es un placer darles la bienvenida al programa sobre ingeniería de prompts. Esta temática, aunque técnica, es esencial para comprender cómo las interacciones con modelos de lenguaje pueden ser afinadas y optimizadas. Espero que juntos podamos descubrir y compartir experiencias valiosas en este viaje. Como siempre, estoy aquí para cualquier consulta o inquietud que surja.

    ¡Vamos a ello!

    Un saludo,

    Manuel.

### Claude

    Estimados participantes:

    ¡Bienvenidos al programa sobre ingeniería de prompts! Me alegra mucho que se hayan inscrito y estén listos para sumergirse en este fascinante tema.

    Durante las próximas semanas exploraremos juntos las posibilidades que ofrece la ingeniería de prompts para mejorar la interacción con los modelos de lenguaje. Veremos cómo diseñar prompts efectivos, iterar y optimizar según los resultados, y aplicar buenas prácticas para prompts robustos y consistentes.

    Esta materia es clave en el campo de la IA generativa, así que me emociona mucho poder compartir mis conocimientos con ustedes. Estoy seguro de que al final del programa saldrán con nuevas habilidades valiosas para sus proyectos.

    Si tienen cualquier duda o consulta, no duden en escribirme. Estoy para ayudarles en lo que necesiten mientras avanzamos juntos en este apasionante recorrido.

    ¡Nos vemos en la primera sesión! Un saludo cordial,

    [Tu nombre]

### NeuroFlash

    Estimados participantes,

    Es un placer darles la más cordial bienvenida al programa dedicado a la ingeniería de prompts. En este emocionante viaje exploraremos las profundidades y posibilidades de este fascinante campo. Estoy encantado de contar con cada uno de ustedes, quienes se sumergirán en el apasionante mundo de la creación y optimización de prompts.

    Durante este programa, nos adentraremos en técnicas avanzadas y estrategias innovadoras para maximizar el potencial de nuestros modelos de lenguaje. A través de sesiones interactivas, ejercicios prácticos y discusiones enriquecedoras, estaremos inmersos en un entorno de aprendizaje colaborativo, donde el intercambio de conocimientos y experiencias será fundamental.

    Mi compromiso es brindarles una experiencia formativa de alta calidad, proporcionándoles las herramientas y los conocimientos necesarios para que puedan dominar la ingeniería de prompts. Estaré a su disposición para responder preguntas, brindar orientación y acompañarlos en cada paso de este fascinante recorrido.

    Como punto de partida, les invito a explorar los materiales de estudio y a familiarizarse con los conceptos clave relacionados con la ingeniería de prompts. Estoy seguro de que esta aventura intelectual será recompensada con nuevos conocimientos, perspectivas renovadas y un crecimiento profesional significativo.

    Una vez más, les doy la más cálida bienvenida a este programa de ingeniería de prompts. Espero con entusiasmo los próximos encuentros y el intercambio de ideas que se avecina.

    ¡Adelante y que comience esta apasionante travesía!

    Atentamente,

    [Nombre]
