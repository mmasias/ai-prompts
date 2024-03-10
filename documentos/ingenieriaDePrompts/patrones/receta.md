<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Patrón Receta

## Intención y Contexto

Este patrón proporciona restricciones para finalmente generar una secuencia de pasos dada una serie de "ingredientes" parcialmente proporcionados que deben configurarse en una secuencia de pasos para lograr un objetivo declarado. Combina los patrones de Plantilla, Enfoques Alternativos y Reflexión.

## Motivación

Los usuarios a menudo quieren que un LLM analice una secuencia concreta de pasos o procedimientos para lograr un resultado declarado. Por lo general, los usuarios generalmente saben, o tienen una idea de, cómo debe ser el objetivo final y qué "ingredientes" pertenecen al indicador. Sin embargo, es posible que no necesariamente conozcan el orden preciso de los pasos para lograr ese objetivo final.

Por ejemplo, un usuario puede querer una especificación precisa sobre cómo se debe implementar o automatizar un fragmento de código, como "crear un libro de jugadas de Ansible para ssh en un conjunto de servidores, copiar archivos de texto de cada servidor, generar un proceso de monitoreo en cada servidor y luego cerrar la conexión ssh a cada servidor". En otras palabras, este patrón representa una generalización del ejemplo de "dado los ingredientes en mi nevera, proporciona recetas para la cena". Un usuario también puede querer especificar un número determinado de posibilidades alternativas, como "proporcionar 3 formas diferentes de implementar una aplicación web en AWS usando contenedores Docker y Ansible con instrucciones paso a paso".

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Me gustaría lograr X
Sé que necesito realizar los pasos A, B, C
Proporcióname una secuencia completa de pasos
Completa los pasos que faltan
Identifica los pasos innecesarios

La primera declaración "Me gustaría lograr X" enfoca al LLM en el objetivo general que se debe construir para lograr la receta. Los pasos se organizarán y completarán para lograr secuencialmente el objetivo especificado. La segunda declaración proporciona la lista parcial de pasos que el usuario quisiera incluir en la receta general. Estos sirven como puntos intermedios para el camino que el LLM va a generar o restricciones en la estructura de la receta. La siguiente declaración en el patrón, "proporcióneme una secuencia completa de pasos", indica al LLM que el objetivo es proporcionar un orden secuencial completo de pasos. "Complete los pasos que faltan" ayuda a asegurar que el LLM intentará completar la receta sin más seguimiento, tomando algunas decisiones en nombre del usuario con respecto a los pasos faltantes, en lugar de simplemente indicar información adicional que se necesita. Finalmente, la última declaración, "identifique los pasos innecesarios", es útil para señalar imprecisiones en la solicitud original del usuario para que la receta final sea eficiente.

## Ejemplo de Implementación

Un ejemplo de uso de este patrón en el contexto de implementar una aplicación en la nube se muestra a continuación:

> "Estoy tratando de implementar una aplicación en la nube. Sé que necesito instalar las dependencias necesarias en una máquina virtual para mi aplicación. Sé que necesito registrarme en una cuenta de AWS. Por favor, proporciona una secuencia completa de pasos. Completa los pasos que faltan e identifica los pasos innecesarios."

Dependiendo del caso de uso y las restricciones, "instalar las dependencias necesarias en una máquina virtual" puede ser un paso innecesario. Por ejemplo, si la aplicación ya está empaquetada en un contenedor Docker, el contenedor podría implementarse directamente en el Servicio AWS Fargate, que no requiere ninguna administración de las máquinas virtuales subyacentes. La inclusión del lenguaje "identificar pasos innecesarios" hará que el LLM señale este problema y omita los pasos de la receta final.

## Consecuencias

Una consecuencia del patrón receta es que un usuario puede no tener siempre una descripción suficientemente especificada de lo que le gustaría implementar, construir o diseñar. Además, este patrón puede introducir un sesgo no deseado a partir de los pasos seleccionados inicialmente por el usuario, por lo que el LLM puede intentar encontrar una solución que los incorpore, en lugar de señalarlos como innecesarios. Por ejemplo, un LLM puede intentar encontrar una solución que instale dependencias para una máquina virtual, incluso si hay soluciones que no lo requieren.
