<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

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

> Aún así, se le puede pedir que [generar elementos gráficos](/documentos/casosDeUso/esquemasDiagramas.md).

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

- [La ventana de contexto](ventanaDeContexto.md)
- [Anatomía de un prompt](anatomia.md): Componentes, elementos & recetas.
- [Ejemplos varios (a.k.a. *taller*)](ejemplos.md)
  - [Custom instructions](customInstructions.md)
  - [GPTs](GPTs.md)
- [Mejores prácticas](mejoresPracticas/README.md)
- ["Hoja de trucos" (a.k.a. atajos)](cheatsheet/README.md)

---

<div align=right><font size=-2>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Modelos de lenguaje](../LLMs.md)<br>Comprende cómo funcionan los LLMs|Fundamentos > **Prompts** (Introducción)|[Anatomía de un prompt](anatomia.md)<br>Estructura y componentes
|[Introducción general](../intro.md)<br>Contexto de la IA generativa||[Ventana de contexto](ventanaDeContexto.md)<br>Limitaciones técnicas fundamentales

<i>**Relacionado**: [Ingeniería de Prompts](../ingenieriaDePrompts/README.md) - Metodología avanzada / [Mejores prácticas](mejoresPracticas/README.md) - Aplicación práctica inmediata</i>

</font></div>
