<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# ReAct: Reasoning + Acting

> **Técnica moderna (2022-2025)** para combinar razonamiento verbal con acciones concretas

## ¿Por qué?

Los modelos de lenguaje tradicionales pueden **razonar** (pensar) o **actuar** (usar herramientas, buscar información), pero históricamente hacían estas cosas por separado. Esto creaba problemas:

- **Solo razonamiento:** El modelo puede alucinar datos que no conoce
- **Solo acción:** El modelo ejecuta herramientas sin planificación estratégica
- **Desconectados:** Las acciones no informan el razonamiento y viceversa

**ReAct resuelve esto integrando razonamiento y acción en un ciclo iterativo**, donde cada uno informa al otro.

## ¿Qué?

ReAct (Reasoning + Acting) es un paradigma de prompting que alterna entre:

1. **Thought (Pensamiento):** El modelo razona sobre qué hacer
2. **Action (Acción):** El modelo ejecuta una acción concreta (búsqueda, cálculo, llamada a API)
3. **Observation (Observación):** El modelo recibe el resultado de la acción
4. **[Repetir]** hasta completar la tarea

### Estructura del ciclo ReAct

```
Thought: [Razonamiento sobre el problema y próximos pasos]
Action: [Comando específico a ejecutar]
Observation: [Resultado de la acción]
Thought: [Análisis del resultado y decisión]
Action: [Siguiente acción basada en el análisis]
Observation: [Resultado]
...
Thought: [Conclusión final]
Answer: [Respuesta al usuario]
```

## ¿Para qué?

- **Agentes de IA:** Sistemas que necesitan planificar y ejecutar tareas complejas
- **Búsqueda de información:** Cuando el modelo necesita datos actuales que no tiene
- **Cálculos precisos:** Delegar matemáticas a calculadoras en lugar de alucinar
- **Interacción con APIs:** Consultar bases de datos, servicios web, etc.
- **Debugging y verificación:** Validar información antes de usarla en razonamiento

## ¿Cómo?

### Ejemplo 1: Búsqueda de información actual

**Pregunta:** "¿Quién ganó el Oscar a Mejor Película en 2024?"

**Prompt ReAct:**
```markdown
Usa el siguiente formato:

Thought: [Tu razonamiento sobre qué necesitas hacer]
Action: [La acción a ejecutar: Search[query] o Finish[respuesta]]
Observation: [Resultado de la acción]

Pregunta: ¿Quién ganó el Oscar a Mejor Película en 2024?

Thought: Necesito buscar información actualizada sobre los Oscars 2024, ya que mi conocimiento tiene fecha de corte.
Action: Search[Oscar Mejor Película 2024 ganador]
Observation: "Oppenheimer" dirigida por Christopher Nolan ganó el Oscar a Mejor Película en 2024.
Thought: Tengo la información que necesito. Puedo proporcionar la respuesta.
Action: Finish[La película "Oppenheimer", dirigida por Christopher Nolan, ganó el Oscar a Mejor Película en 2024.]
```

---

### Ejemplo 2: Resolución de problema con cálculos

**Pregunta:** "Si invierto €10,000 al 7% anual compuesto, ¿cuánto tendré en 5 años?"

**Prompt ReAct:**
```markdown
Thought: Necesito calcular interés compuesto. Usaré la fórmula A = P(1 + r)^t. Necesito una calculadora para precisión.
Action: Calculate[10000 * (1 + 0.07)^5]
Observation: 14025.52

Thought: El resultado es €14,025.52. Debo verificar que tiene sentido: 7% en 5 años debería dar aproximadamente 40% total, y 14k es razonable para 10k inicial.
Action: Calculate[14025.52 - 10000]
Observation: 4025.52

Thought: Gané €4,025.52 en intereses, que es aproximadamente 40% de 10,000. Esto confirma el cálculo.
Action: Finish[En 5 años tendrás €14,025.52 (ganancia de €4,025.52 en intereses)]
```

---

### Ejemplo 3: Investigación multi-paso

**Pregunta:** "¿Cuál es la población actual de la capital de Japón y cómo se compara con la de Francia?"

**Prompt ReAct:**
```markdown
Thought: Primero necesito confirmar cuál es la capital de Japón (aunque sé que es Tokio).
Action: Search[Capital de Japón]
Observation: Tokio es la capital de Japón.

Thought: Ahora necesito la población actual de Tokio.
Action: Search[Población de Tokio 2024]
Observation: El área metropolitana de Tokio tiene aproximadamente 37-38 millones de habitantes.

Thought: Ahora necesito la población de Francia para comparar.
Action: Search[Población de Francia 2024]
Observation: Francia tiene aproximadamente 68 millones de habitantes.

Thought: Tengo ambos datos. Tokio área metropolitana (37-38M) vs Francia país completo (68M). Debo aclarar que Tokio es solo una ciudad metropolitana.
Action: Finish[La capital de Japón es Tokio. El área metropolitana de Tokio tiene aproximadamente 37-38 millones de habitantes. Francia como país completo tiene unos 68 millones de habitantes. Nota: Es importante destacar que Tokio es una ciudad metropolitana mientras que Francia es un país entero, por lo que la comparación directa es entre una región urbana vs una nación completa.]
```

---

