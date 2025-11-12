<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Chain of Thought (Cadena de Pensamiento)

## ¿Por qué?

Los modelos de lenguaje son excelentes generando respuestas directas, pero pueden fallar en problemas que requieren razonamiento paso a paso. Cuando enfrentamos problemas complejos que involucran:
- Múltiples pasos lógicos
- Cálculos intermedios
- Razonamiento causal
- Análisis secuencial

...una respuesta directa puede contener errores porque el modelo "salta" directamente a la conclusión sin mostrar su trabajo.

**Chain of Thought (CoT) resuelve esto obligando al modelo a "mostrar su razonamiento"**, similar a como enseñamos a los estudiantes a mostrar su procedimiento en matemáticas.

> **Ejemplo visual**: Ver [demostración con manzanas 🍎](https://g.co/gemini/share/a94318ce50d0)

## ¿Qué?

Chain of Thought es una técnica de prompting que instruye al modelo a:
1. **Descomponer** problemas complejos en pasos intermedios
2. **Verbalizar** su razonamiento paso a paso
3. **Llegar** a una conclusión basada en esos pasos

A diferencia de una respuesta directa, CoT hace explícito el proceso de pensamiento, lo que permite:
- Detectar errores en el razonamiento
- Entender por qué se llegó a una conclusión
- Validar cada paso individualmente

### CoT vs Respuesta directa

**Sin CoT (respuesta directa):**
```
P: Si tengo 5 manzanas y compro 7 más, luego regalo 3, ¿cuántas tengo?
R: 9 manzanas.
```

**Con CoT:**
```
P: Si tengo 5 manzanas y compro 7 más, luego regalo 3, ¿cuántas tengo? Piensa paso a paso.
R: Veamos:
1. Empiezo con 5 manzanas
2. Compro 7 más: 5 + 7 = 12 manzanas
3. Regalo 3: 12 - 3 = 9 manzanas
Por lo tanto, tengo 9 manzanas.
```

## ¿Para qué?

- **Mejorar precisión** en problemas de razonamiento matemático, lógico y simbólico
- **Aumentar transparencia** del proceso de toma de decisiones del modelo
- **Facilitar debugging** cuando las respuestas son incorrectas
- **Mantener contexto** a lo largo de conversaciones complejas
- **Enseñar** al modelo patrones de razonamiento mediante ejemplos

## ¿Cómo?

### Variante 1: Zero-Shot CoT (Sin ejemplos)

La forma más simple: añade "piensa paso a paso" o similar.

**Prompt:**
```markdown
Resuelve el siguiente problema pensando paso a paso:

Un tren sale de Madrid hacia Barcelona (600 km) a 120 km/h.
Al mismo tiempo, otro tren sale de Barcelona hacia Madrid a 80 km/h.
¿Cuándo se encuentran?
```

**Por qué funciona:** La frase "pensando paso a paso" activa el modo de razonamiento secuencial del modelo.

**Variantes de la frase mágica:**
- "Piensa paso a paso"
- "Razona paso por paso"
- "Explica tu razonamiento"
- "Muestra tu trabajo"
- "Desglosa el problema"

---

### Variante 2: Few-Shot CoT (Con ejemplos)

Proporciona ejemplos de cómo deseas que razonen:

**Prompt:**
```markdown
Resuelve los siguientes problemas mostrando tu razonamiento:

Ejemplo:
P: Juan tiene el doble de edad que María. En 5 años, la suma de sus edades será 35. ¿Cuántos años tiene Juan ahora?
R: Paso a paso:
1. Sea M la edad actual de María
2. Entonces Juan tiene 2M años
3. En 5 años: María = M+5, Juan = 2M+5
4. La suma será: (M+5) + (2M+5) = 35
5. Simplificando: 3M + 10 = 35
6. Resolviendo: 3M = 25, M = 8.33...
7. Juan tiene: 2 × 8.33 ≈ 16.67 años

Ahora resuelve:
P: [TU PROBLEMA AQUÍ]
```

---

### Variante 3: Structured CoT (Estructurado)

Define explícitamente los pasos esperados:

**Prompt:**
```markdown
Analiza el siguiente código y encuentra el bug.

Sigue estos pasos:
1. ¿Cuál es el comportamiento esperado?
2. ¿Qué está haciendo realmente el código?
3. ¿En qué línea está el problema?
4. ¿Por qué esa línea causa el problema?
5. ¿Cuál es la solución?

Código:
[CÓDIGO AQUÍ]
```

---

### Ejemplo práctico: Análisis de viabilidad de negocio

**Sin CoT:**
```markdown
¿Es viable abrir una cafetería en el centro de Salamanca?
```

**Con CoT:**
```markdown
Analiza la viabilidad de abrir una cafetería en el centro de Salamanca.

Razona paso a paso considerando:
1. Población y flujo de personas en el centro
2. Competencia existente (otras cafeterías)
3. Costos estimados (alquiler, personal, suministros)
4. Ingresos potenciales (ticket medio × clientes/día)
5. Break-even point (cuántos meses para recuperar inversión)
6. Riesgos y factores estacionales

Proporciona conclusión basada en este análisis.
```

---

### Ejemplo práctico: Debugging de código

**Sin CoT:**
```markdown
Este código no funciona. ¿Qué está mal?

def calcular_promedio(numeros):
    suma = 0
    for num in numeros:
        suma += num
    return suma / len(numeros)

resultado = calcular_promedio([])
```

**Con CoT:**
```markdown
Analiza este código paso a paso y encuentra el bug:

```python
def calcular_promedio(numeros):
    suma = 0
    for num in numeros:
        suma += num
    return suma / len(numeros)

resultado = calcular_promedio([])
```

Razonamiento esperado:
1. ¿Qué hace la función?
2. ¿Qué pasa cuando numeros = []?
3. ¿Qué valor tiene len([])  ?
4. ¿Qué pasa cuando divides entre ese valor?
5. ¿Cuál es el error y cómo solucionarlo?
```

---

### Comparación de técnicas

| Aspecto | Respuesta directa | Zero-Shot CoT | Few-Shot CoT | Tree of Thought |
|---------|------------------|---------------|--------------|-----------------|
| **Setup** | Ninguno | "Piensa paso a paso" | Ejemplos con pasos | Múltiples caminos |
| **Tokens** | Mínimo | Medio | Alto | Muy alto |
| **Precisión** | Baja en problemas complejos | Media-Alta | Alta | Muy alta |
| **Transparencia** | Nula | Alta | Muy alta | Muy alta |
| **Cuándo usar** | Preguntas simples | Problemas moderados | Problemas complejos | Problemas ambiguos |

---

### Cuándo usar Chain of Thought

✅ **Usar CoT cuando:**
- El problema require múltiples pasos de razonamiento
- Necesitas validar el proceso de pensamiento
- Los errores son costosos y deben evitarse
- Estás enseñando o explicando conceptos
- El dominio es matemático, lógico o técnico

❌ **NO usar CoT cuando:**
- La pregunta es factual simple ("¿Capital de Francia?")
- Necesitas respuestas muy rápidas
- El presupuesto de tokens es limitado
- La pregunta es abierta y creativa (usar [Tree of Thought](arbolPensamiento.md) en su lugar)

---

### Anti-patrones comunes

❌ **CoT vago:**
```markdown
Piensa en esto: ¿Qué hacemos con el proyecto?
```

❌ **Contraproducente:**
```markdown
Dame una respuesta rápida en una palabra, pero razona paso a paso.
```

❌ **Sobre-estructurado:**
```markdown
Para responder "¿Qué hora es?":
1. Analiza el contexto temporal
2. Evalúa la zona horaria
3. Considera el horario de verano
4. [15 pasos más innecesarios...]
```

---

### Casos de uso documentados

- **[Ejemplo paso a paso con Gemini](https://g.co/gemini/share/dfd8f14e1eb2)** - Demostración interactiva
- **[Caso: Artesanía](/documentos/casosDeUso/artesania.md)** - CoT aplicado a dominio específico

---

### Evolución: De CoT a técnicas avanzadas

Chain of Thought es la base de técnicas más avanzadas:

```
Chain of Thought (lineal)
    ↓
Tree of Thought (ramificado)
    ↓
Graph of Thought (en red)
    ↓
Self-Consistency (múltiples CoT, votación mayoritaria)
```

> **Siguiente paso:** [Árbol de Pensamiento](arbolPensamiento.md) para problemas con múltiples soluciones válidas

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Ingeniería de Prompts](README.md)<br>Base metodológica necesaria|Metodología > Ingeniería de Prompts > **Chain of Thought**|[Árbol de pensamiento](arbolPensamiento.md)<br>Evolución de CoT
|[Anatomía de prompts](../prompts/anatomia.md)<br>Comprende componentes básicos||[x-Shot Prompting](xShotPrompting.md)<br>Técnica complementaria

<i>**Relacionado**: [Ventana de contexo](../prompts/ventanaDeContexto.md) - Mantener contexto en conversaciones / [Casos prácticos: Artesanía](../casosDeUso/artesania.md) - Ver CoT en acción / [Priming](priming.md) - Otra forma de guiar respuestas</i>

</div>
