<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Self-Consistency (Auto-Consistencia)

> **Técnica avanzada (2022-2025)** para mejorar precisión mediante votación mayoritaria

## ¿Por qué?

Un solo razonamiento Chain of Thought puede contener errores: el modelo puede tomar un camino incorrecto en algún paso intermedio y llegar a una conclusión errónea. Incluso si el modelo "muestra su trabajo", ese trabajo puede estar equivocado.

**Self-Consistency resuelve esto generando múltiples razonamientos independientes y eligiendo la respuesta más común** (votación mayoritaria). La intuición es simple: si el modelo razona correctamente, debería llegar a la misma respuesta por diferentes caminos. Las respuestas incorrectas tenderán a ser inconsistentes.

## ¿Qué?

Self-Consistency es una técnica que consiste en:

1. **Generar** múltiples razonamientos CoT independientes para el mismo problema
2. **Extraer** la respuesta final de cada razonamiento
3. **Votar** por la respuesta más frecuente (mayoría)
4. **Seleccionar** esa respuesta como la final

### Proceso visual

```
Pregunta → [CoT #1] → Respuesta A
       → [CoT #2] → Respuesta A  ← ✅ Mayoría
       → [CoT #3] → Respuesta B
       → [CoT #4] → Respuesta A
       → [CoT #5] → Respuesta C

Votación: A (3), B (1), C (1)
Respuesta final: A
```

## ¿Para qué?

- **Mejorar precisión** en problemas de razonamiento matemático, lógico y analítico
- **Reducir alucinaciones** al filtrar respuestas inconsistentes
- **Aumentar confianza** cuando múltiples caminos llegan a la misma conclusión
- **Detectar ambigüedad** cuando las respuestas están muy distribuidas
- **Sistemas críticos** donde la precisión es más importante que la velocidad

### Mejora demostrada

Estudios muestran que Self-Consistency mejora significativamente la precisión sobre CoT simple:

| Dataset | CoT simple | Self-Consistency | Mejora |
|---------|-----------|-----------------|--------|
| GSM8K (matemáticas) | 46.4% | 74.4% | **+28%** |
| SVAMP (word problems) | 68.6% | 83.7% | **+15%** |
| AQuA (álgebra) | 35.2% | 52.4% | **+17%** |

## ¿Cómo?

### Método básico (manual)

**Paso 1: Genera múltiples razonamientos**

```markdown
Resuelve este problema paso a paso. Genera 5 soluciones diferentes explorando distintos enfoques:

Problema: María tiene 3 veces la edad de Juan. En 10 años, María tendrá el doble de la edad de Juan. ¿Cuántos años tiene cada uno ahora?
```

**Paso 2: Compara respuestas**

```
Solución 1 → Juan: 10 años, María: 30 años
Solución 2 → Juan: 10 años, María: 30 años
Solución 3 → Juan: 15 años, María: 45 años [ERROR]
Solución 4 → Juan: 10 años, María: 30 años
Solución 5 → Juan: 10 años, María: 30 años

Mayoría: Juan 10, María 30 ✓
```

---

### Método con prompting estructurado

**Prompt único que genera múltiples paths:**

```markdown
Resuelve el siguiente problema generando 3 razonamientos independientes.
Para cada razonamiento, usa un enfoque diferente si es posible.
Al final, identifica la respuesta más común.

Problema: [TU PROBLEMA]

Razonamiento 1:
[Paso a paso...]
Respuesta 1: [X]

Razonamiento 2:
[Paso a paso con enfoque diferente...]
Respuesta 2: [Y]

Razonamiento 3:
[Paso a paso con tercer enfoque...]
Respuesta 3: [Z]

Votación:
- Respuesta [X]: aparece [N] veces
- Respuesta [Y]: aparece [M] veces

Conclusión: La respuesta más consistente es [la más frecuente]
```

---

### Ejemplo práctico completo

**Problema:** Un caracol sube por un poste de 10 metros. Durante el día sube 3 metros, pero durante la noche resbala y baja 2 metros. ¿Cuántos días tarda en llegar a la cima?

**Prompt Self-Consistency:**

```markdown
Genera 3 razonamientos independientes para este problema:

"Un caracol sube por un poste de 10 metros. Durante el día sube 3 metros,
pero durante la noche resbala y baja 2 metros. ¿Cuántos días tarda en llegar a la cima?"

Razonamiento 1 (día a día):
Día 1: Sube a 3m, baja a 1m (neto: 1m)
Día 2: Desde 1m sube a 4m, baja a 2m (neto: 2m)
Día 3: Desde 2m sube a 5m, baja a 3m (neto: 3m)
...
Día 8: Desde 7m sube a 10m ¡LLEGÓ! (ya no baja)
Respuesta 1: 8 días

Razonamiento 2 (progreso neto):
Progreso neto diario = 3 - 2 = 1 metro
Pero el último día no resbala si llega arriba
Necesita llegar a 7m para que al día siguiente llegue a 10m
7m ÷ 1m/día = 7 días
Día 8: Desde 7m + 3m = 10m
Respuesta 2: 8 días

Razonamiento 3 (ecuación):
Sea d = número de días
Altura final: d × 3 - (d-1) × 2 ≥ 10
(el último día no resbala)
3d - 2d + 2 ≥ 10
d + 2 ≥ 10
d ≥ 8
Respuesta 3: 8 días

Votación: Todos coinciden en 8 días
Confianza: ALTA ✓
```

---

### Variantes de Self-Consistency

#### 1. Weighted Self-Consistency (Ponderado)

No todos los razonamientos tienen igual peso. Puedes ponderar según:
- Longitud del razonamiento (más detallado = más peso)
- Confianza explícita del modelo
- Complejidad del camino tomado