### Variantes de ReAct

#### 1. ReAct simplificado (sin formato estricto)

Para uso casual, puedes simplificar:

```markdown
Resuelve esto paso a paso, indicando cuándo necesitas buscar información o hacer cálculos:

[TU PREGUNTA]
```

#### 2. ReAct con herramientas específicas

Define las herramientas disponibles:

```markdown
Tienes acceso a estas herramientas:
- Search[query]: Buscar en internet
- Calculate[expresión]: Calculadora
- WikipediaLookup[término]: Buscar en Wikipedia
- CurrentDate[]: Obtener fecha actual

Usa formato Thought/Action/Observation para resolver:
[TU PREGUNTA]
```

#### 3. ReAct con verificación

Añade paso de verificación:

```markdown
Thought: [Razonamiento]
Action: [Acción]
Observation: [Resultado]
Verification: [¿Es este resultado confiable? ¿Necesito más información?]
Thought: [Siguiente paso]
...
```

---

### Comparación con otras técnicas

| Técnica | Puede razonar | Puede actuar | Verifica resultados | Mejor para |
|---------|--------------|--------------|---------------------|------------|
| **Chain of Thought** | ✅ | ❌ | Limitado | Razonamiento puro |
| **Tool Use básico** | ❌ | ✅ | ❌ | Ejecución simple |
| **ReAct** | ✅ | ✅ | ✅ | Agentes, tareas complejas |
| **Tree of Thought** | ✅ | ❌ | ✅ | Exploración de alternativas |

---

### Implementación práctica en sistemas reales

**En ChatGPT/Claude con plugins:**
```markdown
Usando tus herramientas disponibles, investiga paso a paso:

1. Busca los 5 restaurantes mejor valorados en Barcelona
2. Para cada uno, busca su especialidad
3. Compara precios medios
4. Recomienda el mejor para una cena romántica presupuesto medio

Muestra tu razonamiento en cada paso.
```

**En desarrollo con APIs:**
```python
# Pseudo-código de implementación ReAct
def react_loop(question, max_iterations=5):
    context = question
    for i in range(max_iterations):
        # Thought
        thought = llm.generate(f"Thought sobre: {context}")

        # Action
        action = llm.generate(f"Acción a ejecutar: {thought}")

        if "Finish" in action:
            return extract_answer(action)

        # Execute action
        observation = execute_tool(action)

        # Update context
        context += f"\nObservation: {observation}"

    return llm.generate(f"Respuesta final basada en: {context}")
```

---

### Casos de uso ideales

✅ **Usar ReAct cuando:**
- Necesitas información que el modelo no tiene (datos actuales, específicos)
- La tarea requiere herramientas externas (calculadora, base de datos, APIs)
- Quieres transparencia en cómo el agente toma decisiones
- La precisión es crítica (verificar antes de responder)
- Desarrollas agentes autónomos

❌ **NO usar ReAct cuando:**
- La pregunta es puramente conceptual o teórica
- No hay herramientas disponibles
- La latencia es crítica (ReAct es más lento)
- [Chain of Thought](chainOfThought.md) es suficiente

---

### Anti-patrones comunes

❌ **Acción sin razonamiento:**
```markdown
Action: Search[cosa aleatoria]
Action: Search[otra cosa]
Action: Search[más cosas]
```

❌ **Razonamiento sin acción cuando es necesaria:**
```markdown
Thought: Necesito el dato X pero voy a asumir que es Y
Thought: Basándome en mi asunción...
[Sin nunca buscar el dato real]
```

❌ **Loop infinito:**
```markdown
Thought: Necesito más información
Action: Search[X]
Observation: [Resultado]
Thought: Necesito más información
Action: Search[X]  # ¡Misma búsqueda!
[Sin criterio de parada]
```

---

### Recursos y referencias

- **Paper original:** [ReAct: Synergizing Reasoning and Acting in Language Models (Yao et al., 2022)](https://arxiv.org/abs/2210.03629)
- **Implementaciones:**
  - LangChain ReAct Agent
  - AutoGPT (usa ReAct internamente)
  - AgentGPT
  - Claude con tool use
  - ChatGPT con plugins/Actions

---

### Evolución: De CoT a ReAct a Agentes

```
Chain of Thought (pensar)
    ↓
ReAct (pensar + actuar)
    ↓
Multi-Agent Systems (múltiples ReAct cooperando)
    ↓
Autonomous Agents (ReAct + memoria + planificación)
```

> **Relacionado:** [Chain of Thought](chainOfThought.md) - Base de razonamiento | [Casos de uso](../casosDeUso/README.md) - Aplicaciones prácticas

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Chain of Thought](chainOfThought.md)<br>Razonamiento base necesario|Metodología > Ingeniería de Prompts > **ReAct**|[Árbol de pensamiento](arbolPensamiento.md)<br>Razonamiento multi-ruta
|[Ingeniería de Prompts](README.md)<br>Marco metodológico||[0-Shot Prompting](0ShotPrompting.md)<br>Técnicas complementarias

<i>**Relacionado**: [Tool use / Function calling](#) - Implementación técnica de acciones / [Agentes de IA](#) - Sistemas que usan ReAct / [RAG patterns](#) - Otra forma de acceder información externa</i>

</div>
