<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/prompts/README.md)|[Ingeniería de Prompts](/ingenieriaDePrompts/README.md)|[Patrones](/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Resuma documentos extensos por partes y construya un resumen completo de forma recursiva

> Bloque: Divide y vencerás

## ¿Por qué?

Dado que el procesamiento de información en grandes cantidades puede exceder la capacidad de los modelos GPT y reducir la precisión de las respuestas, segmentar y resumir documentos extensos en partes más pequeñas y manejables es una estrategia eficaz. La construcción recursiva de resúmenes permite consolidar la información de manera estructurada y coherente, garantizando la esencia y relevancia del contenido original.

## ¿Qué?

Es un enfoque que implica descomponer un documento largo en secciones o segmentos más pequeños, resumir cada uno de ellos de manera individual y luego unir estos resúmenes para formar un resumen completo y coherente del documento original.

## ¿Para qué?

- Para facilitar la comprensión y procesamiento de información en documentos extensos.
- Para asegurar que los detalles esenciales no se pierdan en el resumen.
- Para proporcionar una representación concisa y precisa del contenido original.

## ¿Cómo?

|||Ejempo|
|-|-|-|
Segmentación del documento|Divida el documento extenso en secciones o partes más pequeñas basándose en temas, subtítulos o segmentos lógicos.|En un informe anual, segmente por trimestre o por departamentos.
Resumir cada segmento|Una vez dividido, resuma cada sección de manera individual, asegurando que los puntos clave estén incluidos.|Resumir los logros y desafíos principales de un trimestre específico.
Construcción recursiva|Luego de obtener los resúmenes individuales, combine estos resúmenes para formar un resumen más amplio y coherente del documento completo. Esto puede requerir un proceso iterativo para asegurarse de que el resumen final sea coherente y representativo.|Consolidar los resúmenes de cada trimestre para obtener un panorama anual.

Este enfoque, al descomponer y reestructurar la información, permite que los modelos GPT aborden documentos extensos de manera más eficiente y precisa, garantizando una representación fiel y concisa del contenido original.