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

## Diferencias entre modelos (2024-2025)

Cada familia de modelos utiliza su propio sistema de tokenización, lo que significa que **el mismo texto puede consumir diferente cantidad de tokens** según el modelo:

|Modelo|Sistema de tokenización|Características|
|-|-|-|
|**GPT** (OpenAI)|tiktoken (BPE)|~4 caracteres por token (inglés)<br>Menos eficiente en idiomas no latinos
|**Claude** (Anthropic)|Tokenizador propio|Similar a GPT pero optimizado diferente<br>Ligeramente más eficiente en algunos idiomas
|**Gemini** (Google)|SentencePiece|Mayor eficiencia en textos multilingües<br>Mejor manejo de idiomas asiáticos
|**Llama** (Meta)|Tokenizador BPE propio|Vocabulario de 32K tokens<br>Optimizado para eficiencia

**Herramientas para visualizar tokenización:**
- [OpenAI Tokenizer](https://platform.openai.com/tokenizer) - Para modelos GPT
- [Anthropic Token Counter](https://docs.anthropic.com/claude/reference/token-counting) - Documentación de Claude
- [tiktoken (Python)](https://github.com/openai/tiktoken) - Librería oficial de OpenAI

## Optimización de tokens

Con el auge de APIs que cobran por token, optimizar el uso de tokens es cada vez más importante:

### Estrategias de optimización

|Estrategia|Ahorro potencial|Cuándo usar|
|-|:-:|-|
|**Eliminar verbosidad**|10-30%|Siempre - mantén C³ (Claro, Concreto, Conciso)
|**Usar abreviaciones consistentes**|5-15%|Prompts técnicos repetitivos
|**Estructurar con símbolos vs. palabras**|10-20%|Listas, datos estructurados (`-` vs "punto número")
|**Comprimir ejemplos largos**|20-40%|Few-shot prompting con muchos ejemplos
|**Cachear instrucciones del sistema**|50-90%|APIs que soportan caching (Claude, GPT)

### Ejemplo práctico

```markdown
❌ Verboso (más tokens):
"Por favor, podrías ser tan amable de proporcionar un resumen detallado y completo
del siguiente texto, asegurándote de incluir todos los puntos importantes y las
ideas principales que se presentan en el documento"

✅ Optimizado (menos tokens):
"Resume el texto siguiente, incluyendo puntos e ideas principales:"
```

**Nota importante:** La optimización de tokens NO debe sacrificar la [claridad](mejoresPracticas/8virtudesDelPrompting.md). Un prompt confuso que usa menos tokens pero genera respuestas incorrectas es contraproducente.

### 2See

||Paso|Descripción del paso|Entrada|Acción|Salida|
|-|-|-|-|-|-|
|1|Preprocesamiento|Convertir a minúsculas y eliminar signos de puntuación|"Artificial intelligence is unbelievable!"|Convertir todo a minúsculas y remover signos de puntuación|"artificial intelligence is unbelievable"|
|2|División en tokens|Dividir el texto en palabras o subunidades significativas|"artificial intelligence is unbelievable"|Tokenización por palabras|["artificial", "intelligence", "is", "unbelievable"]|
|3|Subtokenización (*Opcional*)|Manejar palabras desconocidas o raras descomponiéndolas en partes conocidas|"unbelievable"|Dividir palabras complejas en subpalabras|["un", "believ", "able"]|
|4|Indexación|Convertir tokens en índices numéricos basados en un vocabulario predefinido|["artificial", "intelligence", "is", "un", "believ", "able"]|Asignar un índice a cada token según el vocabulario del modelo|[481, 1056, 23, 178, 7890, 456]|
|5|Conversión a tensor|Preparar los índices para ser procesados por el modelo|[481, 1056, 23, 178, 7890, 456]|Transformar los índices en un tensor|Tensor de forma (1, 6)|

### 2See2

Solicitud: **escribe 10 oraciones que terminen con la palabra "Manzana"**

- [GPT-3.5](https://chatgpt.com/share/b4d0ea9a-01be-4cdb-870b-7c045b0f74f8)
- [GPT-4](https://chatgpt.com/share/36d73f87-c13a-442c-b52f-673bbaeb6e2f)
- [GPT-4o](https://chatgpt.com/share/f8e74da9-73ca-455e-ad6f-600cb6c22d69)
- [Claude](https://claude.ai/chat/1f7c267e-5b77-4e12-9ce7-1dc156b9251b)
- [Gemini](https://g.co/gemini/share/0ab6e9d33141)
- [Copilot](https://copilot.microsoft.com/sl/b0oJi4iAlNY)
- [Mistral](https://chat.mistral.ai/chat/7514447a-4f0e-42a1-b97c-36610a0635fd)
- [Meta·Llama@Huggingface](https://huggingface.co/chat/conversation/66770a226601390add72bbde)

### 2See3

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

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[¿Qué son los prompts?](README.md)<br>Base conceptual|Fundamentos > Prompts > **Tokens** (Conceptos técnicos)|[Ventana de contexto](ventanaDeContexto.md)<br>Aplicación práctica de tokens
|||[Mejores prácticas](mejoresPracticas/README.md)<br>Optimización considerando limitaciones

<i>**Relacionado**: [Anatomía](anatomia.md) - Los tokens afectan el diseño de prompts / [0-Shot Prompting](../ingenieriaDePrompts/0ShotPrompting.md) - Técnica que debe considerar límites de tokens</i>

</div>
