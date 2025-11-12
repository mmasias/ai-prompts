<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Recetas

## ¿Por qué?

Mientras que la "capa de componentes" se centra en definir y distinguir entre diferentes aspectos del prompt como tarea, instrucciones, contexto, entre otros; la "capa de receta" se adentra en cómo combinar y secuenciar estos componentes de manera efectiva para dirigir al modelo AI hacia un resultado deseado.

## ¿Qué?

Son combinaciones específicas y secuenciaciones de componentes (y por lo tanto, elementos) para lograr un resultado particular con el modelo de AI.

Es la metodología aplicada para ensamblar componentes y elementos de una manera que optimice el resultado.

## ¿Para qué?

Similar a una receta de cocina: no sólo se trata de tener los ingredientes correctos (elementos), sino también de combinarlos de la manera correcta (componentes) y seguir un procedimiento específico (receta).

- **Consistencia**: Asegura resultados uniformes en diferentes escenarios.
- **Eficiencia**: Agiliza la creación de prompts proporcionando una estructura clara.
- **Reutilización**: Fomenta la colaboración y mejora el rendimiento de la IA a través de la compartición y reutilización de recetas.
- **Personalización**: Permite a los usuarios adaptar soluciones manteniendo una estructura predefinida.
- **Optimización**: Mejora el rendimiento de la IA refinando y ajustando los prompts.
- **Catalogación y seguimiento del rendimiento**: Facilita la organización, gestión y seguimiento de los prompts en un repositorio centralizado.
- **Organización de proyectos**: Potencia el enfoque, la colaboración y la toma de decisiones al agrupar los prompts en proyectos.
- **Edición, dsarrollo y evaluación colaborativa**: Promueve el intercambio de conocimientos, la innovación y el trabajo en equipo manteniendo la consistencia.
- **Adaptabilidad de prompts de diversas fuentes**: Permite a los usuarios integrar diversas ideas y experticias en un formato estructurado para la mejora e innovación continua.
- **Flexibilidad**: Permite que los prompts sean programados e inyectados con parámetros en tiempo real.
- **Trazabilidad**: Habilita un control medido sobre el contenido generado.

## ¿Cómo?

- **Secuenciación**: Al igual que en una receta de cocina, el orden en que se introducen los componentes puede afectar el resultado final. Por ejemplo, especificar la audiencia al principio podría enmarcar cómo el modelo aborda el resto del prompt.
- **Combinaciones óptimas**: Algunos componentes funcionan mejor juntos que otros. La experiencia y la experimentación pueden ayudar a determinar qué combinaciones son las más efectivas para ciertas tareas.
- **Flexibilidad**: Aunque puede haber una secuencia recomendada para ciertos objetivos, la capa de receta debe permitir la adaptabilidad. Dependiendo del contexto o del modelo específico de AI, ciertas secuencias pueden ser más eficaces.
- **Iteración**: La ingeniería de prompts es un proceso iterativo. Al experimentar con diferentes recetas, uno puede refinar y ajustar los componentes para obtener resultados óptimos.

### Ya, pero ¿cómo?

