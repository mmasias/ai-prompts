# Tokens

## ¿Por qué?

Los tokens en un modelo de lenguaje son fundamentales porque **actúan como los bloques básicos de construcción de la información con la que el modelo trabaja**. La idea de tokenización surge como respuesta a la necesidad de convertir el texto crudo, altamente variable y extenso, en un formato más manejable y uniforme que pueda ser procesado eficientemente por algoritmos de aprendizaje automático. Esta necesidad se destaca especialmente en el procesamiento del lenguaje natural (PLN), donde es crucial capturar la semántica y la estructura del lenguaje humano de una forma que una máquina pueda entender y sobre la cual pueda generar predicciones precisas.

## ¿Qué?

|Token|Tokenización||
|-|-|-|
En el contexto de los modelos de lenguaje es la unidad de texto que ha sido previamente definida y que el modelo puede identificar y procesar.|Proceso mediante el cual se divide el texto en estos tokens.|Los tokens pueden ser tan simples como palabras, subpalabras o incluso caracteres. 

Ejemplos: [GPT-3.5](https://chatgpt.com/share/19648aa5-2b14-45d2-9f2e-a4d14c4789b7) / 
[GPT-4](https://chatgpt.com/share/c4296e54-ee43-4d25-a889-14651c25d17b) / 
[GPT-4o](https://chatgpt.com/share/8e65f139-5008-434c-b0ad-166c8a09eecd) / 
[Claude](https://claude.ai/chat/38740876-87e2-4088-a484-4c042f34d45a)

Por ejemplo, la palabra "unbelievable" podría tokenizarse en subpalabras como ["un", "believ", "able"] en un modelo que utilice una tokenización a nivel de subpalabra para manejar mejor la derivación y la composición en el lenguaje. 

## ¿Para qué?

La tokenización tiene varios propósitos clave:

1. **Estandarización del input:** Convierte el texto de entrada en un formato estándar que el modelo puede entender, lo cual es esencial para entrenar y operar el modelo de manera consistente.
1. **Manejo de vocabulario extenso:** Permite al modelo gestionar eficazmente un vocabulario amplio y diverso, incluyendo palabras nuevas o raras, mediante la descomposición en subpalabras o caracteres.
1. **Mejora del rendimiento del modelo:** Facilita el aprendizaje del modelo al reducir la dimensionalidad del problema de procesamiento de lenguaje y al ayudar al modelo a centrarse en las unidades semánticas más significativas.

## ¿Cómo?

El proceso de tokenización se realiza típicamente de la siguiente manera:

1. **Preprocesamiento:** Limpieza inicial de texto, como eliminar caracteres no deseados, corregir errores ortográficos, etc.
1. **División en tokens:** Aplicación de un algoritmo específico para descomponer el texto en unidades más pequeñas. Esto puede ser basado en reglas fijas, aprendizaje automático o una combinación de ambos.
1. **Indexación:** Cada token se mapea a un índice numérico en un vocabulario predefinido.
1. **Transformación en tensor:** Los índices de los tokens se convierten en tensores (vectores de números) para que puedan ser procesados por el modelo.

Profundizar en algunos de estos procesos, como la elección del algoritmo de tokenización o la gestión de un vocabulario extenso y dinámico, requeriría explorar más detalladamente temas como el aprendizaje no supervisado en PLN o las técnicas de embedding de palabras.

### 2See

||Paso|Descripción del paso|Entrada|Acción|Salida|
|-|-|-|-|-|-|
|1|Preprocesamiento|Convertir a minúsculas y eliminar signos de puntuación|"Artificial intelligence is unbelievable!"|Convertir todo a minúsculas y remover signos de puntuación|"artificial intelligence is unbelievable"|
|2|División en tokens|Dividir el texto en palabras o subunidades significativas|"artificial intelligence is unbelievable"|Tokenización por palabras|["artificial", "intelligence", "is", "unbelievable"]|
|3|Subtokenización (*Opcional*)|Manejar palabras desconocidas o raras descomponiéndolas en partes conocidas|"unbelievable"|Dividir palabras complejas en subpalabras|["un", "believ", "able"]|
|4|Indexación|Convertir tokens en índices numéricos basados en un vocabulario predefinido|["artificial", "intelligence", "is", "un", "believ", "able"]|Asignar un índice a cada token según el vocabulario del modelo|[481, 1056, 23, 178, 7890, 456]|
|5|Conversión a tensor|Preparar los índices para ser procesados por el modelo|[481, 1056, 23, 178, 7890, 456]|Transformar los índices en un tensor|Tensor de forma (1, 6)|

### 2See2

> A partir de un [prompt de @VictorTaelin](https://gist.github.com/VictorTaelin/e514844f4df9e5f182b28e5a07e44b17) - ([post original en X](https://twitter.com/VictorTaelin/status/1776096481704804789), *seguido de una muy interesante discusión*)

```
A: :B es un sistema con 4 tokens: `A#`, `#A`, `B#` y `#B`.

Un programa A: :B es una secuencia de tokens. Ejemplo:

    B# A# #B #A B#

Para *calcular* un programa, debemos reescribir los tokens vecinos, usando las reglas:

    A# #A ... se convierte en ... nada
    A# #B ... se convierte en ... #B A#
    B# #A ... se convierte en ... #A B#
    B# #B ... se convierte en ... nada

En otras palabras, siempre que dos fichas vecinas tengan su '#' una frente a la otra, deben reescribirse de acuerdo con la regla correspondiente. Por ejemplo, el primer ejemplo que se muestra aquí se calcula como:

    B# A# #B #A B# =
    B# #B A# #A B# =
    A# #A B# =
    B#

Los pasos fueron:

1. Reemplazamos `A# #B` por `#B A#`.
2. Reemplazamos `B# #B` por nada.
3. Reemplazamos `A# #A` por nada.
El resultado final fue simplemente "B#".

Ahora considera el siguiente programa:

A# B# B# #A B# #A #B

Calcúlalo completamente, paso a paso.
```

- [ChatGPT (prompt original en inglés)](https://chat.openai.com/share/838968d3-fe71-42d2-8ebf-6e352beafa1b)
- [ChatGPT](https://chat.openai.com/share/5541a172-7c71-4a4f-8dd4-95036262285e)
- [ChatGPT-4o](https://chat.openai.com/share/4fd77181-bf32-4ae7-97fa-0c0703ad9d19)
- [Gemini](https://g.co/gemini/share/f4dff41a1423)
- [Copilot](https://copilot.microsoft.com/sl/dZcFJEQ7QiG)
