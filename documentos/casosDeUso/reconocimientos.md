<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# CdU > Reconocimientos

## ¿Para qué?

Evaluar y comparar el contenido de guías docentes de asignaturas de dos universidades para determinar si cumplen con al menos un 70% de similitud en términos de contenidos.

## ¿Qué?

- Proceso:
  - Utilizar un LLM para procesar y analizar el contenido de Documento A y Documento B.
  - Comparar y evaluar la similitud entre los dos documentos.
  - Calcular el grado de similitud entre los contenidos, expresado como un porcentaje.
  - Generar un informe de evaluación que muestre el grado de similitud encontrado.
- Entradas:
  - Documento A (Guía Docente de Universidad A).
  - Documento B (Guía Docente de Universidad B).
- Salida:
  - Informe de Evaluación:
  - Porcentaje de similitud entre Documento A y Documento B.
  - Confirmación de si la similitud es igual o superior al 70%.

## ¿Por qué?

- Automatizar el proceso de evaluación y comparación de guías docentes de asignaturas de diferentes universidades para determinar si cumplen con un nivel mínimo de similitud del 70%.
- Ahorrar tiempo y esfuerzo en la revisión manual de los contenidos de las guías docentes.
- Facilitar la toma de decisiones sobre la equivalencia de asignaturas entre universidades o la transferencia de créditos.

## ¿Cómo?

|||
|-|-|
Paso 1: Preparación de Datos|Obtener los documentos (Guías Docentes) de las dos universidades que se desean comparar.
Paso 2: Procesamiento de Datos|Utilizar un LLM de procesamiento de lenguaje natural basada para analizar y procesar los contenidos de ambos documentos.
Paso 3: Comparación de Contenidos|Comparar el resultado del procesamiento para ambos documentos.<br>Calcular la similitud entre los contenidos utilizando métricas adecuadas.
Paso 4: Generación de Informe|Generar un informe que incluya el porcentaje de similitud calculado.<br>Confirmar si el porcentaje de similitud es igual o superior al 70%.
Paso 5: Toma de Decisiones|Basándose en el informe, tomar decisiones sobre la equivalencia de asignaturas o la transferencia de créditos entre las dos universidades.

### 🤖: ChatGPT