[📋 Refinando un prompt](https://docs.google.com/spreadsheets/d/1nYGPwIwWd8x8eVpCEJ6pJnKO-OxhfSlaGpeCdDE3x-I/edit?usp=sharing) y guardando la trazabilidad

[📋 Propuesta de plantilla en hoja de cálculo](https://docs.google.com/spreadsheets/d/12ZWrmk_hv4i6X0tUPkBYEHCHynxTdQNHClmBFpjqbJc/edit?usp=sharing), adaptada de la sugerencia del *Prompt Institute*

## Recetas listas para usar

A continuación, plantillas concretas que puedes copiar, adaptar y usar inmediatamente. Cada receta combina [componentes](componentes.md) siguiendo las [8 virtudes del prompting](mejoresPracticas/8virtudesDelPrompting.md).

### 🎯 Receta 1: Análisis experto estructurado

**Cuándo usar:** Necesitas análisis profundo con perspectiva especializada

```markdown
ROL: Actúa como [experto en DOMINIO] con [X años de experiencia].

TAREA: Analiza [TEMA/DOCUMENTO/SITUACIÓN]

CONTEXTO:
- Audiencia: [tipo de audiencia]
- Objetivo: [propósito del análisis]
- Restricciones: [limitaciones o consideraciones]

FORMATO DE SALIDA:
1. Resumen ejecutivo (3-4 líneas)
2. Análisis detallado por [categorías relevantes]
3. Implicaciones y consecuencias
4. Recomendaciones accionables

ESTILO: [formal/conversacional/técnico], [tono], usando [terminología específica]
```

**Ejemplo aplicado:**
```markdown
ROL: Actúa como arquitecto de software senior con 15 años de experiencia en sistemas distribuidos.

TAREA: Analiza el siguiente diseño de microservicios y identifica potenciales problemas de escalabilidad.

CONTEXTO:
- Audiencia: Equipo técnico de desarrollo
- Objetivo: Preparar para lanzamiento con 100K usuarios simultáneos
- Restricciones: Presupuesto limitado de infraestructura, plazo de 3 meses

FORMATO DE SALIDA:
1. Resumen ejecutivo (3-4 líneas)
2. Análisis detallado por: arquitectura, comunicación entre servicios, persistencia, caché
3. Implicaciones y consecuencias de cada problema identificado
4. Recomendaciones accionables priorizadas

ESTILO: Técnico pero accesible, directo, usando terminología estándar de la industria
```

---

### 📝 Receta 2: Generación de contenido con restricciones

**Cuándo usar:** Crear contenido que debe cumplir criterios específicos

```markdown
TAREA: Escribe [TIPO DE CONTENIDO] sobre [TEMA]

REQUISITOS OBLIGATORIOS:
- Longitud: [específica]
- Incluir: [conceptos/palabras clave]
- Evitar: [temas/tonos]
- Audiencia: [perfil detallado]

ESTRUCTURA:
[Esquema específico con secciones]

EJEMPLOS DE ESTILO:
[Proporciona 1-2 ejemplos del estilo deseado]

CRITERIOS DE ÉXITO:
- [ ] [Criterio 1]
- [ ] [Criterio 2]
- [ ] [Criterio 3]
```

**Ejemplo aplicado:**
```markdown
TAREA: Escribe un artículo de blog sobre seguridad en APIs REST

REQUISITOS OBLIGATORIOS:
- Longitud: 800-1000 palabras
- Incluir: OAuth 2.0, rate limiting, validación de input, HTTPS
- Evitar: Jerga excesivamente técnica, suposiciones sobre conocimiento previo avanzado
- Audiencia: Desarrolladores junior con 1-2 años de experiencia

ESTRUCTURA:
1. Hook inicial (problema común de seguridad)
2. 4-5 mejores prácticas explicadas con ejemplos
3. Checklist práctica al final
4. Call-to-action para profundizar

EJEMPLOS DE ESTILO:
"En lugar de simplemente aceptar todos los requests, imagina tu API como una fortaleza: necesita guardias (autenticación), muros (rate limiting), y vigilancia constante (logging)."

CRITERIOS DE ÉXITO:
- [ ] Cada práctica tiene un ejemplo de código
- [ ] Tono conversacional pero autoritativo
- [ ] Al menos 2 analogías para conceptos complejos
```

---

### 🔄 Receta 3: Transformación de formato

**Cuándo usar:** Convertir información de un formato a otro

```markdown
INPUT: [Descripción del formato de entrada]

TAREA: Transforma el contenido a [FORMATO DE SALIDA]

REGLAS DE TRANSFORMACIÓN:
1. [Regla específica 1]
2. [Regla específica 2]
3. [Regla específica 3]

MANTENER: [Qué debe preservarse exactamente]
ADAPTAR: [Qué puede modificarse]
OMITIR: [Qué debe eliminarse]

EJEMPLO:
Input: [ejemplo concreto]
Output esperado: [transformación del ejemplo]
```

**Ejemplo aplicado:**
```markdown
INPUT: Notas de reunión en formato libre (texto corrido, bullets desordenados)

TAREA: Transforma el contenido a acta formal de reunión ejecutiva

REGLAS DE TRANSFORMACIÓN:
1. Agrupar temas relacionados bajo encabezados claros
2. Convertir decisiones en formato "DECIDIDO: [acción] - Responsable: [persona] - Fecha: [deadline]"
3. Extraer y listar explícitamente todos los action items

MANTENER: Nombres exactos de personas y fechas mencionadas
ADAPTAR: Redacción coloquial a lenguaje formal corporativo
OMITIR: Comentarios off-topic, bromas, digresiones

EJEMPLO:
Input: "entonces juan dijo que mejor movemos el deploy al viernes, todos de acuerdo, maria se encarga"
Output esperado: "DECIDIDO: Posponer deployment a viernes 15/nov - Responsable: María García - Fecha: 15/11/2024"
```

---

### 💡 Receta 4: Brainstorming estructurado

**Cuándo usar:** Generar ideas creativas con cierta dirección

```markdown
DESAFÍO: [Descripción del problema/oportunidad]

CONTEXTO:
- Restricciones: [limitaciones reales]
- Recursos disponibles: [qué hay disponible]
- Audiencia/usuarios: [para quién]

MÉTODO DE IDEACIÓN:
[SCAMPER/6 sombreros/Analogías/etc.]

GENERAR: [número] ideas que cumplan:
- Criterio 1: [específico]
- Criterio 2: [específico]
- Criterio 3: [específico]

FORMATO PARA CADA IDEA:
- Nombre/concepto
- Descripción (2-3 líneas)
- Ventajas principales (3)
- Desafíos de implementación (2)
- Nivel de originalidad: [1-5]
```

**Ejemplo aplicado:**
```markdown
DESAFÍO: Aumentar engagement de usuarios en app de aprendizaje de idiomas

CONTEXTO:
- Restricciones: Sin presupuesto para premios físicos, desarrollo debe usar stack actual (React Native)
- Recursos disponibles: Equipo de 3 developers, 8 semanas, base de usuarios de 50K
- Audiencia/usuarios: Adultos 25-40 años, aprendiendo por desarrollo profesional

MÉTODO DE IDEACIÓN:
Combinar gamificación con aprendizaje social

GENERAR: 5 ideas que cumplan:
- Criterio 1: Implementables en 8 semanas con equipo pequeño
- Criterio 2: Fomentan hábito diario sin ser intrusivas
- Criterio 3: Aprovechan motivaciones intrínsecas (logro, conexión, autonomía)

FORMATO PARA CADA IDEA:
- Nombre/concepto
- Descripción (2-3 líneas)
- Ventajas principales (3)
- Desafíos de implementación (2)
- Nivel de originalidad: [1-5]
```

---

### 🐛 Receta 5: Debugging y troubleshooting

**Cuándo usar:** Resolver problemas técnicos paso a paso

```markdown
PROBLEMA: [Descripción concreta del error/comportamiento]

CONTEXTO TÉCNICO:
- Entorno: [sistema operativo, versiones, stack]
- Qué funcionaba antes: [estado previo]
- Qué cambió: [últimas modificaciones]
- Comportamiento esperado vs actual: [comparación]

DATOS DE DEBUG:
```
[Logs, mensajes de error, stack traces]
```

PROCESO SOLICITADO:
1. Identifica las 3 causas más probables
2. Para cada causa, sugiere un paso de diagnóstico
3. Una vez identificada la causa raíz, proporciona solución paso a paso
4. Incluye cómo prevenir este problema en el futuro

FORMATO: Razonamiento claro → diagnóstico → solución → prevención
```

**Ejemplo aplicado:**
```markdown
PROBLEMA: API REST devuelve 500 Internal Server Error solo en producción, funciona en local

CONTEXTO TÉCNICO:
- Entorno: Node.js 18, Express 4.x, PostgreSQL 14, desplegado en AWS ECS
- Qué funcionaba antes: Deploy de hace 2 días funcionaba correctamente
- Qué cambió: Se añadió nuevo endpoint para reportes, se actualizó librería de conexión a DB
- Comportamiento esperado vs actual: Debería devolver JSON con datos, devuelve 500 sin mensaje

DATOS DE DEBUG:
```
2024-11-12T10:23:45Z ERROR: TypeError: Cannot read property 'rows' of undefined
    at /app/controllers/report.js:42
2024-11-12T10:23:45Z INFO: DB connection pool status: 0 active, 10 idle
```

PROCESO SOLICITADO:
1. Identifica las 3 causas más probables
2. Para cada causa, sugiere un paso de diagnóstico específico
3. Una vez identificada la causa raíz, proporciona solución paso a paso
4. Incluye cómo prevenir este problema en el futuro (CI/CD, tests, monitoring)

FORMATO: Razonamiento claro → diagnóstico → solución → prevención
```

---

### 📊 Receta 6: Comparación estructurada

**Cuándo usar:** Evaluar opciones para tomar decisiones

```markdown
OPCIONES A COMPARAR:
- Opción A: [nombre/descripción]
- Opción B: [nombre/descripción]
- Opción C: [nombre/descripción]

CONTEXTO DE DECISIÓN:
- Objetivo: [qué se busca lograr]
- Prioridades: [ordenadas por importancia]
- Deal-breakers: [qué es inaceptable]

CRITERIOS DE EVALUACIÓN:
1. [Criterio 1] - Peso: [alto/medio/bajo]
2. [Criterio 2] - Peso: [alto/medio/bajo]
3. [Criterio 3] - Peso: [alto/medio/bajo]
[...]

FORMATO DE SALIDA:
- Tabla comparativa (fila por criterio, columna por opción)
- Puntuación ponderada
- Pros/contras únicos de cada opción
- Recomendación final con justificación
- Escenarios donde cada opción sería óptima
```

**Ejemplo aplicado:**
```markdown
OPCIONES A COMPARAR:
- Opción A: PostgreSQL
- Opción B: MongoDB
- Opción C: DynamoDB

CONTEXTO DE DECISIÓN:
- Objetivo: Elegir base de datos para aplicación de e-commerce con 100K productos
- Prioridades: 1) Consistencia transaccional, 2) Costo operacional, 3) Escalabilidad
- Deal-breakers: No puede requerir gestión manual de sharding en los primeros 2 años

CRITERIOS DE EVALUACIÓN:
1. Consistencia transaccional (ACID) - Peso: alto
2. Costo mensual estimado (100K usuarios) - Peso: alto
3. Complejidad operacional - Peso: medio
4. Ecosistema y herramientas - Peso: medio
5. Capacidad de búsqueda compleja - Peso: bajo

FORMATO DE SALIDA:
- Tabla comparativa (fila por criterio, columna por opción)
- Puntuación ponderada del 1-10 por criterio
- Pros/contras únicos de cada opción
- Recomendación final con justificación basada en prioridades
- Escenarios donde cada opción sería óptima (ej: "PostgreSQL si..." / "MongoDB si...")
```

---

## Adaptando recetas a tu necesidad

Estas recetas son plantillas. Para adaptarlas:

1. **Reemplaza los [PLACEHOLDERS]** con tu información específica
2. **Ajusta el nivel de detalle** según la complejidad de tu tarea
3. **Añade o quita secciones** según necesites
4. **Combina recetas** para tareas complejas (ej: Análisis + Comparación)
5. **Itera y refina** - guarda versiones que funcionen bien para reusar

**Recuerda:** Una buena receta es [Clara, Concreta y Concisa](mejoresPracticas/8virtudesDelPrompting.md), pero también suficientemente detallada para obtener el resultado deseado.

|||
|-|-|
**Elección de una aplicación**|Se selecciona una aplicación, como MS Excel, para crear y gestionar las recetas de indicaciones.
**Definición de los componentes centrales**|Se describen los cuatro componentes principales - Tarea, Instrucciones, Contexto y Parámetros/Configuraciones.
**Creación de una estructura flexible**|Se diseña una plantilla que pueda ser fácilmente adaptada y personalizada para diversas tareas y requisitos.
**Incorporación de estandarización**|Se asegura una terminología y pautas de formato consistentes a lo largo de la plantilla.
**Inclusión de opciones de personalización**|Se indica qué partes de la plantilla pueden ser modificadas y se proporciona orientación para adaptarlas.
**Adición de documentación de metadatos**|Se proporciona información detallada sobre el propósito, uso y opciones de personalización de la plantilla, incluyendo las mejores prácticas para un rendimiento óptimo de la IA.
**Prueba y refinamiento**|Se valida la plantilla con tareas ejemplares y se realizan los ajustes necesarios para mejorar la usabilidad y efectividad.

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Componentes](componentes.md)<br>Categorías fundamentales|Fundamentos > Prompts > **Recetas**|[Ejemplos prácticos](ejemplos.md)<br>Ver recetas en acción
|[Elementos](elementos.md)<br>Especificaciones granulares||[Mejores prácticas](mejoresPracticas/README.md)<br>Aplicación sistemática
|[Anatomía de un prompt](anatomia.md)<br>Marco conceptual completo|||

<i>**Relacionado**: [8 virtudes del prompting](mejoresPracticas/8virtudesDelPrompting.md) - Principios para crear buenas recetas / [GPTs](GPTs.md) - Recetas personalizadas automatizadas / [Ingeniería de Prompts](../ingenieriaDePrompts/README.md) - Técnicas avanzadas</i>

</div>