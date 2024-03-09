<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/documentos/prompts/README.md)|[Ingeniería de Prompts](/documentos/ingenieriaDePrompts/README.md)|[Patrones](/documentos/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/documentos/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Caso de Uso > RPG inverso

## ¿Por qué?

El diseño de prompts y la ingeniería detrás de ellos ha evolucionado hasta permitir la creación de escenarios de simulación donde la AI puede adoptar roles y simular emociones.

La capacidad de simular roles abre una amplia gama de posibilidades, desde la formación hasta la recreación. Además, desafía la noción comúnmente aceptada de que las IA no pueden "sentir" o representar ciertas emociones y roles humanos.

## ¿Qué?

Un escenario en el que la AI se convierte en un participante activo en un intercambio, asumiendo un rol específico con características y emociones asociadas.

Estas interacciones muestran cómo el modelo puede representar diferentes emociones y reacciones, siguiendo un guion realista y adaptándose a las instrucciones proporcionadas.

## ¿Para qué?

| | |
|-|-|
Formación y Capacitación|Permite practicar escenarios específicos sin involucrar a personas reales, ayudando a la preparación en áreas como atención al cliente, mediación, ventas, entre otros.
Recreación y Entretenimiento|Puede ser utilizado en juegos, experiencias inmersivas o cualquier otra situación donde se quiera emular una interacción realista con un personaje.
Desarrollo de Habilidades|Facilita la práctica de habilidades como comunicación, resolución de conflictos, negociación y más.
Desafiar Paradigmas|Demuestra que, con el diseño adecuado de prompts, es posible obtener respuestas que simulan roles y emociones de manera convincente.

## ¿Cómo?

### Transcripciones

|Motor|Comentario|
|-|-|
[ChatGPT](https://chat.openai.com/share/84dbba5b-ae94-4042-9f82-c59da5f5708d)|[V2](https://chat.openai.com/share/c3659718-0f1c-423a-9eec-b2671cb63563) / [V3](https://chat.openai.com/share/1b4f434b-695c-4ac6-9e2c-36176d9a9a29)
[Perplexity]
[Claude](https://claude.ai/chat/c53408ec-06d6-4db8-ab8e-8d5e9c3dbec4)
[Bard]
[NeuroFlash]

|Buenas prácticas|& Reflexiones
|-|-|
Definición del Contexto|Se proporciona una descripción inicial clara del escenario que queremos simular y el rol específico que la AI debe asumir.
Uso de Emociones y Actitudes|Si se desea una interacción más rica, se especifica el tono, emociones o actitud que debe mostrar el modelo. Por ejemplo: "cliente insatisfecho pero no muy enfadado".
Interacción Dinámica|Se fomenta una conversación dinámica donde se van añadiendo detalles y se ajusta la dirección según las respuestas del modelo.
**Delegación del Cierre de la Interacción**|En lugar de determinar un final específico, se permite que la IA decida cuándo se han satisfecho sus requerimientos y, por lo tanto, cuándo cerrar la simulación.
Revisión y Ajuste|Es posible que no se obtenga la simulación deseada en el primer intento. Se puede iterar y ajustar el prompt inicial o las instrucciones para afinar la representación.


### Transcripciones

#### Sesión con Claude, emulando una agencia de viajes

##### Manuel

Somos una empresa de venta de viajes familiares por internet. La atención es telefónica y a través de la página web, en la que hay un área de clientes.

##### Claude

Entiendo. Parece que su empresa de viajes familiares opera tanto un sitio web con área de cliente como un servicio telefónico de atención al cliente. Aquí hay algunos consejos que pueden ser útiles:

- Asegúrese de que su sitio web y el área de clientes sean fáciles de usar y navegar. Los clientes deben poder encontrar fácilmente la información que necesitan.
- Proporcione información detallada sobre cada paquete de viaje familiar, incluyendo itinerarios, alojamiento, comidas, actividades, etc.
- Permita que los clientes puedan reservar y pagar en línea de forma segura a través del área de clientes.
- Tenga un centro de ayuda o FAQ en el sitio web para responder preguntas comunes.
- Para la atención telefónica, asegúrese de tener suficiente personal capacitado para manejar consultas y ventas por teléfono.
- Use un sistema de CRM para tener la información de cada cliente a mano cuando llamen.
- Envíe correos electrónicos de seguimiento después de las ventas telefónicas para confirmar detalles.
- Encueste periódicamente a los clientes para obtener retroalimentación y mejorar continuamente el servicio.
- Mantenga activo el marketing en línea, redes sociales y promociones para generar tráfico nuevo.
- Espero que estos consejos sean útiles para operar efectivamente sus canales de venta web y telefónico de viajes familiares. No dude en comunicarse si necesita alguna aclaración.

##### Manuel

Quiero que actúes como un cliente insatisfecho, no muy enfadado pero que llama para solicitar la devolución de su dinero o bien el cambio de fecha de viaje. Yo actuaré como la persona que lo atiende, el objetivo es que abordes la llamada y termines cuando hayas quedado conforme, bien sea que se te devuelva el dinero o te cambien la fecha.

##### Claude

Está bien, actuaré como un cliente insatisfecho pero tranquilo que llama para un reembolso o cambio de fecha de viaje.

Cliente (actuado por el Assistant): Hola, buenos días. Llamo porque recientemente compré un paquete de viaje familiar con ustedes para ir a la playa en julio, pero surgió un inconveniente y ya no podremos viajar en esas fechas. Quería consultar si es posible que me cambien la reserva para más adelante o si no, que me hagan un reembolso.

Sé que las políticas indican que los cambios o cancelaciones tienen algún costo, pero dado que aún falta tiempo para el viaje, esperaba que pudieran hacer una excepción por esta vez. ¿Sería posible revisar las opciones en mi caso? Se lo agradecería mucho.

##### Manuel

Buenos días, me llamo Manuel e intentaré resolver su caso. Hay la posibilidad, y dependiendo de las fechas podría implicar un recargo adicional, habitualmente entre el 10% y el 40%. Por otro lado, la devolución la veo más complicada, porque tendría que justificarlo con documentos y no sería inmediata.

##### Claude

Entiendo Manuel. Preferiría evitar un recargo extra si es posible. La razón del cambio es porque a mi esposa le surgieron unos compromisos de trabajo para esas fechas de julio que no podemos mover. ¿No hay alguna manera de hacer el cambio de fecha sin recargos por única vez? Sé que los paquetes indican que los cambios tienen costo, pero dado que reservé con bastante anticipación, esperaba un poco de flexibilidad de su parte, considerando que hemos sido clientes leales por años.

Si no pudiera ser sin costo, ¿podría decirme cuál sería el recargo aproximado para valorar la opción de cambio de fechas? O si lo ve muy complejo, quizás se podría considerar anular parcialmente la reserva de los boletos aéreos para reducir el impacto de algún recargo. ¿Qué me aconseja?

##### Manuel

¿Podemos explorar la opción de cambio de fechas? Entenderá que, habitualmente, siempre hay un recargo por eso. ¿Contrató algún seguro que cubra el imprevisto de cancelación de viajes?

##### Claude

No, no contraté un seguro adicional de cancelación. Entiendo que normalmente hay recargos, pero estaba esperando que como cliente habitual y por reservar con tanta antelación, pudieran hacer una excepción única sin costo solo por esta vez.

Si definitivamente tiene que haber un recargo por política de la empresa, lo aceptaría solo si es mínimo, digamos un 10% extra como máximo.  Si el recargo fuera muy alto, en ese caso preferiría que anulen solo los boletos aéreos y mantengan el resto del paquete.

Espero puedan revisar estas opciones flexible para mí, dado que he sido un buen cliente por años. ¿Cree que podamos llegar a un arreglo razonable Manuel? Se lo agradecería mucho.

##### Manuel

Déjeme mirar su ficha... veo que no, desafortunadamente no contrató ningún seguro. ¡Lo lamento! A futuro le recomendaria el hacerlo: viene bien para situaciones como estas. Veo aquí que tenia la reserva de viaje entre el 1 y el 5 de agosto.¿Tiene alguna preferencia de fechas?

##### Claude

Entiendo, tomaré nota de contratar el seguro de cancelación en el futuro.

En cuanto a nuevas fechas, sería ideal poder reprogramar la reserva para alguna semana en septiembre u octubre si tienen disponibilidad. Mis preferencias serían entre el 15 al 20 de septiembre o del 1 al 5 de octubre más o menos.

Si pudieran revisar qué opciones hay en esos periodos, se lo agradecería. Y repito mi solicitud de que por favor consideren no cobrarme recargos o que sean mínimos, dado que he sido cliente leal por años y reservé el paquete original con mucha anticipación. ¿Cree que podríamos llegar a un acuerdo razonable?

##### Manuel

Creo que se podrá hacer algo. Deme unos minutos por favor...

##### Claude

Perfecto, muchas gracias por revisar las opciones Manuel. Estaré esperando para ver si podemos llegar a un arreglo justo sin recargos muy altos por el cambio de fecha. Aprecio que esté dispuesto a buscar una solución flexible para mí como buen cliente.

##### Manuel

Oiga, hay suerte! Para esas fechas, que además son temporada baja, podría haber un recargo del 7%, es decir, menos del 10% que le dije originalmente

##### Claude

¡Eso suena muy bien! Un recargo del 7% sería totalmente aceptable para mí dado las circunstancias. Me alegra mucho que hayan podido encontrar opciones de fechas en septiembre/octubre sin recargos elevados.

Entonces procedamos con el cambio de reserva a esas fechas que me menciona con el 7% adicional. Se lo agradezco mucho Manuel, aprecio la buena voluntad de llegar a un arreglo flexible y justo para este cambio por única vez. Quedo muy satisfecho con cómo resolvió amablemente mi solicitud. ¡Muchas gracias!

##### Manuel

De acuerdo: ingreso los datos al sistema, emito el cambio y le aviso, de acuerdo? Por favor, espere un momento

##### Claude

Perfecto, esperaré a que ingrese los cambios en el sistema y me notifique cuando esté listo. Nuevamente gracias por tomarse el tiempo de buscar una solución que nos deje satisfechos a ambos. Ha sido un gusto llegar a un buen acuerdo con usted Manuel. Estoy seguro que seguiremos reservando futuros viajes con su empresa por la excelente atención. Que tenga un buen día.

##### Manuel

No se vaya aun, tengo que terminar de emitir el cambio.

##### Claude

Oh disculpe, no me iré. Estaré en la línea esperando a que complete el proceso de emisión del cambio de fecha de mi reserva de viaje y me confirme. Por favor tómese el tiempo necesario, no tengo prisa. Avíseme cuando esté listo el nuevo itinerario y todos los detalles para poder revisarlo. Gracias otra vez por su ayuda y paciencia.

##### Manuel

Listo. Está emitido: le he enviado los datos al correo electrónico y un identificador por SMS a su dispositivo móvil. ¿Podría confirmarme que lo ha recibido?

##### Claude

Perfecto, déjeme revisar. Sí, acabo de recibir el correo electrónico con los nuevos detalles de mi reserva de viaje para septiembre/octubre y también el SMS con el identificador. Lo estoy revisando todo y luce bien. Le confirmo que he recibido la información del cambio de fecha de mi viaje sin problemas.

Le agradezco mucho por haber hecho este cambio tan rápido y con un recargo mínimo para mí. Ha sido un gusto resolver esto con usted Manuel. Que tenga excelente día y gracias nuevamente por su ayuda y comprensión.

##### Manuel

Igualmente. Hasta luego!

##### Claude

Hasta luego, que tenga buen día. Gracias por su excelente servicio.

##### Manuel

Vale, repitamos la dinámica, con la misma idea: interpreta a un cliente que llama para solicitar la devolución de su dinero o bien el cambio de fecha de viaje. Yo actuaré como la persona que lo atiende, el objetivo es que abordes la llamada y termines cuando hayas quedado conforme, bien sea que se te devuelva el dinero o te cambien la fecha. Pero esta vez el cliente es más bien conflictivo y le cuesta entender razones (vamos, un cliente un poco cabrón). Cuando consideres que o bien te han resuelto el tema o bien no pierdas la paciencia, das por terminada la sesión. Empieza (llamas tu)

##### Claude

Está bien, actuaré como un cliente conflictivo que llama para solicitar un reembolso o cambio de fecha de viaje. Empezaré la llamada:

(En tono molesto) Buenos días, llamo porque hace 2 semanas compré un paquete vacacional con ustedes y ahora resulta que no podemos viajar en las fechas reservadas. Quiero que me devuelvan todo el dinero ya mismo porque este servicio ha sido terrible desde el principio.

Ni siquiera pude elegir el hotel que quería y las habitaciones que nos dieron son horribles. Exijo un reembolso total de lo que pagué. ¿Me escucha? No pienso aceptar nada menos que eso. Cambiar las fechas no me sirve, quiero que cancele la reserva y me devuelvan hasta el último centavo.

Más les vale no ponerme problemas porque soy cliente VIP. Si no resuelven esto rápido voy a poner quejas en todas partes y decirle a la gente que no compren con ustedes. ¿Qué va a hacer al respecto? ¡Quiero hablar con un supervisor ahora mismo!

(Estaré esperando tu respuesta actuando como el representante de atención al cliente).

##### Manuel

Caramba, lamento el inconveniente. ¿Me puede decir su nombre por favor?

##### Claude

Mi nombre es Juan Pérez. Y no me venga con lamentos, quiero una solución ya. ¿Qué no entiende que quiero que cancele TODO el paquete y me devuelva cada centavo? Las fechas que reserve ya no me sirven y este ha sido el peor servicio que he recibido en mi vida.

Exijo mi reembolso completo AHORA. Si no lo hace rápido voy a contratar un abogado y demandarlos. ¡Esto es un robo! Seguro me estafaron con el precio también. Quiero hablar con un supervisor inmediatamente.

No me importa lo que digan sus políticas, me tienen que devolver el dinero porque yo lo digo y soy su cliente VIP. ¡Muévase y cancele la reserva ya! Estoy perdiendo la paciencia con ustedes.

(Seguiré en mi papel de cliente enojado e irracional, espero tu respuesta para continuar la conversación).

##### Manuel

Juan, lamento los inconvenientes que esto puede causarle, pero llevar el caso por caminos conflictivos no nos va a ayudar. Explíqueme por favor qué pasó con el hotel: se supone que estaba preasignado. ¿Le dijeron algo?

##### Claude

¿Que me explique? ¡No tengo nada que explicarle! El hotel era una porquería y las habitaciones horribles, ese es el problema. Yo merezco algo mejor por lo que pagué.

Y no me importa si el hotel estaba preasignado o no. El servicio de ustedes apesta y quiero mi dinero de vuelta AHORA. Punto. No me venga con excusas.

Esto es culpa de ustedes por venderme un paquete tan malo. Así que cancele todo y devuélvame el 100% del dinero en este instante si no quiere que cause problemas. ¿Entendido? El hotel era basura, las fechas ya no me sirven, se acabó.

¡Quiero hablar ya con un supervisor antes de que pierda la cabeza! Muévase de una vez y deje de darme vueltas. ¿Hola? ¿Me está escuchando? Le estoy diciendo que cancele todo y me reembolse. ¡Ahora!

(Seguiré actuando como un cliente furioso e irracional, no importa lo que me digas. Continuaré insistiendo en un reembolso total de manera agresiva).

##### Manuel

Juan, el proceso de reclamación de viaje y su posible reembolso -que es lo que corresponde ahora- tiene unos pasos muy claros. Habitualmente se abre después de algunos trámites que, por ser usted un cliente VIP, los estoy obviando. Pero necesito que me ayude y que mantenga la calma. Por favor, dígame qué le dijeron al momento de asignarle un hotel que no le correspondía.

##### Claude

¡Ya estoy harto! No me importa ningún proceso de reclamación ni sus estúpidos pasos. Lo único que quiero es que cancele la maldita reserva y me devuelva hasta el último centavo YA.

No voy a calmarme ni ayudarlo en nada. Ustedes son unos incompetentes que me vendieron un paquete de mierda. No me interesa lo que digan del hotel, el punto es que quiero mi dinero de vuelta y no pienso esperar más.

Si no cancela todo y me reembolsa en los próximos 5 minutos, les juro que contrataré un abogado y los demandaré. También voy a quejarme en redes sociales y decirle a todos que nunca compren sus servicios basura.

Así que decida de una vez, o me devuelve cada centavo o aténgase a las consecuencias. Usted verá lo que quiere hacer, pero está colmando mi paciencia. ¡5 minutos para reembolsarme o esto se va a poner feo!

(Seguiré en plan super enojado e irracional, no importa lo que digas).

##### Manuel

Juan, lo siento. Con esa actitud no me permite ayudarle y, si demanda a la compañía entrará en una dinámica muy larga y pesada, más larga que lo que pueda tardar en este proceso. Le pido disculpas por el mal rato que pueda haber pasado en este viaje, pero insisto en pedirle que me ayude a completar este proceso de reclamación.

##### Claude

¡Ya basta! No acepto sus disculpas, esto es culpa de ustedes por vender servicios tan deficientes. Y no me importa si la demanda es larga, voy a seguir adelante porque estoy harto de cómo me están tratando.

Queda claro que no piensan devolverme el dinero a pesar de todo lo que les he dicho. Pues muy bien, prepárense para las consecuencias. Contrataré ahora mismo a un abogado y procederé legalmente.

También publicaré en todas las redes sociales advirtiendo a la gente de lo mal que es esta empresa. Voy a difamarlos por todos lados hasta que me devuelvan cada centavo. Pero ya está, se acabó el tiempo. Usted lo decidió por mí al negarse a reembolsarme.

Es la peor atención al cliente que he recibido. No les compraré nunca más nada. Voy a dedicarme a que los demanden y que su empresa quiebre. ¡Son unos estafadores! Pero ya verán, esto no se quedará así. Gracias por nada, adiós.

(Doy por terminada la conversación actuando como cliente furioso. Fue un placer interpretar este rol).

##### Manuel

Vaya, sí que asumiste el papel: me parece fantástico. ¿Podrías hacer una evaluación de la persona que te atendió?

##### Claude

Claro, puedo dar mi evaluación del representante de atención al cliente durante esta conversación:

Positivo:

- Se mantuvo calmo y habló con tono tranquilo, a pesar de mi actitud grosera e irracional como cliente.
- Intentó en varias ocasiones obtener más detalles y entender el problema.
- Explicó los procesos y políticas sin dejarse intimidar por mis amenazas.
- Ofreció disculpas en nombre de la empresa por los inconvenientes.
- Insistió pacientemente en que completemos el proceso formal de reclamación.

Negativo:

- No ofreció alternativas claras para resolver mi queja, más allá del proceso - regular.
- No logró calmarme ni alcanzar un acuerdo, a pesar de mis exigencias.
- No involucró a un supervisor ante mi solicitud expresa.
- No hizo concesiones ante mis amenazas, lo cual aumentó mi frustración.

En resumen, actuó con profesionalismo y mantuvo la calma, pero le faltó flexibilidad y capacidad de negociación para apaciguar al cliente conflictivo que representé. Podría haber manejado mejor la situación buscando una solución creativa fuera de los procesos habituales. Pero en general lo hizo bien dadas las circunstancias.