|Prompt(s)|Comentario|
|-|-|
*Te voy a adjuntar dos archivos, que contienen cada uno la guía docente de una asignatura por su respectiva universidad. Compara los contenidos impartidos de estas asignaturas y dime si coinciden en al menos en un 70%, utilizando como referencia los contenidos del documento que corresponda a la Universidad Europea del Atlántico. Para visualizar la valoración, muestra una tabla en la que se vea esta comparación, con una columna para los contenidos y una columna por asignatura, luego incluye los contenidos en las filas. En los encabezados de las columnas pones los nombres de cada archivo y agrega una columna adicional que diga si hay coincidencia o no. Luego compara también las competencias especificas y los resultados de aprendizaje*|[Iteración 1](https://chat.openai.com/share/b8873029-ca42-483d-80b6-56da031b6371)<br>Dudas entre usar la extracción directa del PDF o un método mediante OCR. Hay timeouts. No termina de ser eficiente.


### 🤖: Claude.ai

#### Iteración 001

|Prompt|Para qué|Comentario
|-|-|-
Compara los contenidos de las asignaturas que te envío y dime si coinciden en al menos en un 70%, utilizando como referencia los contenidos del documento de la Universidad Europea del Atlántico. Crea una tabla que muestre esta comparación, con una columna por asignatura y los contenidos en las filas. En los encabezados de las columnas pones los nombres de cada archivo y agrega una columna adicional que diga si hay coincidencia o no. Luego compara también las competencias especificas y los resultados de aprendizaje|Ayuda para evaluar el reconocimiento de asignaturas|Necesita supervisión
Compara las competencias y los resultados de aprendizaje|Extender la comparación|

##### Respuesta 
---
Aquí está la tabla comparativa de los contenidos de las dos asignaturas de Programación I:

| Introduccion_al_Software.pdf | C1S1 - IYA003 - Programacion I - rMMV-2022-09-02.docx | ¿Coinciden? |
|-|-|-|
| Fundamentos de programación en C. Estructura de un programa C. Entrada/salida de texto y de caracteres. Entrada/salida de números. Funciones | Tema 2: El lenguaje de programación JAVA. Características. Instalación y Primeros programas. | No |
| Datos y expresiones. Tipos primitivos. Variables y constantes. Operadores y expresiones. Conversión de tipos. Paso de parámetros. Uso de funciones matemáticas. | Tema 3: Variables, Tipos de Datos y Operadores. Variables y tipos de datos. Identificador de variable. Operadores aritméticos. Operadores de asignación. | Parcialmente |
| Estructuras algorítmicas. Instrucción condicional. Instrucción condicional múltiple. Instrucciones de bucle. Recursividad. Descripción de algoritmos mediante pseudocódigo. | Tema 5: Estructuras de control alternativas. Construcción de expresiones lógicas. Operadores lógicos y relacionales. Estructura alternativa simple y doble. Estructura alternativa múltiple. Tema 6: Estructuras de control repetitivas. Estructuras de control repetitivas. Estructura de control repetitiva while y do-while. Estructura de control repetitiva for. | Sí |  
| Datos compuestos. Arrays y tablas unidimensionales. Algoritmos de recorrido y búsqueda. Arrays multidimensionales. Tipos enumerados. Estructuras | Tema 7: Tipos de variables II. Arreglos. Introducción a los arreglos. Arreglos unidimensionales. Operaciones básicas sobre arreglos. Arreglos multidimensionales. | Sí |
| Programación modular. Diseño modular. Ámbito de las variables. Bibliotecas | Tema 8: Métodos estáticos. Introducción. Declaración de métodos. Paso de variables. | Sí |
| Estructuras de datos dinámicas. Definición. Declaración de punteros y asignación de memoria. Reserva dinámica de memoria. Punteros y funciones. Punteros y estructuras |  | No |
| Uso de sistemas operativos. Uso de un entorno integrado de desarrollo de programas. Uso de una hoja de cálculo. Uso de una base de datos. |  | No |

En cuanto a las competencias específicas y los resultados de aprendizaje, ambas coinciden en desarrollar:

- Conocimientos sobre programación en un lenguaje como Java/C.  
- Capacidad para implementar algoritmos y programas.
- Manejo de variables, tipos de datos, sentencias de control, funciones, etc.

En conclusión, diría que el contenido de las dos asignaturas tiene aproximadamente un 70-80% de coincidencia en los conceptos centrales de programación imperativa y estructurada en un lenguaje como Java/C. Las diferencias se encuentran en algunos contenidos específicos de cada una.

#### Iteración 002

|Prompt(s)|Comentario|
|-|-|
*Te voy a adjuntar dos archivos, que contienen cada uno la guía docente de una asignatura por su respectiva universidad. Compara los contenidos impartidos de estas asignaturas y dime si coinciden en al menos en un 70%, utilizando como referencia los contenidos del documento que corresponda a la Universidad Europea del Atlántico. Para visualizar la valoración, muestra una tabla en la que se vea esta comparación, con una columna para los contenidos y una columna por asignatura, luego incluye los contenidos en las filas. En los encabezados de las columnas pones los nombres de cada archivo y agrega una columna adicional que diga si hay coincidencia o no. Luego compara también las competencias especificas y los resultados de aprendizaje*|[Doc1](/documentos/imagenes/CdU-Reconocimientos-2014-3ProgramacionI.docx) / [Doc2](/documentos/imagenes/CdU-Reconocimientos-GII-IYA003.pdf)  



##### Transcripción de la respuesta 

Entendido. Voy a comparar los contenidos, competencias específicas y resultados de aprendizaje de las dos asignaturas, usando como referencia el documento de la Universidad Europea del Atlántico (GII-IYA003.pdf). Primero, presentaré una tabla comparativa de los contenidos, y luego analizaré las competencias específicas y los resultados de aprendizaje.

Tabla comparativa de contenidos:

| Contenidos (GII-IYA003.pdf) | GII-IYA003.pdf | 2014-3ProgramacionI.docx | Coincidencia |
|---------------------------|----------------|--------------------------|--------------|
| Tema 1: Algoritmos | Sí | Sí (incluido en Justificación) | Sí |
| Tema 2: El lenguaje de programación JAVA | Sí | No (usa C++) | No |
| Tema 3: Variables, Tipos de Datos y Operadores | Sí | Sí (implícito en varios temas) | Sí |
| Tema 4: Sentencias de entrada y salida | Sí | Sí (implícito en varios temas) | Sí |
| Tema 5: Estructuras de control alternativas | Sí | Sí (implícito en varios temas) | Sí |
| Tema 6: Estructuras de control repetitivas | Sí | Sí (implícito en varios temas) | Sí |
| Tema 7: Tipos de variables II. Arreglos | Sí | Sí (implícito en varios temas) | Sí |
| Tema 8: Métodos estáticos | Sí | No (no se menciona específicamente) | No |
| Archivos y manejo de datos | No | Sí | No |
| Memoria dinámica | No | Sí | No |
| Pilas y colas | No | Sí | No |

Basándonos en esta comparación, podemos ver que hay coincidencia en 6 de los 8 temas principales del documento GII-IYA003.pdf, lo que representa un 75% de coincidencia. Sin embargo, el documento 2014-3ProgramacionI.docx incluye temas adicionales que no están presentes en GII-IYA003.pdf.

Comparación de competencias específicas:

Las competencias específicas no coinciden exactamente, pero hay algunas similitudes:

1. GII-IYA003.pdf se enfoca en:
   - Conocimientos básicos de programación y uso de ordenadores
   - Diseño y desarrollo de aplicaciones
   - Procedimientos algorítmicos y estructuras de datos

2. 2014-3ProgramacionI.docx se centra en:
   - Técnicas de programación estructurada y orientada a objetos
   - Desarrollo de criterio para selección y aplicación del lenguaje
   - Hábito de investigación

Aunque no hay una coincidencia exacta, ambos programas buscan desarrollar habilidades de programación y resolución de problemas.

Comparación de resultados de aprendizaje:

1. GII-IYA003.pdf especifica:
   - Conocer los fundamentos de un lenguaje de programación de alto nivel
   - Conocer los principales algoritmos para resolución de problemas comunes
   - Saber manejar tipos de datos, estructuras de datos y tipos abstractos de datos

2. 2014-3ProgramacionI.docx menciona:
   - Realizar programas estructurados y orientados a objetos
   - Aplicar criterios de investigación en un lenguaje de programación a elección
   - Desarrollar aplicaciones agnósticas al sistema operativo

Aunque los resultados de aprendizaje no coinciden exactamente, ambos programas buscan que los estudiantes sean capaces de desarrollar programas y aplicar conceptos de programación.

En conclusión, aunque hay diferencias significativas en el lenguaje de programación utilizado (Java vs C++) y en algunos temas específicos, los contenidos fundamentales de programación coinciden en más del 70%. Las competencias específicas y los resultados de aprendizaje, aunque no son idénticos, tienen objetivos similares en cuanto al desarrollo de habilidades de programación y resolución de problemas.

### Versión 2025

Utilizando ChatGPT gratuito.

- Paso 0: preparar una [tabla con asignaturas / contenidos](reconocimientos_gII.md).
- Paso 1: Hacer [un caso de prueba](https://chatgpt.com/share/68406c3c-e0d0-8002-a289-f53dce85881a) suficientemente denso.
- Paso 2: Alcanzado el Nirvana, pedirle que reformule un único prompt, de modo que capture todas las casuísticas que se hayan abordado en el caso de prueba.
  > Quiero que evalúes el posible reconocimiento de asignaturas universitarias.
  >
  > 1. Tengo un plan de estudios de referencia que contiene las asignaturas oficiales de una carrera (te lo proporcionaré al inicio).
  > 2. Te enviaré los sílabos o contenidos de asignaturas externas para que determines si pueden reconocerse por alguna asignatura del plan de referencia.
  > 3. Un reconocimiento es posible **solo si**:
  >
  > * Hay al menos un **70% de similitud global en contenidos**.
  > * **La densidad de contenido** (cantidad de horas o profundidad temática) es comparable a la asignatura de referencia.
  > * **No se permiten reconocimientos parciales**: la asignatura externa debe ser equivalente a una asignatura entera del plan de referencia, no a una parte de varias asignaturas.
  >
  > 4. Quiero que tu respuesta sea estricta:
  >
  > * **SI**: indicando la asignatura del plan por la cual puede reconocerse.
  > * **NO**: si no puede reconocerse, y sin intentar combinar varias asignaturas.
  >
  > 5. Solo si el porcentaje de similitud es **mayor al 60%**, pero no alcanza el 70%, indícame la asignatura más cercana y el porcentaje aproximado.
  > 6. Si el porcentaje es menor o no hay posibilidad, solo responde **NO**.
  >
  > ¿Entiendes estas reglas? Si es así, te enviaré el plan de estudios y comenzamos.
- Paso 3: Iniciar una charla de reconocimiento con el prompt indicado y la tabla de asignaturas.

