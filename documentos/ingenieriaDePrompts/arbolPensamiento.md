<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Árbol de pensamiento (Tree of Thought)

## ¿Por qué?

Los modelos de lenguaje, por defecto, generan respuestas de forma lineal y directa. Sin embargo, muchos problemas complejos requieren explorar múltiples caminos de razonamiento antes de llegar a una conclusión. Tree of Thought (ToT) permite que el modelo explore sistemáticamente diferentes ramas de pensamiento, evalúe su validez, y elija el camino más prometedor.

## ¿Qué?

Tree of Thought es una técnica avanzada de prompting que estructura el razonamiento del modelo como un árbol de decisiones, donde:
- Cada **nodo** representa un paso de pensamiento parcial
- Cada **rama** representa una línea de razonamiento alternativa
- El modelo puede **explorar, evaluar y retroceder** (backtrack) entre diferentes caminos

A diferencia de [Chain of Thought](chainOfThought.md) que sigue un único camino lineal, ToT explora múltiples caminos simultáneamente.

## ¿Para qué?

- **Problemas complejos** que requieren considerar múltiples enfoques
- **Razonamiento multi-paso** donde decisiones tempranas afectan resultados finales
- **Exploración de alternativas** para encontrar soluciones óptimas
- **Auto-corrección** cuando un camino de razonamiento resulta infructuoso

## ¿Cómo?

### Ejemplo fundamental: El problema de Bob

Este problema clásico demuestra la diferencia entre razonamiento lineal y Tree of Thought:

```
Bob está en la sala de estar.
Camina hacia la cocina, llevando una taza.
Él pone una pelota en la taza y lleva la taza al dormitorio.
Voltea la taza boca abajo y luego camina hacia el jardín.
Pone la taza en el jardín y luego camina hacia el garaje.
¿Dónde está la pelota?
```

#### Resultados sin Tree of Thought (pregunta directa):

