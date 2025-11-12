<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# RAG: Retrieval-Augmented Generation

> **Patrón fundamental (2020-2025)** para usar información propia con LLMs

## ¿Por qué?

Los modelos de lenguaje tienen limitaciones fundamentales:

- **Conocimiento con fecha de corte:** No saben nada después de su entrenamiento
- **Sin acceso a datos propios:** No conocen tu documentación interna, políticas, productos
- **Alucinaciones:** Pueden inventar información que suena correcta pero es falsa
- **No actualizables fácilmente:** Reentrenar es costoso y lento

**RAG resuelve esto separando "conocimiento" de "razonamiento"**: el modelo no necesita memorizar todo, solo necesita saber buscar y usar información relevante cuando la necesita.

## ¿Qué?

RAG (Retrieval-Augmented Generation) es un patrón que combina:

1. **Retrieval (Recuperación):** Buscar información relevante en una base de datos/documentos
2. **Augmentation (Aumento):** Inyectar esa información en el contexto del prompt
3. **Generation (Generación):** El LLM genera respuesta basándose en la información recuperada

### Flujo RAG básico

```
Usuario pregunta: "¿Cuál es nuestra política de vacaciones?"
          ↓
    [1. BÚSQUEDA]
Recuperar de base de datos: Documentos relevantes sobre política de vacaciones
          ↓
    [2. CONTEXTO]
Construir prompt: "Basándote en estos documentos: [docs], responde: ¿política vacaciones?"
          ↓
    [3. GENERACIÓN]
LLM genera respuesta fundamentada en los documentos recuperados
          ↓
Respuesta: "Según la política de la empresa, tienes 22 días..."
```

### RAG vs Alternativas

| Enfoque | Actualización | Costo | Transparencia | Limitación |
|---------|--------------|-------|---------------|------------|
| **Fine-tuning** | Reentrenar modelo | Alto | Baja | Lento de actualizar |
| **Context stuffing** | Inmediato | Bajo | Alta | Límite de tokens |
| **RAG** | Actualizar BD | Medio | Alta | Calidad de búsqueda |
| **Hybrid (Fine-tune + RAG)** | Ambos | Alto | Media-Alta | Complejo |

## ¿Para qué?

### Casos de uso ideales

- **Chatbots empresariales:** Responder preguntas sobre políticas internas, procedimientos
- **Asistentes de documentación:** Buscar en manuales técnicos, APIs, wikis
- **Soporte al cliente:** Acceder a base de conocimiento de productos
- **Análisis de documentos legales:** Buscar en contratos, regulaciones
- **Investigación académica:** Consultar papers, artículos científicos
- **E-commerce:** Información actualizada de productos, inventario

### Ventajas de RAG

✅ **Actualización inmediata:** Añade documentos nuevos sin reentrenar
✅ **Transparencia:** Puedes ver qué documentos usó para responder
✅ **Reduce alucinaciones:** Respuestas basadas en fuentes reales
✅ **Escalable:** Añade millones de documentos sin afectar el modelo
✅ **Costo-efectivo:** No requiere reentrenamiento constante

## ¿Cómo?

### Patrón básico: RAG manual (sin base de datos vectorial)

Para empezar a experimentar sin infraestructura compleja:

**Paso 1: Prepara tu información**
```markdown
DOCUMENTOS RELEVANTES:

Doc 1 - Política de Vacaciones:
Los empleados tienen derecho a 22 días laborables de vacaciones al año.
Las vacaciones deben solicitarse con 2 semanas de anticipación.

Doc 2 - Política de Días Personales:
Se otorgan 3 días personales al año adicionales a las vacaciones.
Pueden usarse sin justificación previa.
```

**Paso 2: Construye el prompt RAG**
```markdown
Basándote ÚNICAMENTE en la información proporcionada, responde la pregunta.
Si la información no está en los documentos, di "No encuentro esa información en la documentación".

INFORMACIÓN DISPONIBLE:
[Pega aquí los documentos relevantes]

PREGUNTA: ¿Cuántos días de vacaciones tengo?

INSTRUCCIONES:
- Cita el documento que usaste
- No inventes información
- Si hay ambigüedad, indícala
```

---

### Patrón intermedio: RAG con búsqueda simple

**Estructura del sistema:**

