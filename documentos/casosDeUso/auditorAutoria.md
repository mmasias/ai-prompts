<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/documentos/prompts/README.md)|[Ingeniería de Prompts](/documentos/ingenieriaDePrompts/README.md)|[Patrones](/documentos/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/documentos/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Caso de Uso > Auditor de autoría

## ¿Por qué?

El plagio en la escritura académica, periodística o en cualquier tipo de contenido es un problema serio que compromete la integridad y la originalidad del trabajo. La detección de plagio no siempre es sencilla, especialmente cuando las similitudes no son obvias o están hábilmente disfrazadas.

Utilizar un Modelo de Lenguaje de Aprendizaje Profundo (LLM) para verificar similitudes entre dos artículos puede ofrecer una solución automatizada y eficiente para identificar posibles casos de plagio, asegurando así la originalidad y autenticidad del contenido.

## ¿Qué?

Este caso de uso implica el desarrollo y la implementación de un sistema basado en LLM que analiza y compara dos textos para identificar similitudes significativas en su estructura, fraseo o contenido. El sistema utilizará las capacidades avanzadas de procesamiento de lenguaje natural de un LLM para realizar un análisis detallado y contextual de los textos, buscando coincidencias que puedan sugerir plagio.

## ¿Para qué?

- Detectar eficazmente **posibles casos de plagio** en documentos escritos.
- Proporcionar a los educadores, editores y otros profesionales una herramienta rápida y confiable para **verificar la originalidad del contenido**.
- Mejorar la integridad académica y profesional al desalentar y detectar el plagio.
- Ahorrar tiempo y recursos en el proceso de revisión de textos.

## ¿Cómo?

|Preparación de Datos|Diseño del Sistema|Pruebas y validación|Implementación|Mejora|
|-|-|-|-|-|
Recopilar pares de artículos para el análisis, incluyendo tanto ejemplos de textos originales como textos plagiados conocidos para entrenamiento y prueba.|Configurar el LLM para procesar y analizar textos. Esto puede incluir la tokenización del texto, análisis semántico y sintáctico, y comparación de patrones de escritura.|Probar el sistema con una variedad de documentos para evaluar su precisión y capacidad para detectar plagio en diferentes estilos y formatos de escritura.|Integrar el sistema en un entorno donde educadores y profesionales puedan subir documentos para su revisión.|Recopilar retroalimentación de los usuarios para mejorar continuamente la precisión y usabilidad del sistema.
||Implementar algoritmos para puntuar y resaltar similitudes entre los textos.||Proporcionar una interfaz de usuario intuitiva para presentar los resultados del análisis.

Ejemplo 2: [Documento original (en inglés)](https://instituciones.sld.cu/psicosaludhabana/files/2012/02/f_usability_jh1.pdf) / [Documento plagiado](auditorAutoriaArticuloPlagiadoArticulo.md)

### Transcripciones

|Motor|Comentario|
|-|-|
[ChatGPT](https://chat.openai.com/share/eb63349b-849b-4b5f-b5df-8f52a1890454) / [Ejemplo 2](https://chat.openai.com/share/f77c7c2c-e5e6-4c7e-8671-f429e7e7130a)
[Perplexity]
[Claude]
[Bard]
[NeuroFlash]

|Buenas prácticas|& Reflexiones|
|-|-|
|Inicio claro|Comenzamos con una instrucción precisa sobre el objetivo general (en este caso, construir una oferta de trabajo).|
|Estructura abierta|Permitimos que la IA nos guíe a través de preguntas estructuradas y nos ofrezca espacio para ir llenando cada sección.|
|Feedback inmediato|Respondemos y ajustamos la información según lo propuesto por la IA. Si es necesario, pedimos aclaraciones o especificamos más.|
|Continuación dinámica|Una vez que una sección esté completa, indicamos que estamos listos para seguir adelante con la siguiente sección o parte.|
|Conclusión|Al final, repasamos el contenido global para asegurarnos de que cumple con nuestras expectativas y realizamos ajustes finales si es necesario.|

#### Antipatrón

*[:link:]() EJ_DE_ANTI_PATRON*

|Punto|Detalle|
|-|-|
