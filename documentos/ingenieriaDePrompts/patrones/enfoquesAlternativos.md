<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Patrón Enfoques Alternativos

## Intención y Contexto

La intención de este patrón es asegurar que un LLM siempre ofrezca formas alternativas de realizar una tarea, de modo que un usuario no siga únicamente los enfoques con los que está familiarizado. El LLM puede proporcionar alternativas que hagan que el usuario reflexione sobre lo que está haciendo y determine si es el mejor enfoque para alcanzar su objetivo. Además, resolver la tarea puede informar o enseñar al usuario sobre nuevos conceptos para un seguimiento posterior.

## Motivación

Los humanos a menudo sufren de sesgos cognitivos que los llevan a elegir un enfoque particular para resolver un problema, incluso cuando no es el enfoque correcto o "mejor". Además, es posible que los humanos no estén al tanto de enfoques alternativos a los que han utilizado en el pasado. La motivación del Patrón de Enfoques Alternativos es asegurar que el usuario esté al tanto de enfoques alternativos para seleccionar un mejor enfoque para resolver un problema disolviendo sus sesgos cognitivos.

## Estructura e Ideas Clave

Declaraciones contextuales fundamentales:

|Declaraciones Contextuales
|-|
Dentro del alcance X, si hay formas alternativas de lograr lo mismo, enumera los mejores enfoques alternativos.
(Opcional) compara/contrasta los pros y contras de cada enfoque.
(Opcional) incluye la forma original que pregunté.
(Opcional) pregúntame qué enfoque me gustaría usar.

La primera declaración, "dentro del alcance X", delimita la interacción a un objetivo, tema o límites particulares en el cuestionamiento. El alcance son las restricciones que el usuario está imponiendo a los enfoques alternativos. El alcance podría ser "para decisiones de implementación" o "para el despliegue de la aplicación". El alcance asegura que cualquier alternativa se ajuste a los límites o restricciones a los que el usuario debe adherirse.

La segunda declaración, "si hay formas alternativas de lograr lo mismo, enumera los mejores enfoques alternativos", instruye al LLM a sugerir alternativas. Como con otros patrones, la especificidad de las instrucciones puede aumentarse o incluir información contextual específica del dominio. Por ejemplo, la declaración podría delimitarse a "si hay formas alternativas de lograr lo mismo con el marco de software que estoy usando" para evitar que el LLM sugiera alternativas que son inherentemente inviables porque requerirían demasiados cambios en otras partes de la aplicación.

Dado que el usuario puede no estar al tanto de los enfoques alternativos, también es posible que no esté al tanto de por qué uno elegiría una de las alternativas. La declaración opcional "compara/contrasta los pros y contras de cada enfoque" añade criterios de toma de decisiones al análisis. Esta declaración asegura que el LLM proporcionará al usuario la justificación necesaria para los enfoques alternativos. La declaración final, "pregúntame qué enfoque me gustaría usar", ayuda a eliminar la necesidad de que el usuario copie/pegue o introduzca manualmente un enfoque alternativo si se selecciona uno.

## Ejemplo de Implementación

Ejemplo de implementación de indicativo para generar, comparar y permitir al usuario seleccionar uno o más enfoques alternativos:

> “Cada vez que te pida desplegar una aplicación en un servicio en la nube específico, si hay servicios alternativos para lograr lo mismo con el mismo proveedor de servicios en la nube, enumera los mejores servicios alternativos y luego compara/contrasta los pros y contras de cada enfoque con respecto a coste, disponibilidad y esfuerzo de mantenimiento e incluye la forma original que pregunté. Luego, pregúntame con qué enfoque me gustaría continuar.”

Esta implementación del Patrón de Enfoques Alternativos está específicamente adaptada para el contexto de la ingeniería de software y se centra en el despliegue de aplicaciones en servicios en la nube. El indicativo tiene la intención de interceptar lugares donde el desarrollador puede haber hecho una selección de servicio en la nube sin plena conciencia de servicios alternativos que pueden tener un precio más competitivo o ser más fáciles de mantener. El indicativo dirige a ChatGPT a listar los mejores servicios alternativos que pueden lograr la misma tarea con el mismo proveedor de servicios en la nube (proporcionando restricciones a las alternativas) y comparar y contrastar los pros y contras de cada enfoque.

## Consecuencias

Este patrón es efectivo en su forma genérica y se puede aplicar eficazmente a una variedad de tareas. Las refinaciones podrían incluir tener un catálogo estandarizado de alternativas aceptables en un dominio específico del cual el usuario debe seleccionar. El Patrón de Enfoques Alternativos también puede usarse para incentivar a los usuarios a seleccionar uno de un conjunto aprobado de enfoques mientras les informa de los pros/contras de las opciones aprobadas.
