<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Prompts

## ¿Por qué?

|Evolución (*natural?* / *lógica?* / *esperada?* / *definitiva?*) de los mecanismos de interacción.|
|-|
Los LLMs **se entrenan principalmente en grandes conjuntos de datos de texto**, por lo que son muy buenos para generar y comprender texto. El habla requeriría entrenamiento adicional con conjuntos de datos de voz.
El procesamiento de lenguaje natural para texto está **más avanzado** que para voz. 
Interactuar a través de texto permite una **comunicación asíncrona**. 
Los prompts de texto proporcionan un **registro claro** de la conversación. Las conversaciones habladas son más efímeras.
Los usuarios pueden **tomarse su tiempo** para escribir prompts y leer respuestas en lugar de tener una conversación en tiempo real.
Es más fácil para un LLM **analizar** correctamente un prompt escrito que uno hablado.
**Es más fácil detectar y corregir errores** en un formato de texto. Los LLMs aún cometen errores que los humanos pueden detectar más fácilmente al leer.
Muchas aplicaciones de LLMs como la generación de código, resúmenes y traducciones se prestan mejor al formato de texto.

> Aún así, se le puede pedir que [generar elementos gráficos](/casosDeUso/esquemasDiagramas.md).

## ¿Qué?

<div align="center">

|![](/documentos/imagenes/modelosUML/sesion.svg)|
|-|
Instrucción o solicitud de información que se le da a un modelo de lenguaje, en forma de pregunta o enunciado que inicia la conversación o solicita una respuesta del modelo.
Por ejemplo, "*¿Cuál es la capital de Francia?*" o "*Escribe un poema sobre la primavera*".

</div>

## ¿Para qué?

Los prompts se utilizan para interactuar con modelos de lenguaje, solicitar información específica o realizar tareas particulares. Proporcionan la **dirección** y el **contexto** necesarios para que la IA genere respuestas útiles y pertinentes.

## ¿Cómo?

- [Anatomía de un prompt](anatomia.md): Componentes, elementos & recetas.
- [La ventana de contexto](ventanaDeContexto.md)
  - [Custom instructions](customInstructions.md)
  - [GPTs](GPTs.md)
- [Mejores prácticas](mejoresPracticas/README.md)
- ["Hoja de trucos" (a.k.a. atajos)](cheatsheet/README.md)
