<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Structured Outputs (Salidas Estructuradas)

> **Técnica esencial (2023-2025)** para integrar LLMs con sistemas de software

## ¿Por qué?

Los LLMs generan texto natural por defecto, pero los sistemas de software necesitan **datos estructurados** (JSON, XML, CSV) para procesarlos. Sin estructura:

- ❌ Difícil parsear respuestas del LLM
- ❌ Formato inconsistente entre respuestas
- ❌ Errores al integrar con bases de datos, APIs
- ❌ Requiere lógica compleja de extracción

**Structured Outputs resuelve esto garantizando que el LLM genere respuestas en formatos predefinidos y parseables.**

## ¿Qué?

Structured Outputs son técnicas y características que fuerzan al LLM a generar respuestas en formatos estructurados específicos:

### Niveles de estructura

```
Nivel 1: Texto libre
"Juan tiene 25 años y vive en Madrid"

Nivel 2: Texto con delimitadores
"Nombre: Juan | Edad: 25 | Ciudad: Madrid"

Nivel 3: Semi-estructurado
nombre: Juan
edad: 25
ciudad: Madrid

Nivel 4: Estructurado (JSON)
{"nombre": "Juan", "edad": 25, "ciudad": "Madrid"}

Nivel 5: Fuertemente tipado (JSON Schema)
{
  "nombre": string,
  "edad": number,
  "ciudad": enum["Madrid", "Barcelona", "Valencia"]
}
```

### Formatos soportados

- **JSON:** Más común, universal
- **XML:** Sistemas legacy, intercambio B2B
- **YAML:** Configuraciones, más legible
- **CSV/TSV:** Datos tabulares, Excel
- **Custom:** Formatos específicos del dominio

## ¿Para qué?

### Casos de uso

- **Integración con bases de datos:** Extraer datos para insertar en BD
- **APIs y microservicios:** Respuestas parseables por código
- **Pipelines de datos:** ETL, procesamiento batch
- **Formularios dinámicos:** Generar estructuras de formularios
- **Automatización:** Workflows que requieren datos estructurados
- **Validación:** Garantizar que la salida cumple un esquema

## ¿Cómo?

### Método 1: Prompting básico (Nivel 2)

**Prompt:**
```markdown
Extrae la siguiente información en formato JSON:

Texto: "María García, ingeniera de 32 años, trabaja en Acme Corp desde 2019"

JSON esperado:
{
  "nombre": "...",
  "profesion": "...",
  "edad": ...,
  "empresa": "...",
  "anio_inicio": ...
}
```

**Problema:** No garantiza 100% que sea JSON válido.

---

### Método 2: JSON Mode (OpenAI/Anthropic)

**Activación en API:**
```python
response = openai.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Extrae datos..."}],
    response_format={"type": "json_object"}  # ← Fuerza JSON válido
)
```

**Prompt debe mencionar "JSON":**
```markdown
Extrae la información del siguiente texto y devuélvela en formato JSON:

Texto: [...]

Responde SOLO con JSON válido.
```

---

### Método 3: Function Calling / Tool Use (Avanzado)

**Definir esquema:**
```python
tools = [{
    "type": "function",
    "function": {
        "name": "extraer_persona",
        "description": "Extrae información de una persona del texto",
        "parameters": {
            "type": "object",
            "properties": {
                "nombre": {"type": "string"},
                "edad": {"type": "number"},
                "profesion": {"type": "string"},
                "empresa": {"type": "string"}
            },
            "required": ["nombre"]
        }
    }
}]

response = openai.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Extrae: María García, 32 años..."}],
    tools=tools,
    tool_choice={"type": "function", "function": {"name": "extraer_persona"}}
)
```

**Ventajas:**
- ✅ Garantiza esquema exacto
- ✅ Validación automática de tipos
- ✅ Campos opcionales vs requeridos
- ✅ Enums, rangos, validaciones

---

### Método 4: Structured Outputs con Pydantic (Python)

**Definir modelo:**
```python
from pydantic import BaseModel

class Persona(BaseModel):
    nombre: str
    edad: int
    profesion: str
    empresa: str | None = None

# Con instructor library
import instructor
client = instructor.patch(OpenAI())

persona = client.chat.completions.create(
    model="gpt-4o",
    response_model=Persona,  # ← Modelo Pydantic
    messages=[{"role": "user", "content": "Extrae: María..."}]
)

# persona es ahora una instancia de Persona, validada
print(persona.edad)  # 32 (int, no string)
```

