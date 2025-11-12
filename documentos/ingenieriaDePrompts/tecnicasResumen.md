<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Técnicas de Ingenieria de Prompts

## ¿Por qué?

Surgen con el objetivo de controlar y mejorar la generación de texto, de modo que seamos capaces de abordar desafíos específicos en la interacción con modelos de lenguaje y responder a las necesidades de los usuarios.

## ¿Qué?

### Técnicas fundamentales

- **Priming**: Establecer contexto inicial para orientar las respuestas del modelo
- **X-shot Prompting**: Proporcionar ejemplos específicos (0, 1, pocos, muchos) para guiar el comportamiento
- **Chain of Thought**: Razonamiento paso a paso para problemas complejos

### Técnicas avanzadas de razonamiento

- **Tree of Thought**: Exploración de múltiples caminos de razonamiento simultáneamente
- **Self-Consistency**: Mejora de precisión mediante votación mayoritaria de múltiples razonamientos
- **ReAct**: Combinación de razonamiento verbal con acciones concretas (Reasoning + Acting)

### Técnicas de integración

- **RAG**: Recuperación y aumento de información externa (Retrieval-Augmented Generation)
- **Structured Outputs**: Salidas estructuradas en JSON, XML y formatos parseables

## ¿Para qué?

### Técnicas fundamentales

- **[Priming](priming.md)**
  - Establecer contexto inicial (rol, estilo, formato, restricciones)
  - Influir en el tono y tema desde el primer mensaje
  - Orientar la generación hacia expectativas específicas

- **[X-shot Prompting](xShotPrompting.md)**
  - Controlar y orientar respuestas mediante ejemplos
  - Enseñar patrones sin modificar el modelo
  - Adaptar comportamiento a dominios específicos

- **[Chain of Thought](chainOfThought.md)**
  - Descomponer problemas complejos en pasos intermedios
  - Hacer explícito el proceso de razonamiento
  - Mejorar precisión en problemas matemáticos y lógicos

### Técnicas avanzadas de razonamiento

- **[Tree of Thought](arbolPensamiento.md)**
  - Explorar múltiples soluciones en paralelo
  - Evaluar alternativas antes de elegir camino
  - Resolver problemas con múltiples soluciones válidas

- **[Self-Consistency](selfConsistency.md)**
  - Mejorar precisión mediante votación mayoritaria
  - Reducir alucinaciones filtrando respuestas inconsistentes
  - Aumentar confianza en sistemas críticos

- **[ReAct](ReAct.md)**
  - Integrar razonamiento verbal con acciones concretas
  - Acceder a información actualizada mediante herramientas
  - Desarrollar agentes autónomos que planifican y ejecutan

### Técnicas de integración

- **[RAG](RAG.md)**
  - Acceder a conocimiento propio y actualizado
  - Reducir alucinaciones con fuentes verificables
  - Escalar conocimiento sin reentrenar modelos

- **[Structured Outputs](structuredOutputs.md)**
  - Integrar LLMs con sistemas de software
  - Garantizar formatos parseables (JSON, XML)
  - Validar esquemas y tipos de datos

## ¿Cómo?

### Comparación de técnicas

| Técnica | Complejidad | Setup | Cuándo usar | Costo (tokens) |
|---------|------------|-------|-------------|----------------|
| **Priming** | Baja | Contexto inicial | Siempre, como base | Bajo |
| **0-Shot** | Baja | Instrucción directa | Tareas generales | Muy bajo |
| **X-Shot** | Media | Ejemplos previos | Enseñar patrones | Medio |
| **Chain of Thought** | Media | "Piensa paso a paso" | Razonamiento complejo | Medio-Alto |
| **Tree of Thought** | Alta | Múltiples caminos | Problemas abiertos | Alto |
| **Self-Consistency** | Alta | Múltiples generaciones | Precisión crítica | Muy alto |
| **ReAct** | Alta | Tools + razonamiento | Agentes, info externa | Alto |
| **RAG** | Alta | Vector DB + retrieval | Conocimiento propio | Alto |
| **Structured Outputs** | Media | Schema/JSON mode | Integración software | Medio |

### Combinaciones efectivas

Las técnicas no son excluyentes, se pueden combinar:

- **Priming + X-Shot**: Contexto inicial + ejemplos específicos
- **Chain of Thought + Self-Consistency**: Razonamiento múltiple + votación
- **ReAct + RAG**: Agente que busca en base de conocimiento
- **RAG + Structured Outputs**: Información externa en formato parseable
- **Tree of Thought + Self-Consistency**: Exploración exhaustiva + validación

### Progresión de aprendizaje recomendada

```
1. Fundamentos
   └─ Priming, 0-Shot, X-Shot

2. Razonamiento
   └─ Chain of Thought, Tree of Thought

3. Precisión y validación
   └─ Self-Consistency

4. Integración externa
   └─ ReAct, RAG, Structured Outputs
```