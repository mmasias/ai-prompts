# Tokens

> A partir de un [prompt de @VictorTaelin](https://gist.github.com/VictorTaelin/e514844f4df9e5f182b28e5a07e44b17)

> [Post original en X](https://twitter.com/VictorTaelin/status/1776096481704804789) (*seguido de una muy interesante discusión*)

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
- [Gemini](https://g.co/gemini/share/f4dff41a1423)
- [Copilot](https://copilot.microsoft.com/sl/dZcFJEQ7QiG)
