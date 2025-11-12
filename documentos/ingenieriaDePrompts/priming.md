<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Ingeniería de Prompts](README.md)<br>Base metodológica necesaria|Metodología > Ingeniería de Prompts > **Priming**|[Árbol de pensamiento](arbolPensamiento.md)<br>Estructuras complejas
|[Contexto en prompts](../prompts/componentes.md)<br>Componente clave para priming||[Chain of Thought](chainOfThought.md)<br>Razonamiento guiado

<i>**Relacionado**: [0-Shot Prompting](0ShotPrompting.md) - Otra forma de guiar sin ejemplos / [x-Shot Prompting](xShotPrompting.md) - Contraste con ejemplos / [Acrónimo](../casosDeUso/02_acronimo.md) - Caso práctico de priming</i>

</div>

# Ingeniería de Prompts > Priming

> *[Efecto relacionado con la memoria implícita por el cual la exposición a determinados estímulos influye en la respuesta que se da a estímulos presentados con posterioridad.](https://es.wikipedia.org/wiki/Primado_(psicolog%C3%ADa))*

## ¿Por qué?

- Los modelos de lenguaje vienen pre entrenados, pueden dar respuestas.
- Algunas veces estas respuestas son excesivamente generales y ambiguas.
- Además, la manera que tenemos para comunicar también puede ser ambigua.
- Hace falta reducir y afinar por ambos lados, de modo que queden más claras las intenciones del usuario y se guíen a los modelos de lenguaje para proporcionar respuestas más precisas y contextuales.

## ¿Qué?

Proceso de alimentar a un sistema de inteligencia artificial con información que oriente sus respuestas. 

En el caso de la ingeniería de prompts, nos referimos a las indicaciones o comandos iniciales que se proporcionan a un modelo de lenguaje para que genere respuestas o contenido de texto.

Esta podría ser cualquier cosa: desde la definición de un término, la descripción de una situación, o la aclaración de la intención de la pregunta.

## ¿Para qué?

Para comprender mejor la intención del usuario y generar respuestas más adecuadas.

|Respuestas 
|-|
Definir la precisión
Afinar la intención de coherencia
Más enfocadas a la intención de la pregunta

Por ejemplo, si estamos pidiendo a la IA que genere un poema, podríamos usar el priming para especificar el tono (alegre, triste), el tema (amor, naturaleza), y el estilo (haiku, soneto) que queremos.

## ¿Cómo?

El priming se logra proporcionando contexto inicial que "prepara" al modelo antes de la tarea principal. Existen varios tipos de priming que se pueden combinar:

### 1. Priming de rol

**Sin priming:**
```markdown
¿Cómo mejoro el rendimiento de mi API?
```

**Con priming de rol:**
```markdown
Actúa como un arquitecto de software senior especializado en optimización de APIs.

¿Cómo mejoro el rendimiento de mi API REST que actualmente tarda 2 segundos en responder?
```

**Por qué funciona:** El modelo ajusta su vocabulario, profundidad y enfoque según el rol asignado.

---

### 2. Priming de estilo/tono

**Sin priming:**
```markdown
Explica qué es una base de datos.
```

**Con priming de tono:**
```markdown
Explica qué es una base de datos como si estuvieras hablando con un niño de 10 años. Usa analogías simples y evita jerga técnica.
```

**Por qué funciona:** Define el nivel de complejidad y el tipo de lenguaje esperado.

---

### 3. Priming de formato

**Sin priming:**
```markdown
Dame información sobre Python.
```

**Con priming de formato:**
```markdown
Proporciona información sobre Python en el siguiente formato:

1. Definición (1 línea)
2. Usos principales (3 bullets)
3. Ventajas (3 bullets)
4. Ejemplo de código básico
```

**Por qué funciona:** Estructura la respuesta de forma predecible y reutilizable.

---

### 4. Priming de contexto temporal/situacional

**Sin priming:**
```markdown
¿Qué tecnologías debería usar?
```

**Con priming contextual:**
```markdown
Contexto: Soy desarrollador junior trabajando en una startup fintech en 2025. Tengo 3 meses para lanzar MVP.

¿Qué stack tecnológico debería usar para una aplicación de pagos móviles?
```

**Por qué funciona:** Elimina ambigüedad y permite recomendaciones específicas para la situación.

---

### 5. Priming con ejemplos previos (combinación con few-shot)

**Priming combinado:**
```markdown
Voy a pedirte que generes acrónimos creativos siguiendo este estilo:

PANAL: Puerta de Acceso Normalizada a Aplicaciones LMS
COLMENA: COmponentes Ligeros para el Modelado de ERPs de Naturaleza Académica

Ahora crea un acrónimo para: Sistema de Gestión de Respuestas Automáticas
```

**Por qué funciona:** Establece patrones mediante ejemplos antes de la tarea real.

> **Ver caso completo:** [Creación de acrónimos](/documentos/casosDeUso/02_acronimo.md)

---

### 6. Priming de restricciones

**Sin priming:**
```markdown
Escribe un artículo sobre IA.
```

**Con priming de restricciones:**
```markdown
Restricciones para este artículo:
- Longitud: 500 palabras exactas
- No mencionar: machine learning, algoritmos, datos
- Usar analogías cotidianas
- Público: personas sin conocimiento técnico

Escribe un artículo explicando qué es la inteligencia artificial.
```

**Por qué funciona:** Define límites claros que guían la generación.

---

### Combinando múltiples tipos de priming

Para tareas complejas, combina varios tipos:

```markdown
ROL: Actúa como profesor de programación para principiantes

CONTEXTO: Mis estudiantes tienen 18-20 años, nunca han programado,
y tienden a frustrarse con conceptos abstractos

TONO: Paciente, usa analogías del mundo real, celebra pequeños logros

FORMATO:
1. Concepto en una frase simple
2. Analogía del mundo real
3. Ejemplo de código comentado línea por línea
4. Ejercicio práctico

RESTRICCIONES:
- No uses términos como "compilar", "runtime", "heap" sin explicarlos
- Máximo 3 conceptos nuevos por explicación

Ahora explica: ¿Qué es una variable en programación?
```

---

### Tabla comparativa de técnicas

|Tipo de priming|Cuándo usar|Impacto principal|Ejemplo clave|
|-|-|-|-|
|**Rol**|Necesitas expertise específico|Profundidad y vocabulario|"Actúa como [experto]"
|**Estilo/Tono**|La audiencia importa|Nivel de complejidad|"Explica como si..."
|**Formato**|Necesitas estructura consistente|Organización de respuesta|"Formato: 1. ... 2. ..."
|**Contexto**|Situación específica|Relevancia de recomendaciones|"Contexto: soy [quien] en [situación]"
|**Ejemplos previos**|Patrón sutil o estilo único|Replicación de estilo|Ver acrónimos
|**Restricciones**|Limitaciones específicas|Cumplimiento de requisitos|"No uses... Máximo..."

---

### Progresión: De básico a avanzado

**Nivel 1 - Priming básico (un tipo):**
```markdown
Actúa como nutricionista.
¿Qué desayuno me recomiendas?
```

**Nivel 2 - Priming combinado (2-3 tipos):**
```markdown
Actúa como nutricionista deportivo.
Contexto: Corredor de maratones, entreno 6 días/semana.
Formato: Lista de alimentos + cantidades + timing.

¿Qué desayuno me recomiendas para día de entrenamiento intenso?
```

**Nivel 3 - Priming complejo (sistema completo):**
```markdown
ROL: Nutricionista deportivo especializado en resistencia

CONTEXTO PERSONAL:
- Corredor de maratones (nivel avanzado)
- Entrenamiento: 80km/semana
- Objetivo: Mejorar tiempo en 15 minutos
- Restricción: Intolerancia a lactosa

CONTEXTO SITUACIONAL:
- Época: Preparación para maratón en 3 meses
- Clima: Entrenamientos en verano (calor)

FORMATO DE RESPUESTA:
1. Plan de desayuno pre-entrenamiento (6:00 AM)
2. Plan de desayuno días de descanso
3. Justificación nutricional (macros)
4. Hidratación recomendada
5. Suplementación si aplica

RESTRICCIONES:
- Ingredientes disponibles en España
- Preparación < 15 minutos
- Budget: Moderado

Genera el plan de desayunos:
```

---

### Anti-patrones: Priming inefectivo

❌ **Demasiado vago:**
```markdown
Sé creativo y dame una buena respuesta sobre marketing.
```

❌ **Contradicciones internas:**
```markdown
Sé muy breve pero detallado. Usa lenguaje simple pero técnico.
```

❌ **Priming irrelevante:**
```markdown
Actúa como chef francés.
¿Cómo optimizo mi base de datos PostgreSQL?
```

❌ **Exceso de priming:**
```markdown
[10 párrafos de contexto para una pregunta simple]
```

---

### Cuándo NO usar priming

- Preguntas factuales directas ("¿Cuántos habitantes tiene Madrid?")
- Cuando el modelo ya tiene suficiente contexto
- Cuando la pregunta es auto-explicativa
- Para tareas triviales que no requieren especialización

**Regla práctica:** Si el 0-shot funciona bien, no añadas priming innecesario.