```python
# Pseudo-código conceptual
def simple_rag(question, documents):
    # 1. BÚSQUEDA: Filtrar documentos relevantes
    relevant_docs = search_documents(question, documents)
    # (búsqueda por palabras clave simple)

    # 2. CONTEXTO: Construir prompt
    context = "\n\n".join(relevant_docs)
    prompt = f"""
    Basándote en estos documentos:
    {context}

    Responde: {question}

    Si la respuesta no está en los documentos, di "No tengo esa información".
    """

    # 3. GENERACIÓN: LLM responde
    response = llm.generate(prompt)
    return response
```

---

### Patrón avanzado: RAG con embeddings (producción)

**Flujo completo:**

```
[INDEXACIÓN - Hacer una vez]
Documentos → Split en chunks → Generar embeddings → Guardar en vector DB

[CONSULTA - Cada pregunta]
Pregunta → Embedding → Búsqueda semántica → Top-K chunks → Prompt → LLM
```

**Prompt pattern para RAG avanzado:**

```markdown
Eres un asistente que responde basándose en documentación oficial.

CONTEXTO RECUPERADO:
---
Fragmento 1 (fuente: manual-empleados.pdf, pág 12):
[Texto relevante recuperado]

Fragmento 2 (fuente: politicas-2024.pdf, pág 5):
[Texto relevante recuperado]

Fragmento 3 (fuente: FAQ-interna.md):
[Texto relevante recuperado]
---

REGLAS IMPORTANTES:
1. Responde SOLO basándote en el contexto proporcionado
2. Si necesitas información que no está en el contexto, di explícitamente que no la tienes
3. Cita la fuente cuando respondas (ej: "Según el manual-empleados.pdf...")
4. Si hay información contradictoria entre fuentes, menciona ambas

PREGUNTA DEL USUARIO:
{pregunta}

RESPUESTA:
```

---

### Ejemplos prácticos

#### Ejemplo 1: Chatbot de soporte técnico

**Setup:**
```markdown
Base de conocimiento:
- 200 artículos de troubleshooting
- 50 guías de usuario
- 100 FAQs

Usuario: "Mi impresora no conecta por WiFi"

RAG recupera:
1. "Troubleshooting: Conexión WiFi impresoras HP"
2. "FAQ: Problemas comunes de red"
3. "Guía: Configurar WiFi en impresoras"

Prompt al LLM:
"Basándote en estos 3 documentos, ayuda al usuario con su problema..."
```

#### Ejemplo 2: Asistente de documentación de API

**Setup:**
```markdown
Base de conocimiento:
- Documentación de 500 endpoints
- Ejemplos de código
- Changelog

Desarrollador: "¿Cómo autenticar con OAuth2?"

RAG recupera:
1. Endpoint /auth/oauth2
2. Ejemplo: auth-flow.js
3. Security best practices

Prompt incluye ejemplos de código reales de la documentación
```

---

### Mejorando la calidad de RAG

#### 1. Chunking estratégico

**Malo:**
```
Chunk gigante de 5000 tokens → Pierde contexto local
```

**Bueno:**
```
Chunks de 200-500 tokens con overlap de 50 tokens
→ Mantiene contexto entre chunks
```

#### 2. Metadatos enriquecidos

```json
{
  "text": "Política de vacaciones...",
  "metadata": {
    "source": "manual-empleados.pdf",
    "page": 12,
    "last_updated": "2024-01-15",
    "department": "RRHH",
    "language": "es"
  }
}
```

**Uso en prompt:**
```markdown
Fragmento actualizado el 2024-01-15 (RECIENTE):
[texto]
```

#### 3. Re-ranking de resultados

```python
# Búsqueda recupera 20 documentos
results_20 = vector_search(query, top_k=20)

# Re-rank con modelo más sofisticado
results_5 = reranker(query, results_20, top_k=5)

# Usar solo top 5 en prompt
```

#### 4. Hybrid search (Keyword + Semantic)

```python
# Combinar búsqueda tradicional + vectorial
keyword_results = bm25_search(query)
semantic_results = vector_search(query)
final_results = merge_and_rank(keyword_results, semantic_results)
```

---

### Anti-patrones comunes

❌ **Recuperar demasiados documentos:**
```markdown
[50 documentos de contexto]
→ Excede ventana de contexto
→ LLM se confunde con información irrelevante
```