#### 2. Self-Consistency con temperatura variable

Genera razonamientos con diferentes temperaturas:
- Temperature 0.7: 3 razonamientos
- Temperature 0.3: 2 razonamientos conservadores
- Votación ponderada

#### 3. Self-Consistency con verificación

Añade un paso de verificación para cada respuesta candidata:

```markdown
Candidato A (3 votos): [Respuesta]
Verificación: Sustituir en problema original y comprobar que funciona
¿Es válido? SÍ/NO

Candidato B (2 votos): [Respuesta]
Verificación: ...
```

---

### Comparación con otras técnicas

| Técnica | Generaciones | Votación | Precisión | Costo (tokens) | Latencia |
|---------|-------------|----------|-----------|----------------|----------|
| **CoT simple** | 1 | No | Base | 1x | 1x |
| **Self-Consistency 3x** | 3 | Sí | +15-20% | 3x | 3x |
| **Self-Consistency 5x** | 5 | Sí | +20-28% | 5x | 5x |
| **Tree of Thought** | Múltiple | Evaluación | Alta | 5-10x | 5-10x |

---

### Implementación práctica

**Con API (pseudo-código):**

```python
def self_consistency(prompt, n_samples=5):
    """
    Genera n_samples razonamientos independientes y vota por mayoría
    """
    responses = []

    for i in range(n_samples):
        # Generar con temperatura > 0 para diversidad
        response = llm.generate(
            prompt + "\nPiensa paso a paso:",
            temperature=0.7  # Importante: no usar 0
        )
        answer = extract_final_answer(response)
        responses.append(answer)

    # Votación mayoritaria
    from collections import Counter
    vote_counts = Counter(responses)
    most_common = vote_counts.most_common(1)[0]

    return {
        'answer': most_common[0],
        'confidence': most_common[1] / n_samples,
        'all_responses': responses
    }
```

**Con ChatGPT/Claude (manual):**

```markdown
Por favor genera 5 razonamientos diferentes para este problema.
Usa enfoques variados si es posible.
Al final, indica cuál es la respuesta más común.

[Tu problema aquí]
```

---

### Cuándo usar Self-Consistency

✅ **Usar Self-Consistency cuando:**
- La precisión es crítica (medicina, finanzas, legal)
- El problema es complejo con múltiples pasos
- Puedes permitirte el costo adicional
- Quieres medir la confianza (consistencia = confianza)
- Estás evaluando/benchmarking modelos

❌ **NO usar Self-Consistency cuando:**
- Necesitas respuestas en tiempo real
- El presupuesto de tokens es limitado
- El problema es muy simple (overkill)
- [Chain of Thought simple](chainOfThought.md) es suficiente
- Necesitas creatividad (votación elimina respuestas únicas)

---

### Medición de confianza

La distribución de votos indica confianza:

```
Alta confianza:     [A:9, B:1]      → 90% de acuerdo
Media confianza:    [A:5, B:3, C:2] → 50% de acuerdo
Baja confianza:     [A:2, B:2, C:2, D:2, E:2] → 20% de acuerdo
```

**Si la confianza es baja (<50%), considera:**
- El problema puede estar mal definido
- Necesitas más contexto
- Hay múltiples respuestas válidas
- El modelo no es adecuado para este problema

---

### Anti-patrones

❌ **Temperatura 0 en todas las generaciones:**
```python
# MALO: Todos los razonamientos serán idénticos
for i in range(5):
    generate(prompt, temperature=0)  # ¡Siempre da lo mismo!
```

❌ **Ignorar distribución de votos:**
```
Votos: [A:3, B:2]
"A gana" ← Técnicamente sí, pero poca confianza (60%)
```

❌ **Usar para preguntas factuales simples:**
```
"¿Capital de Francia?" → 5 generaciones → "París" (5 votos)
[Desperdicio de tokens]
```

---

### Combinación con otras técnicas

**Self-Consistency + ReAct:**
```
Genera 3 razonamientos ReAct independientes
→ Compara las respuestas finales
→ Si hay discrepancia, ejecuta verificación adicional
```

**Self-Consistency + Tree of Thought:**
```
Genera múltiples árboles de pensamiento
→ Vota por los caminos más frecuentes
→ Mayor robustez
```

---

### Recursos y referencias

- **Paper original:** [Self-Consistency Improves Chain of Thought Reasoning (Wang et al., 2022)](https://arxiv.org/abs/2203.11171)
- **Benchmarks:** GSM8K, SVAMP, AQuA, CommonsenseQA
- **Implementaciones:**
  - LangChain (built-in)
  - OpenAI Cookbook examples
  - Anthropic Claude examples

---

### Evolución de técnicas de razonamiento

```
Chain of Thought (2022)
    ↓
Self-Consistency (2022) ← Estamos aquí
    ↓
Least-to-Most Prompting (2022)
    ↓
Faithful CoT (2023)
    ↓
Complexity-based Consistency (2024)
```

> **Relacionado:** [Chain of Thought](chainOfThought.md) - Técnica base | [Tree of Thought](arbolPensamiento.md) - Exploración de caminos

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Chain of Thought](chainOfThought.md)<br>Técnica base necesaria|Metodología > Ingeniería de Prompts > **Self-Consistency**|[Tree of Thought](arbolPensamiento.md)<br>Exploración estructurada
|[Ingeniería de Prompts](README.md)<br>Marco metodológico||[ReAct](ReAct.md)<br>Razonamiento + acción

<i>**Relacionado**: [Árbol de pensamiento](arbolPensamiento.md) - Otra forma de explorar múltiples caminos / [Casos de uso](../casosDeUso/README.md) - Aplicaciones prácticas</i>

</div>
