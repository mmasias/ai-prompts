<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Ingeniería de Prompts

## Principios fundamentales

### 1. Usar lenguaje simple

**Por qué:** La claridad reduce ambigüedad. Los modelos interpretan literalmente, sin inferir intenciones ocultas.

**Cómo:**
- ✅ "Lista 5 ventajas de TypeScript"
- ❌ "Dime cositas buenas de ese lenguaje del que hablamos antes"

**Cuándo romper la regla:** Cuando el dominio requiere terminología técnica específica.

---

### 2. Ser específico

**Por qué:** Los modelos pueden responder casi cualquier pregunta, pero respuestas genéricas son poco útiles.

**Cómo:**
- ✅ "Explica recursividad con ejemplo en Python, máximo 10 líneas de código"
- ❌ "Explica recursividad"

**Nivel de especificidad:**
```
Genérico → Dominio → Formato → Restricciones → Criterios de éxito
```

---

### 3. Mantener estructura lógica

**Por qué:** Instrucciones organizadas facilitan que el modelo procese cada parte correctamente.

**Cómo:**
```markdown
CONTEXTO: [Situación]
TAREA: [Qué hacer]
FORMATO: [Cómo presentarlo]
RESTRICCIONES: [Límites]
```

**Anti-patrón:** Mezclar instrucciones, contexto y ejemplos sin separación clara.

---

### 4. Incluir ejemplos

**Por qué:** Los ejemplos enseñan patrones mejor que explicaciones abstractas ([X-Shot Prompting](xShotPrompting.md)).

**Cuántos ejemplos:**
- **0-shot**: Tareas generales que el modelo conoce
- **1-shot**: Mostrar formato esperado
- **Few-shot (3-5)**: Enseñar patrones específicos
- **Many-shot**: Dominios muy especializados

---

### 5. Tener en cuenta el contexto

**Por qué:** El contexto determina la interpretación. Sin contexto adecuado, respuestas pueden ser incorrectas aunque bien formuladas.

**Tipos de contexto:**
- **Temporal:** "Usando estándares de 2024..."
- **Situacional:** "Para audiencia técnica..." vs "Para principiantes..."
- **Acumulativo:** Conversaciones largas ([Chain of Thought](chainOfThought.md))
- **Externo:** Documentos, datos ([RAG](RAG.md))

## ¡Bah!

<img src="../imagenes/ingDePrompts.png" width="30%" align=right>

Al final, la ingeniería de prompts no es más que aplicar lo que se enseña desde la infancia sobre comunicación efectiva:


- **Habla despacio**: Da tiempo al modelo para procesar cada parte de la instrucción
- **Habla claro**: Usa lenguaje específico y sin ambigüedades
- **Piensa antes de hablar**: Estructura tus ideas antes de formular el prompt
- **No te aturulles**: Mantén la calma y la claridad en instrucciones complejas
- **No te precipites**: Permite que el razonamiento se desarrolle paso a paso
- **De a poquitos**: Divide problemas grandes en partes manejables

La tecnología avanza, pero los principios de buena comunicación siguen siendo los mismos.

---

## Consideraciones modernas (2024-2025)

### Ventanas de contexto largas

Con modelos que manejan 128K-2M tokens ([ventana de contexto](../prompts/ventanaDeContexto.md)), cambia la estrategia:

**Antes (GPT-3.5, 4K tokens):**
- Obsesión por brevedad
- Resúmenes agresivos
- Múltiples llamadas

**Ahora (GPT-4o, Claude Sonnet 4.5, 200K tokens):**
- Puedes dar contexto completo
- Documentos enteros como entrada
- Conversaciones largas sin pérdida de contexto

**Pero cuidado:** Más tokens = más costo. Usa contexto extenso solo cuando aporte valor real.

---

### Razonamiento extendido

Modelos como o1 razonan internamente antes de responder:

**Implicación para prompts:**
- ❌ Ya no necesitas "piensa paso a paso" con o1
- ✅ Sigue siendo útil con GPT-4o, Claude, Gemini
- ✅ Especifica **qué** quieres, deja el **cómo** al modelo

---

### Multimodalidad

Los modelos modernos procesan texto + imágenes + (pronto) audio/video:

**Nuevas posibilidades:**
- Adjuntar diagrama y pedir análisis
- Describir screenshot de error
- Combinar código + gráfico + descripción

**Principio:** Usa el medio más eficiente para cada tipo de información.

---

## Anti-patrones comunes

### ❌ Sobrecarga de instrucciones

```markdown
Actúa como experto, piensa paso a paso, sé creativo pero preciso,
usa tono formal pero amigable, incluye ejemplos pero sé breve,
considera múltiples perspectivas pero da una respuesta clara...
[100 líneas más]
```

**Problema:** Demasiadas instrucciones contradictorias confunden al modelo.

**Solución:** Prioriza 3-5 instrucciones clave.

---

### ❌ Asumir conocimiento implícito

```markdown
Haz lo que hicimos la última vez pero para el otro proyecto.
```

**Problema:** El modelo no tiene memoria entre sesiones (a menos que uses custom instructions/projects).

**Solución:** Explicita siempre el contexto necesario.

---

### ❌ Preguntar y restringir simultáneamente

```markdown
Sé creativo... pero solo usa estas 3 palabras exactas.
```

**Problema:** Instrucciones contradictorias.

**Solución:** Clarifica prioridades: ¿creatividad o restricciones?

---

### ❌ No iterar

```markdown
[Escribes prompt]
[Respuesta no es perfecta]
[Abandonas o empiezas desde cero]
```

**Problema:** Los prompts raramente funcionan perfectamente en el primer intento.

**Solución:** Refina iterativamente. Cada respuesta te enseña cómo mejorar el prompt.

---

## Principio meta

> **El mejor prompt es el que no necesitas escribir.**

Si encuentras que escribes el mismo tipo de prompt repetidamente:
- Crea un [patrón reutilizable](patrones/README.md)
- Usa [custom instructions](../prompts/customInstructions.md)
- Considera [Claude Projects](https://www.anthropic.com/news/projects) o [ChatGPT GPTs](https://openai.com/index/introducing-gpts/)
- Automatiza con [structured outputs](structuredOutputs.md) + código