---

### Ejemplos prácticos

#### Ejemplo 1: Extraer entidades de noticias

**Prompt:**
```markdown
Extrae entidades del siguiente artículo en formato JSON:

ARTÍCULO:
"Apple anunció el iPhone 15 el martes en Cupertino. El CEO Tim Cook presentó
las nuevas funcionalidades. Las acciones subieron 3.2% en NASDAQ."

FORMATO JSON:
{
  "empresas": ["nombre1", "nombre2"],
  "productos": ["producto1"],
  "personas": [{"nombre": "...", "cargo": "..."}],
  "ubicaciones": ["ubicacion1"],
  "metricas": [{"tipo": "...", "valor": ..., "unidad": "..."}]
}
```

**Respuesta esperada:**
```json
{
  "empresas": ["Apple", "NASDAQ"],
  "productos": ["iPhone 15"],
  "personas": [{"nombre": "Tim Cook", "cargo": "CEO"}],
  "ubicaciones": ["Cupertino"],
  "metricas": [{"tipo": "variación_acciones", "valor": 3.2, "unidad": "%"}]
}
```

---

#### Ejemplo 2: Generar configuración YAML

**Prompt:**
```markdown
Genera configuración de servidor web en YAML basándote en estos requisitos:

Requisitos:
- Puerto: 8080
- SSL habilitado
- Logs en /var/log/app.log
- Máximo 100 conexiones
- Timeout de 30 segundos

Formato YAML con estructura estándar de nginx.
```

**Respuesta:**
```yaml
server:
  port: 8080
  ssl:
    enabled: true
  logging:
    path: /var/log/app.log
    level: info
  limits:
    max_connections: 100
    timeout: 30
```

---

#### Ejemplo 3: Convertir lenguaje natural a SQL

**Prompt:**
```markdown
Convierte la siguiente pregunta a SQL. Devuelve JSON con la query y explicación.

Base de datos: Tabla "empleados" (id, nombre, salario, departamento, fecha_contratacion)

Pregunta: "¿Cuántos empleados de ingeniería ganan más de 50k y fueron contratados después de 2020?"

Formato:
{
  "query": "SELECT ...",
  "explicacion": "..."
}
```

---

### Mejores prácticas para Structured Outputs

#### 1. Define el esquema claramente

**❌ Malo:**
```markdown
Dame la info en JSON
```

**✅ Bueno:**
```markdown
Formato JSON exacto:
{
  "campo1": "tipo string",
  "campo2": tipo_number,
  "campo3": ["array", "de", "strings"]
}
```

---

#### 2. Proporciona ejemplos (few-shot)

```markdown
Extrae contactos del email en JSON.

Ejemplo 1:
Email: "Contacta a Juan (juan@example.com) o María (maria@example.com)"
JSON: {"contactos": [
  {"nombre": "Juan", "email": "juan@example.com"},
  {"nombre": "María", "email": "maria@example.com"}
]}

Ejemplo 2:
Email: "Escribe a support@acme.com para ayuda"
JSON: {"contactos": [
  {"nombre": null, "email": "support@acme.com"}
]}

Ahora extrae:
Email: [TU EMAIL AQUÍ]
JSON:
```

---

#### 3. Maneja casos edge

```markdown
Reglas especiales:
- Si no hay datos: retorna {} (objeto vacío)
- Si un campo es opcional y no existe: usa null
- Si una lista está vacía: usa []
- Si hay ambigüedad: incluye campo "confianza": 0-1
```

---

#### 4. Valida después de generar

```python
import json
from jsonschema import validate

response = llm.generate(prompt)
try:
    data = json.loads(response)
    validate(instance=data, schema=mi_esquema)
    # ✓ JSON válido y cumple esquema
except:
    # Reintentar o manejar error
```

---

### Patrones avanzados

#### Pattern 1: Structured Output con razonamiento

```markdown
Analiza el sentimiento del texto Y devuelve resultado estructurado.

IMPORTANTE: Primero razona, luego genera JSON.

Texto: "El producto es caro pero la calidad es excepcional"

Formato:
RAZONAMIENTO: [Tu análisis aquí]

JSON:
{
  "sentimiento_general": "positivo|negativo|neutral|mixto",
  "confianza": 0.0-1.0,
  "aspectos": [
    {"aspecto": "precio", "sentimiento": "...", "mencion": "caro"},
    {"aspecto": "calidad", "sentimiento": "...", "mencion": "excepcional"}
  ]
}
```

