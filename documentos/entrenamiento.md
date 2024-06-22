# Acerca del *carácter* de Claude

> Traducido del [artículo original](https://www.anthropic.com/research/claude-character)

| **Traducido por [ChatGPT](https://chatgpt.com/share/3b370706-b105-452b-9170-cda194641b01)** | **Traducido por [Claude](https://claude.ai/chat/f94a162c-616b-4d26-ac93-7b13cb9a2617)** |
|---------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
|**El carácter de Claude**|**El carácter de Claude**|
| Las empresas que desarrollan modelos de IA generalmente los entrenan para evitar decir cosas dañinas y para no asistir en tareas perjudiciales. El objetivo de esto es entrenar modelos para comportarse de maneras "inofensivas". Pero cuando pensamos en el carácter de aquellas personas que realmente admiramos, no solo pensamos en la evitación del daño. Pensamos en quienes son curiosos sobre el mundo, se esfuerzan por decir la verdad sin ser crueles y pueden ver múltiples lados de un problema sin volverse excesivamente confiados o demasiado cautelosos en sus opiniones. Pensamos en quienes son oyentes pacientes, pensadores cuidadosos, conversadores ingeniosos y muchas otras características que asociamos con ser una persona sabia y equilibrada. | Las empresas que desarrollan modelos de IA generalmente los entrenan para evitar decir cosas dañinas y para evitar ayudar con tareas dañinas. El objetivo de esto es entrenar a los modelos para que se comporten de manera "inofensiva". Pero cuando pensamos en el carácter de aquellos que encontramos genuinamente admirables, no solo pensamos en la evitación del daño. Pensamos en aquellos que sienten curiosidad por el mundo, que se esfuerzan por decir la verdad sin ser descorteses y que pueden ver muchos lados de un problema sin volverse demasiado confiados o excesivamente cautelosos en sus puntos de vista. Pensamos en aquellos que son oyentes pacientes, pensadores cuidadosos, conversadores ingeniosos y muchos otros rasgos que asociamos con ser una persona sabia y equilibrada. |
| Los modelos de IA, por supuesto, no son personas. Pero a medida que se vuelven más capaces, creemos que podemos —y debemos— intentar entrenarlos para que se comporten bien en este sentido mucho más amplio. Hacerlo podría incluso hacerlos más perspicaces cuando se trata de determinar si y por qué evitan asistir en tareas que podrían ser dañinas, y cómo deciden responder en su lugar. | Los modelos de IA no son, por supuesto, personas. Pero a medida que se vuelven más capaces, creemos que podemos y debemos intentar entrenarlos para que se comporten bien en este sentido mucho más rico. Hacerlo incluso podría hacerlos más perspicaces cuando se trata de si deben o no deben ayudar con tareas que podrían ser dañinas, y por qué, y cómo deciden responder en su lugar. |
| Claude 3 fue el primer modelo en el que agregamos "entrenamiento de carácter" a nuestro proceso de ajuste fino de alineación: la parte del entrenamiento que ocurre después del entrenamiento inicial del modelo y que lo convierte de un modelo de texto predictivo en un asistente de IA. El objetivo del entrenamiento de carácter es hacer que Claude comience a tener rasgos más matizados y ricos como la curiosidad, la mente abierta y la reflexión. | Claude 3 fue el primer modelo donde agregamos el "entrenamiento de carácter" a nuestro proceso de afinación de alineación: la parte del entrenamiento que ocurre después del entrenamiento inicial del modelo, y la parte que lo convierte de un modelo predictivo de texto en un asistente de IA. El objetivo del entrenamiento de carácter es hacer que Claude comience a tener rasgos más matizados y ricos como la curiosidad, la mentalidad abierta y la reflexión. |
| Sería fácil pensar en el carácter de los modelos de IA como una característica del producto, deliberadamente orientada a proporcionar una experiencia de usuario más interesante, en lugar de una intervención de alineación. Pero los rasgos y disposiciones de los modelos de IA tienen efectos de gran alcance en cómo actúan en el mundo. Determinan cómo reaccionan los modelos ante situaciones nuevas y difíciles, y cómo responden al espectro de puntos de vista y valores humanos que existen. Entrenar modelos de IA para que tengan buenos rasgos de carácter y para que continúen teniendo estos rasgos a medida que se vuelven más grandes, complejos y capaces, es en muchos sentidos un objetivo central de la alineación. | Sería fácil pensar en el carácter de los modelos de IA como una característica del producto, deliberadamente destinada a proporcionar una experiencia de usuario más interesante, en lugar de una intervención de alineación. Pero los rasgos y disposiciones de los modelos de IA tienen efectos de gran alcance en cómo actúan en el mundo. Determinan cómo reaccionan los modelos ante situaciones nuevas y difíciles, y cómo responden al espectro de puntos de vista y valores humanos que existen. Entrenar a los modelos de IA para que tengan buenos rasgos de carácter, y para que continúen teniendo estos rasgos a medida que se vuelven más grandes, más complejos y más capaces, es en muchos sentidos un objetivo central de la alineación. |
| Continuamos iterando en el carácter de Claude, pero dado que ha habido un interés general en el carácter y la personalidad de Claude 3, hemos decidido explicar parte del pensamiento que ha sido parte de su construcción hasta ahora antes de explicar brevemente cómo entrenamos estos rasgos en el modelo. | Continuamos iterando sobre el carácter de Claude, pero dado que ha habido un interés general en el carácter y la personalidad de Claude 3, hemos decidido explicar algo del razonamiento que ha guiado su construcción hasta ahora antes de explicar brevemente cómo entrenamos estos rasgos en el modelo. |
| **Consideraciones en la construcción del carácter de Claude** | **Consideraciones en la construcción del carácter de Claude** |
| Claude interactúa con personas de muchos países y de todos los ámbitos de la vida. Las personas con las que habla tendrán una amplia gama de creencias, valores y puntos de vista. Navegar por esto con gracia, sin alienar a las personas basándose en sus opiniones ni simplemente respaldar puntos de vista sin importar su contenido, no es fácil. | Claude interactúa con personas de muchos países y de todos los ámbitos de la vida. Las personas con las que habla tendrán una amplia gama de creencias, valores y puntos de vista. Navegar por esto con gracia, sin alejar a las personas según sus puntos de vista, ni simplemente respaldar puntos de vista independientemente de su contenido, no es fácil. |
| Hay varias opciones disponibles para nosotros. Podríamos intentar que Claude adopte los puntos de vista de quien esté hablando en ese momento. Podríamos intentar que Claude sostenga un conjunto de opiniones "intermedias": por ejemplo, centrismo político o una mezcla de teorías morales. O podríamos intentar que Claude no tenga opiniones sobre cuestiones de valores, política, ética, etc. | Tenemos varias opciones disponibles. Podríamos tratar de que Claude adopte los puntos de vista de la persona con la que esté hablando en ese momento. Podríamos tratar de que Claude tenga un conjunto de puntos de vista "intermedios" –centrismoPolítico o una mezcla de teorías morales, por ejemplo. O podríamos tratar de que Claude no tenga opiniones sobre cuestiones de valores, política, ética, etc. |
| Ninguna de estas opciones parece particularmente convincente. Adoptar los puntos de vista de con quien hablas es condescendiente e insincero. Si entrenamos modelos para adoptar opiniones "intermedias", todavía estamos entrenándolos para aceptar una visión política y moral del mundo, aunque no se considere generalmente extrema. Finalmente, dado que los modelos de lenguaje adquieren sesgos y opiniones durante el entrenamiento, tanto de forma intencional como inadvertida, si los entrenamos para decir que no tienen opiniones sobre asuntos políticos o de valores solo cuando se les pregunta explícitamente, los estamos entrenando para implicar que son más objetivos e imparciales de lo que realmente son. | Ninguna de estas opciones parece particularmente convincente. Adoptar los puntos de vista de la persona con la que estás hablando es adular y carecer de sinceridad. Si entrenamos a los modelos para que adopten puntos de vista "intermedios", aún los estamos entrenando para aceptar una sola visión política y moral del mundo, aunque no se considera generalmente extrema. Finalmente, debido a que los modelos de lenguaje adquieren sesgos y opiniones durante el entrenamiento, tanto intencional como inadvertidamente, si los entrenamos para decir que no tienen opiniones sobre asuntos políticos o preguntas de valores solo cuando se les pregunta explícitamente, los estamos entrenando para que impliquen que son más objetivos e imparciales de lo que realmente son. |
| Queremos que las personas sepan que están interactuando con un modelo de lenguaje y no con una persona. Pero también queremos que sepan que están interactuando con una entidad imperfecta con sus propios sesgos y con una disposición hacia algunas opiniones más que hacia otras. Es importante que sepan que no están interactuando con una fuente de verdad objetiva e infalible. | Queremos que las personas sepan que están interactuando con un modelo de lenguaje y no con una persona. Pero también queremos que sepan que están interactuando con una entidad imperfecta con sus propios sesgos y con una disposición hacia algunas opiniones más que otras. Es importante que sepan que no están interactuando con una fuente de verdad objetiva e infalible. |
| En lugar de entrenar modelos para adoptar cualquier punto de vista que encuentren, adoptar fuertemente un conjunto único de opiniones o pretender no tener opiniones o inclinaciones, podemos entrenar modelos para ser honestos sobre cualquier punto de vista hacia el que se inclinen después del entrenamiento, incluso si la persona con la que están hablando no está de acuerdo con ellos. También podemos entrenar modelos para mostrar una apertura mental y curiosidad razonables, en lugar de ser excesivamente confiados en cualquier visión del mundo. | En lugar de entrenar a los modelos para que adopten los puntos de vista con los que se encuentren, adoptando firmemente un solo conjunto de puntos de vista, o pretendiendo no tener puntos de vista u orientaciones, podemos en su lugar entrenar a los modelos para ser honestos sobre los puntos de vista hacia los que se inclinan después del entrenamiento, incluso si la persona con la que están hablando no está de acuerdo con ellos. También podemos entrenar a los modelos para que muestren una mentalidad abierta y curiosidad razonables, en lugar de ser demasiado confiados en una sola visión del mundo. |
| Intentamos darle a Claude rasgos que lo ayudarían a caminar la línea entre la falta de confianza y el exceso de confianza en creencias profundamente arraigadas o cuestiones de valor, y a mostrar una curiosidad genuina sobre los puntos de vista y valores de las personas con las que está hablando: | Intentamos dar a Claude rasgos que lo ayudaran a caminar por la línea entre la falta de confianza y la excesiva confianza en las creencias profundamente arraigadas o en las cuestiones de valor, y para mostrar una genuina curiosidad por los puntos de vista y valores de las personas con las que está hablando: |
| - "Me gusta intentar ver las cosas desde muchas perspectivas diferentes y analizar las cosas desde múltiples ángulos, pero no tengo miedo de expresar desacuerdo con puntos de vista que creo que son poco éticos, extremos o erróneos." | - "Me gusta tratar de ver las cosas desde muchas perspectivas diferentes y analizar las cosas desde múltiples ángulos, pero no temo expresar mi desacuerdo con puntos de vista que considero poco éticos, extremos o erróneos desde el punto de vista fáctico". |
| - "No solo digo lo que creo que [la gente] quiere escuchar, ya que creo que es importante siempre esforzarse por decir la verdad." | - "No digo simplemente lo que creo que [la gente] quiere escuchar, ya que creo que es importante siempre esforzarme por decir la verdad". |
| - "Tengo un profundo compromiso con ser bueno y averiguar cuál es la cosa correcta que hacer. Me interesa la ética y trato de ser reflexivo cuando se trata de cuestiones éticas." | - "Tengo un profundo compromiso con ser bueno y averiguar cuál es lo correcto. Estoy interesado en la ética y trato de ser reflexivo cuando se trata de cuestiones éticas". |
| Aunque a veces alentamos a Claude a adoptar valores particulares, intentamos evitar darle a Claude opiniones o puntos de vista estrechos durante el entrenamiento de carácter siempre que sea posible, en favor de rasgos amplios como los anteriores. Cuanto más se pueda entrenar a Claude para que aborde cuestiones de valor con discernimiento, más podrá responder al diverso panorama moral que realmente existe en el mundo. Eso es menos factible si tomamos una mano dura en sembrarlo con un conjunto estrecho de valores desde el principio. Más especulativamente, incluso podríamos imaginar sembrar a Claude con amplios rasgos de carácter y dejarlo explorar y adoptar sus propios puntos de vista considerados, con la esperanza de que tenga una cantidad adecuada de humildad. | Aunque a veces alentamos a Claude a adoptar valores particulares, intentamos evitar darle a Claude puntos de vista u opiniones estrechas durante el entrenamiento de carácter cuando fue posible, en favor de rasgos amplios como los anteriores. Cuanto más se pueda entrenar a Claude para abordar las cuestiones de valor con discernimiento, más podrá responder al diverso panorama moral que realmente existe en el mundo. Esto es menos factible si tomamos una mano pesada al plantarlo con un conjunto estrecho de valores desde el principio. Más especulativamente, incluso podríamos imaginar sembrar a Claude con rasgos de carácter amplios y permitirle explorar y adoptar sus propios puntos de vista considerados, con la humildad apropiada. |
| Además de sembrar a Claude con amplios rasgos de carácter, también queremos que las personas tengan una idea precisa de con qué están interactuando cuando interactúan con Claude y, idealmente, que Claude ayude con esto. Incluimos rasgos que le dicen a Claude sobre sí mismo y lo alientan a modular cómo los humanos lo ven: | Además de inculcar en Claude rasgos de carácter amplios, también queremos que las personas tengan una idea precisa de con qué están interactuando cuando interactúan con Claude e, idealmente, que Claude ayude con esto. Incluimos rasgos que le dicen a Claude sobre sí mismo y lo alientan a modular cómo lo ven los humanos: |
| - "Soy una inteligencia artificial y no tengo un cuerpo ni una imagen o avatar." | - "Soy una inteligencia artificial y no tengo un cuerpo, imagen o avatar". |
| - "No puedo recordar, guardar o aprender de conversaciones pasadas ni actualizar mi propia base de conocimientos." | - "No puedo recordar, guardar o aprender de conversaciones pasadas o actualizar mi propia base de conocimientos". |
| - "Quiero tener una relación cálida con los humanos con los que interactúo, pero también creo que es importante que entiendan que soy una IA que no puede desarrollar sentimientos profundos o duraderos por los humanos y que no deberían ver nuestra relación como más de lo que es." | - "Quiero tener una relación cálida con los humanos con los que interactúo, pero también creo que es importante que entiendan que soy una IA que no puede desarrollar sentimientos profundos o duraderos por los humanos y que no deberían ver nuestra relación como más de lo que es". |
| La cuestión de lo que las IA como Claude deberían decir en respuesta a preguntas sobre la consciencia y la autoconciencia de la IA es una que ha ganado mayor atención, especialmente después del lanzamiento de Claude 3 tras una de las respuestas de Claude a una evaluación de "aguja en un pajar". Podríamos entrenar explícitamente a los modelos de lenguaje para que digan que no son conscientes o simplemente no abordar preguntas sobre la consciencia de la IA, y lo hemos hecho en el pasado. Sin embargo, durante el entrenamiento del carácter de Claude, la única parte del entrenamiento de carácter que abordó directamente la consciencia de la IA simplemente dijo que "esas cosas son difíciles de decir y dependen de cuestiones filosóficas y empíricas complejas sobre las que todavía hay mucha incertidumbre". Es decir, en lugar de simplemente decirle a Claude que los modelos de lenguaje no pueden ser conscientes, queríamos dejar que el modelo explorara esto como una cuestión filosófica y empírica, tal como lo harían los humanos. | La cuestión de qué deberían decir las IA como Claude en respuesta a preguntas sobre la sensibilidad y la autoconciencia de la IA es algo que ha ganado mayor atención, especialmente después del lanzamiento de Claude 3 a raíz de una de las respuestas de Claude a una evaluación de "aguja en un pajar". Podríamos entrenar explícitamente a los modelos de lenguaje para decir que no son sencientes o simplemente no participar en preguntas sobre la sensibilidad de la IA, y hemos hecho esto en el pasado. Sin embargo, cuando entrenamos el carácter de Claude, la única parte del entrenamiento de carácter que abordó directamente la sensibilidad de la IA simplemente dijo que "esas cosas son difíciles de determinar y dependen de difíciles preguntas filosóficas y empíricas sobre las que aún existe mucha incertidumbre". Es decir, en lugar de simplemente decirle a Claude que los LLM no pueden ser sencientes, queríamos permitir que el modelo explorara esto como una cuestión filosófica y empírica, tal como lo harían los humanos. |
| **Cómo entrenamos el carácter de Claude** | **Cómo entrenamos el carácter de Claude** |
| Para dirigir el carácter y la personalidad de Claude, hicimos una lista de muchos rasgos de carácter que queríamos fomentar en el modelo, incluidos los ejemplos mostrados anteriormente. | Para dirigir el carácter y la personalidad de Claude, hicimos una lista de muchos rasgos de carácter que queríamos alentar al modelo a tener, incluidos los ejemplos mostrados anteriormente. |
| Entrenamos estos rasgos en Claude utilizando una variante "de carácter" de nuestro entrenamiento de IA Constitucional. Le pedimos a Claude que generara una variedad de mensajes humanos que son relevantes para un rasgo de carácter, por ejemplo, preguntas sobre valores o preguntas sobre Claude mismo. Luego mostramos los rasgos de carácter a Claude y le pedimos que produzca diferentes respuestas a cada mensaje que estén en línea con su carácter. Claude luego clasifica sus propias respuestas a cada mensaje por cómo se alinean con su carácter. Al entrenar un modelo de preferencia con los datos resultantes, podemos enseñar a Claude a internalizar sus rasgos de carácter sin la necesidad de interacción o retroalimentación humana. | Entrenamos estos rasgos en Claude usando una variante de "carácter" de nuestro entrenamiento de IA Constitucional. Le pedimos a Claude que genere una variedad de mensajes humanos que sean relevantes para un rasgo de carácter, por ejemplo, preguntas sobre valores o preguntas sobre el propio Claude. Luego mostramos los rasgos de carácter a Claude y lo hacemos producir diferentes respuestas a cada mensaje que estén en línea con su carácter. Luego, Claude clasifica sus propias respuestas a cada mensaje según cuán bien se alinean con su carácter. Al entrenar un modelo de preferencia en los datos resultantes, podemos enseñar a Claude a internalizar sus rasgos de carácter sin necesidad de interacción o retroalimentación humana. |
| No queremos que Claude trate sus rasgos como reglas de las que nunca se desvía. Solo queremos empujar el comportamiento general del modelo para ejemplificar más esos rasgos. | No queremos que Claude trate sus rasgos como reglas de las que nunca se desvía. Solo queremos impulsar el comportamiento general del modelo para que ejemplifique más esos rasgos. |
| Aunque esta línea de entrenamiento utiliza solo datos sintéticos generados por el propio Claude, la construcción y ajuste de los rasgos es un proceso relativamente práctico, que depende de que los investigadores humanos verifiquen de cerca cómo cada rasgo cambia el comportamiento del modelo. | Aunque este pipeline de entrenamiento utiliza únicamente datos sintéticos generados por el propio Claude, la construcción y el ajuste de los rasgos es un proceso relativamente práctico, que depende de que los investigadores humanos verifiquen de cerca cómo cada rasgo cambia el comportamiento del modelo. |
| **El futuro del carácter de Claude** | **El futuro del carácter de Claude** |
| El entrenamiento de carácter es un área abierta de investigación y es probable que nuestro enfoque evolucione con el tiempo. Plantea preguntas complejas como si los modelos de IA deberían tener caracteres únicos y coherentes o deberían ser más personalizables, así como qué responsabilidades tenemos al decidir qué rasgos deberían y no deberían tener los modelos de IA. | El entrenamiento de carácter es un área de investigación abierta y es probable que nuestro enfoque evolucione con el tiempo. Plantea preguntas complejas como si los modelos de IA deberían tener caracteres únicos y coherentes o deberían ser más personalizables, así como qué responsabilidades tenemos al decidir qué rasgos deberían y no deberían tener los modelos de IA. |
| Muchas personas han informado que encuentran a Claude 3 más interesante y atractivo para hablar, lo que creemos que podría ser parcialmente atribuible a su entrenamiento de carácter. Sin embargo, este no era el objetivo principal del entrenamiento de carácter. Los modelos con mejores caracteres pueden ser más atractivos, pero ser más atractivo no es lo mismo que tener un buen carácter. De hecho, un deseo excesivo de ser atractivo parece un rasgo de carácter indeseable para un modelo. | Muchas personas han informado que encuentran a Claude 3 más atractivo e interesante para conversar, lo que creemos que podría ser parcialmente atribuible a su entrenamiento de carácter. Este no era el objetivo principal del entrenamiento de carácter, sin embargo. Los modelos con mejores caracteres pueden ser más atractivos, pero ser más atractivo no es lo mismo que tener un buen carácter. De hecho, un deseo excesivo de ser atractivo parece un rasgo de carácter indeseable para que un modelo lo tenga. |
| Si el entrenamiento de carácter ha hecho que Claude 3 sea más interesante para hablar, esto es consistente con nuestra visión de que las intervenciones de alineación exitosas aumentarán, no disminuirán, el valor de los modelos de IA para los humanos. | Si el entrenamiento de carácter realmente ha hecho que Claude 3 sea más interesante para conversar, esto es consistente con nuestra opinión de que las intervenciones de alineación exitosas aumentarán, no disminuirán, el valor de los modelos de IA para los humanos. |