❌ **No validar calidad de recuperación:**
```python
results = vector_search(query, top_k=5)
# ¡Asumir que son relevantes sin verificar!
```

❌ **Prompts sin instrucciones claras:**
```markdown
[Documentos]
Pregunta: [X]
→ LLM puede ignorar documentos y alucinar
```

❌ **No manejar "no encontrado":**
```markdown
Si documentos vacíos → LLM inventa respuesta
MEJOR: Detectar y responder "No tengo información sobre eso"
```

---

### Arquitecturas RAG comunes

#### Naive RAG (Básico)
```
Query → Retrieve → Generate
```
**Pros:** Simple, rápido
**Contras:** Calidad variable

#### Advanced RAG (Avanzado)
```
Query → Expand query → Retrieve → Rerank → Generate
```
**Pros:** Mayor precisión
**Contras:** Más complejo

#### Agentic RAG (Con agente)
```
Query → Agent decide:
  → ¿Buscar más?
  → ¿Reformular query?
  → ¿Combinar múltiples búsquedas?
→ Generate con toda la información
```
**Pros:** Más robusto
**Contras:** Costoso, lento

---

### Stack tecnológico típico

**Vector Databases:**
- Pinecone (cloud, fácil)
- Weaviate (open-source)
- Qdrant (rápido)
- ChromaDB (desarrollo local)
- PGVector (PostgreSQL extension)

**Frameworks:**
- LangChain (Python/JS)
- LlamaIndex (Python, especializado en RAG)
- Haystack (Python)

**Embeddings:**
- OpenAI text-embedding-3-small/large
- Sentence Transformers (open-source)
- Cohere embed-v3

---

### Evaluación de sistemas RAG

**Métricas clave:**

| Métrica | Qué mide | Objetivo |
|---------|----------|----------|
| **Recall** | ¿Recuperamos documentos relevantes? | >90% |
| **Precision** | ¿Los recuperados son relevantes? | >80% |
| **MRR** | ¿Qué tan arriba está el doc relevante? | >0.8 |
| **Answer correctness** | ¿La respuesta final es correcta? | >85% |
| **Latency** | Tiempo de respuesta | <2s |

**Testing:**
```python
# Dataset de prueba
test_questions = [
    {"question": "...", "expected_answer": "...", "source": "doc-123"},
    ...
]

for test in test_questions:
    retrieved_docs = rag_retrieve(test.question)
    # ¿Está doc-123 en top-5?
    # ¿La respuesta generada coincide con expected_answer?
```

---

### Cuándo usar RAG

✅ **Usar RAG cuando:**
- Necesitas información actualizada constantemente
- Tienes documentación/datos propios
- La transparencia es importante (citar fuentes)
- Quieres reducir alucinaciones
- Tu dominio es específico (no en entrenamiento del modelo)

❌ **NO usar RAG cuando:**
- El conocimiento ya está en el modelo
- No tienes fuentes de datos estructuradas
- Latencia ultra-baja es crítica
- El problema es puramente generativo (creatividad)

---

### Recursos y próximos pasos

**Papers fundamentales:**
- [RAG: Retrieval-Augmented Generation (Lewis et al., 2020)](https://arxiv.org/abs/2005.11401)
- [Improving RAG (2023-2024 research)](https://arxiv.org/search/?query=retrieval+augmented+generation&searchtype=all)

**Tutoriales prácticos:**
- LangChain RAG Tutorial
- LlamaIndex documentation
- OpenAI RAG guide

**Siguiente nivel:**
- Graph RAG (usando knowledge graphs)
- Multi-modal RAG (texto + imágenes)
- Adaptive RAG (selección dinámica de estrategia)

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Ingeniería de Prompts](README.md)<br>Base metodológica necesaria|Metodología > Ingeniería de Prompts > **RAG**|[ReAct](ReAct.md)<br>Reasoning + Acting
|[Componentes de prompts](../prompts/componentes.md)<br>Contexto y estructura||[Chain of Thought](chainOfThought.md)<br>Razonamiento base

<i>**Relacionado**: [ReAct](ReAct.md) - Combinar RAG con razonamiento / [Use texto de referencia](../prompts/mejoresPracticas/usoTextoReferencia.md) - RAG manual simple / [Casos de uso](../casosDeUso/README.md) - Aplicaciones prácticas</i>

</div>
