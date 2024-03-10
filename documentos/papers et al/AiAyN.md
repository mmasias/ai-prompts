<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Attention Is All You Need

## ¿Para qué?

El paper "Attention Is All You Need" fue escrito para presentar una nueva arquitectura para modelos de traducción automática denominada Transformer, que se basa principalmente en mecanismos de atención para procesar los datos de entrada y salida en lugar de depender de las redes recurrentes (RNNs) o convolucionales (CNNs) que se usaban previamente en este campo.

## ¿Qué?

La arquitectura Transformer introduce una estructura que permite procesar entradas y salidas en paralelo (en lugar de secuencialmente, como es el caso con RNNs), y se basa fuertemente en el mecanismo de atención, en particular, la "atención de producto punto escalado" (scaled dot-product attention). Esta atención permite que el modelo asigne diferentes pesos a diferentes palabras en función de su relevancia para la traducción o tarea específica.

## ¿Por qué?

Las RNNs, aunque efectivas, tienen problemas de eficiencia y dificultades para manejar dependencias a largo plazo debido a problemas como el desvanecimiento del gradiente. Por otro lado, las CNNs, aunque pueden procesar información en paralelo, no están diseñadas específicamente para capturar las dependencias temporales en los datos secuenciales. La arquitectura Transformer supera estos problemas mediante el uso de mecanismos de atención, lo que le permite capturar dependencias a largo plazo y procesar datos en paralelo, mejorando tanto la eficiencia como la capacidad de modelado.

## ¿Cómo?

La arquitectura Transformer se basa en varias capas de atención y tiene dos componentes principales: el codificador (encoder) y el decodificador (decoder).

- *Codificador:* Consiste en una serie de capas idénticas. Cada capa tiene dos sub-capas: una sub-capa de atención de múltiples cabezas y una red feed-forward totalmente conectada. La atención permite al modelo centrarse en diferentes palabras en función de su relevancia.

- *Decodificador:* También está formado por capas idénticas. Sin embargo, además de las sub-capas mencionadas para el codificador, hay una tercera sub-capa que realiza atención sobre la salida del codificador. Esto permite que el decodificador tenga información sobre todas las palabras en la entrada al producir la traducción.

La relevancia del Transformer radica en que se ha convertido en el pilar de muchos modelos posteriores de procesamiento de lenguaje natural, especialmente aquellos utilizados para tareas de comprensión y generación de texto. El modelo BERT, por ejemplo, que ha revolucionado la comprensión del lenguaje natural, se basa en la arquitectura Transformer.

## Aplicación:

Mientras que el paper original se centró en la traducción automática, la arquitectura Transformer ha encontrado aplicaciones en una amplia variedad de tareas de procesamiento de lenguaje natural, como clasificación de texto, generación de texto, resumen automático, respuesta a preguntas y más. Su flexibilidad y eficiencia lo han convertido en un estándar en la industria y la investigación.