---

#### Pattern 2: Streaming de JSON

Para respuestas largas, streaming de arrays:

```python
# El modelo genera JSON incremental
{"items": [
  {"id": 1, "nombre": "..."},  # ← Procesar inmediatamente
  {"id": 2, "nombre": "..."},  # ← Procesar inmediatamente
  # ... más items
]}
```

---

#### Pattern 3: Multi-formato

```markdown
Genera la respuesta en AMBOS formatos:

FORMATO HUMANO (markdown):
[Explicación clara para humanos]

FORMATO MAQUINA (JSON):
{
  "dato1": "...",
  "dato2": ...
}
```

---

### Comparación de métodos

| Método | Garantía formato | Tipado | Complejidad | Cuando usar |
|--------|-----------------|--------|-------------|-------------|
| **Prompting básico** | ~85% | No | Baja | Prototipos, no crítico |
| **JSON Mode** | 99% | No | Baja | Producción simple |
| **Function Calling** | 100% | Sí | Media | Producción robusta |
| **Pydantic** | 100% | Sí | Alta | Python, máxima validación |

---

### Lenguajes y librerías

**Python:**
- instructor (Pydantic + OpenAI)
- marvin (Structured outputs fácil)
- langchain.output_parsers

**JavaScript/TypeScript:**
- zod (validación de schemas)
- langchain.js output parsers

**General:**
- JSON Schema
- OpenAPI specs
- Protocol Buffers (casos avanzados)

---

### Anti-patrones

❌ **Confiar ciegamente sin validar:**
```python
json_str = llm.generate(prompt)
data = json.loads(json_str)  # ¡Puede fallar!
# Usar data sin validar
```

❌ **Esquemas ambiguos:**
```markdown
Dame JSON con los datos
# ← ¿Qué datos? ¿Qué estructura?
```

❌ **No manejar null/undefined:**
```json
{"nombre": "", "edad": 0}  # ← ¿Vacío o unknown?
MEJOR: {"nombre": null, "edad": null}
```

❌ **Mezclar explicación con JSON:**
```
Aquí está el JSON que pediste:
{"dato": "valor"}
Como puedes ver...
# ← Difícil de parsear
```

---

### Casos de uso reales

**1. E-commerce:** Extraer productos de descripciones
```json
{
  "nombre": "MacBook Pro 14",
  "precio": 1999.00,
  "especificaciones": {
    "ram": "16GB",
    "ssd": "512GB",
    "chip": "M3 Pro"
  },
  "disponibilidad": true
}
```

**2. Legal:** Extraer cláusulas de contratos
```json
{
  "tipo_contrato": "Arrendamiento",
  "partes": ["Arrendador", "Arrendatario"],
  "duracion": {"valor": 12, "unidad": "meses"},
  "clausulas_criticas": [...]
}
```

**3. Healthcare:** Estructurar notas médicas
```json
{
  "sintomas": ["fiebre", "tos"],
  "diagnostico": "Gripe común",
  "medicacion": [
    {"nombre": "Paracetamol", "dosis": "500mg", "frecuencia": "8h"}
  ]
}
```

---

### Recursos

**Documentación oficial:**
- [OpenAI JSON Mode](https://platform.openai.com/docs/guides/structured-outputs)
- [Anthropic Tool Use](https://docs.anthropic.com/claude/docs/tool-use)
- [JSON Schema](https://json-schema.org/)

**Librerías útiles:**
- [instructor (Python)](https://github.com/jxnl/instructor)
- [marvin (Python)](https://github.com/PrefectHQ/marvin)
- [zod (TypeScript)](https://zod.dev/)

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Componentes de prompts](../prompts/componentes.md)<br>Formato y especificaciones|Metodología > Ingeniería de Prompts > **Structured Outputs**|[RAG](RAG.md)<br>Información externa estructurada
|[Ingeniería de Prompts](README.md)<br>Base metodológica||[ReAct](ReAct.md)<br>Acciones estructuradas

<i>**Relacionado**: [Automatización de salida](patrones/automatizacionSalida.md) - Patrón relacionado / [Casos de uso](../casosDeUso/README.md) - Aplicaciones prácticas</i>

</div>