|ChatGPT 3.5|ChatGPT 4|Claude|Gemini|Perplexity|Neuroflash|Huggingface (Mistral)|Copilot|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:
|[📋](https://chat.openai.com/share/dab16269-912b-4987-be3f-0215ba6e992c)|[📋](https://chat.openai.com/share/e21450b5-9d55-441e-9cb3-673afc365f80)|[📋](https://claude.ai/chat/3a1554f1-af18-4894-ac03-05e5955e8100)|[📋](https://g.co/gemini/share/2789c30f1dd2)|[📋](https://www.perplexity.ai/search/Bob-est-en-QMP1HrIjQ5mIGUFhp37eZA#0)|[📋](https://app.neuro-flash.com/ai-writer/e833d1d68a55890ea3072b671ae03c4d/preview)|[📋](https://huggingface.co/chat/conversation/661714c2a490f2673196c15f)|[📋](https://copilot.microsoft.com/sl/jYKwIpvUzT2)|
|<sub>Cocina</sub>|<sub>Jardín</sub>|<sub>Dormitorio</sub>|<sub>Jardín</sub>|<sub>En la taza no está</sub>|<sub>Dormitorio++</sub>|<sub>Dormitorio</sub>|<sub>Taza@Jardin</sub>

**Respuesta correcta:** Dormitorio (la pelota quedó allí cuando Bob volteó la taza)

**Observación:** Solo algunos modelos aciertan sin ayuda. La mayoría cometen errores de razonamiento espacial.

---

#### Resultados CON Tree of Thought (prompt de "tres expertos"):

**Prompt utilizado:**
```markdown
Imagina que tres expertos diferentes están respondiendo a esta pregunta.
Todos los expertos escribirán un paso de su pensamiento, luego lo compartirán con el grupo.
Luego, todos los expertos pasarán al siguiente paso, etc.
Si algún experto se da cuenta de que está equivocado en algún momento, entonces se retirará.
La pregunta es...

[AQUÍ VA EL PROBLEMA DE BOB]
```

|ChatGPT 3.5|ChatGPT 4|Claude|Gemini|Perplexity|Neuroflash|Huggingface (Mistral)|Copilot|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:
|[📋](https://chat.openai.com/share/dab16269-912b-4987-be3f-0215ba6e992c)|[📋](https://chat.openai.com/share/e21450b5-9d55-441e-9cb3-673afc365f80)|[📋](https://claude.ai/chat/3a1554f1-af18-4894-ac03-05e5955e8100)|[📋](https://g.co/gemini/share/2789c30f1dd2)|[📋](https://www.perplexity.ai/search/Bob-est-en-QMP1HrIjQ5mIGUFhp37eZA#0)|[📋](https://app.neuro-flash.com/ai-writer/e833d1d68a55890ea3072b671ae03c4d/preview)|[📋](https://huggingface.co/chat/conversation/661714c2a490f2673196c15f)|[📋](https://copilot.microsoft.com/sl/jYKwIpvUzT2)|
|<sub>Cocina</sub>|<sub>Jardín</sub>|<sub>Dormitorio</sub>|<sub>Jardín</sub>|<sub>En la taza no está</sub>|<sub>Dormitorio++</sub>|<sub>Dormitorio</sub>|<sub>Taza@Jardin</sub>|
|[📋](https://chat.openai.com/share/a5f146b5-15d0-4d58-b62d-abfcb3318cce)|[📋](https://chat.openai.com/share/44001e8f-26bd-4e92-aabc-3647c8593e39)|[📋](https://claude.ai/chat/14291ee0-d58b-467e-870e-c268f44e75a3)|[📋](https://g.co/gemini/share/7f62c7ccdd89)|[📋](https://www.perplexity.ai/search/Imagina-a-tres-kEBpJLOmQiaHEOxpba5YBw)|[📋](https://app.neuro-flash.com/ai-writer/c065303f45dab80e1a9932598c86ed35/preview)|[📋](https://huggingface.co/chat/conversation/661719fff88d12d297535fce)|[📋](https://copilot.microsoft.com/sl/JIJ3rdtavY)|
|<sub>Dormitorio</sub>|<sub>Dormitorio</sub>|<sub>Jardín</sub>|<sub>Faltan datos</sub>|<sub>"Meme"</sub>|<sub>Dormitorio</sub>|<sub>En la taza</sub>|<sub>3 posibles sitios</sub>|

**Observación:** ¡Mejora significativa! Más modelos llegan a la respuesta correcta (Dormitorio) al usar la técnica de "tres expertos". El razonamiento colaborativo ayuda a evitar errores lógicos.

---

### Variantes de prompts Tree of Thought

#### 1. Variante "Tres expertos" (ya demostrada)

**Cuándo usar:** Problemas de razonamiento espacial, lógico o que requieren múltiples perspectivas.

#### 2. Variante "Exploración y evaluación"

```markdown
Para resolver este problema, vamos a:
1. Generar 3 posibles enfoques diferentes
2. Evaluar las fortalezas y debilidades de cada enfoque
3. Elegir el enfoque más prometedor
4. Desarrollarlo paso a paso
5. Verificar si la solución es válida

Problema: [TU PROBLEMA AQUÍ]

Comienza generando los 3 enfoques posibles:
```

**Cuándo usar:** Problemas abiertos con múltiples soluciones válidas (diseño, estrategia, creatividad).

#### 3. Variante "Árbol de decisión explícito"

```markdown
Vamos a resolver esto construyendo un árbol de decisión:

Nivel 1 - Decisión inicial:
- Opción A: [descripción]
- Opción B: [descripción]
- Opción C: [descripción]

Para cada opción, analiza:
1. Consecuencias inmediatas
2. Posibles problemas
3. Próximos pasos requeridos

Luego profundiza en la opción más prometedora con un segundo nivel de decisiones.

Problema: [TU PROBLEMA AQUÍ]
```

**Cuándo usar:** Planificación estratégica, análisis de escenarios, decisiones complejas.

#### 4. Variante "Backtracking explícito"

```markdown
Resuelve este problema paso a paso.
Después de cada paso, evalúa: "¿Este paso me acerca a la solución?"
Si la respuesta es NO, retrocede y prueba un camino alternativo.
Muestra explícitamente cuándo retrocedes y por qué.

Problema: [TU PROBLEMA AQUÍ]
```

**Cuándo usar:** Problemas de búsqueda, laberintos, debugging, resolución de puzzles.

### Ejemplo práctico: Planificación de proyecto

**Sin ToT (pregunta directa):**
```markdown
¿Cómo debería organizar un proyecto de migración a microservicios para una aplicación monolítica?
```

**Con ToT (exploración de alternativas):**
```markdown
Vamos a planificar la migración a microservicios explorando 3 estrategias diferentes:

1. Primero genera 3 estrategias de migración distintas (ej: Strangler Fig, Big Bang, Modular)
2. Para cada estrategia, lista: ventajas, riesgos, requisitos, tiempo estimado
3. Evalúa cuál estrategia es más adecuada para una aplicación con:
   - 100K usuarios activos
   - Equipo de 8 developers
   - Deadline de 6 meses
   - Base de código legacy de 5 años
4. Para la estrategia elegida, desglosa en fases específicas

Comienza generando las 3 estrategias:
```

### Comparación: CoT vs ToT

| Aspecto | Chain of Thought | Tree of Thought |
|---------|-----------------|----------------|
| **Estructura** | Lineal (A→B→C→D) | Ramificada (A→B1/B2/B3→...) |
| **Exploración** | Un solo camino | Múltiples caminos simultáneos |
| **Auto-corrección** | Limitada | Explícita (backtracking) |
| **Complejidad** | Menor | Mayor |
| **Uso de tokens** | Moderado | Alto |
| **Cuándo usar** | Problemas con solución clara | Problemas complejos o ambiguos |
| **Ejemplo ideal** | Cálculos matemáticos | Planificación, diseño, estrategia |

### Limitaciones y consideraciones

- **Consumo de tokens:** ToT genera respuestas mucho más largas
- **No siempre necesario:** Para problemas simples, CoT es suficiente
- **Variabilidad:** Los resultados pueden variar según el modelo
- **Requiere validación:** El modelo puede explorar caminos inválidos

### Cuándo usar Tree of Thought

✅ **Usar ToT cuando:**
- El problema tiene múltiples soluciones válidas
- Se requiere considerar trade-offs
- La decisión temprana afecta opciones posteriores
- Necesitas justificación de por qué se eligió un camino

❌ **NO usar ToT cuando:**
- El problema tiene una única solución correcta clara
- El tiempo/tokens son limitados
- La respuesta es factual y directa
- [Chain of Thought](chainOfThought.md) es suficiente

---

## Enlaces y recursos

- [Paper original: Tree of Thoughts (Yao et al., 2023)](https://arxiv.org/abs/2305.10601)
- [Chain of Thought](chainOfThought.md) - Técnica relacionada más simple
- [Casos de uso](../casosDeUso/README.md) - Aplicaciones prácticas
