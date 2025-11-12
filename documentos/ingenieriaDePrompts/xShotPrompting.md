<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[0-Shot Prompting](0ShotPrompting.md)<br>Comprende generalización básica|Metodología > Ingeniería de Prompts > **x-Shot Prompting**|[Chain of Thought](chainOfThought.md)<br>Razonamiento estructurado
|[Componentes de prompts](../prompts/componentes.md)<br>Estructura para incluir ejemplos||[Priming](priming.md)<br>Otra forma de contextualizar

<i>**Relacionado**: [Jitanjáfora](../casosDeUso/04_aprendizajeJitanjafora.md) - Caso práctico / [Acrónimos](../casosDeUso/02_acronimo.md) - Ejemplo de aplicación / [Elementos](../prompts/elementos.md) - Detalles de implementación</i>

</div>

# X-Shot prompting

## ¿Por qué?

X-shot prompting es utilizado debido a que los modelos de lenguaje de IA, aunque potentes, a veces necesitan ejemplos adicionales para comprender y responder correctamente a una solicitud de información específica. Esto es particularmente útil en casos en los que se necesitan respuestas más precisas o donde el dominio del conocimiento es más especializado.

## ¿Qué?

El término *x-shot* se refiere al número de ejemplos (donde "x" es el número) que se proporcionan al modelo para ayudarlo a entender el contexto o el tipo de respuesta que se busca. Estos ejemplos actúan como puntos de referencia para guiar al modelo.

### ¿Para qué?

Para ajustar la salida del modelo de IA y ayudarlo a generar respuestas más relevantes y precisas. 

### ¿Cómo?

El x-shot prompting funciona proporcionando ejemplos concretos que sirven como "demostración" de lo que esperas. La cantidad de ejemplos (x) varía según la complejidad de la tarea:

#### Progresión: De 1-shot a N-shot

**1-shot (un ejemplo):**
```markdown
Tarea: Clasifica el sentimiento del siguiente texto como positivo, negativo o neutral.

Ejemplo:
Texto: "¡Este producto superó mis expectativas!"
Sentimiento: Positivo

Ahora clasifica:
Texto: "El servicio fue decepcionante y lento"
Sentimiento:
```

**2-shot (dos ejemplos):**
```markdown
Tarea: Convierte descripciones técnicas a lenguaje simple.

Ejemplo 1:
Técnico: "La latencia de red excede los parámetros aceptables"
Simple: "Internet está muy lento"

Ejemplo 2:
Técnico: "El dispositivo requiere calibración de sensores"
Simple: "Hay que ajustar el aparato"

Ahora convierte:
Técnico: "Se detectó una anomalía en el sistema de autenticación"
Simple:
```

**3-shot o más (para tareas complejas):**

Útil cuando el patrón es sutil o requiere contexto adicional. Por ejemplo, crear acrónimos siguiendo un estilo específico.

#### Estructura general de un prompt few-shot

```markdown
[INSTRUCCIÓN CLARA DE LA TAREA]

Ejemplos:

[EJEMPLO 1]
Input: ...
Output: ...

[EJEMPLO 2]
Input: ...
Output: ...

[EJEMPLO 3]
Input: ...
Output: ...

Ahora aplica lo mismo a:
Input: [TU CASO ESPECÍFICO]
Output:
```

#### Casos de uso documentados

Estos casos de uso del repositorio demuestran few-shot prompting en acción:

|Caso de uso|Técnica aplicada|Enlace|
|-|-|-|
|**Jitanjáforas**|Se proporcionan ejemplos de palabras inventadas para que la IA aprenda a reconocer y generar jitanjáforas|[Ver caso completo](/documentos/casosDeUso/04_aprendizajeJitanjafora.md)
|**Creación de acrónimos**|Se muestran acrónimos previos (PANAL, COLMENA) para establecer el patrón y estilo deseado|[Ver caso completo](/documentos/casosDeUso/02_acronimo.md)
|**Estilo de escritura**|Ejemplos de texto con un estilo específico para que la IA lo replique|[Ver conversación](https://chat.openai.com/share/584af1d9-e459-4fc3-b571-bf8a3c317d66)

#### Ejemplo práctico: Extracción de información estructurada

```markdown
Extrae información de facturas en formato JSON.

Ejemplos:

Factura: "Factura #001 - Fecha: 15/03/2024 - Cliente: Acme Corp - Total: €1,250.00"
JSON: {"numero": "001", "fecha": "15/03/2024", "cliente": "Acme Corp", "total": 1250.00}

Factura: "Nº F-2024-045 | 22 Mar 2024 | TechStart SL | Importe: 3.400,50 EUR"
JSON: {"numero": "F-2024-045", "fecha": "22/03/2024", "cliente": "TechStart SL", "total": 3400.50}

Ahora extrae:
Factura: "FACT-789 del 05/04/2024 para Global Industries - Monto: 875,25€"
JSON:
```

#### Cuándo usar cada variante

|Variante|Cuándo usar|Ventajas|Limitaciones|
|-|-|-|-|
|**1-shot**|Tareas simples con patrón claro|Económico en tokens|Puede ser insuficiente para patrones sutiles
|**2-3 shot**|Tareas de complejidad media|Balance entre claridad y economía|Punto óptimo para la mayoría de casos
|**5+ shot**|Patrones complejos o sutiles|Mayor precisión y consistencia|Consume muchos tokens, riesgo de sobre-especificación

#### Consejos

[Min et al. (2022)](https://arxiv.org/abs/2202.12837) nos proporciona algunos consejos para aplicar con esta técnica:

- El espacio de etiquetas y la distribución del texto de entrada especificado por los ejemplos son ambos importantes (independientemente de si las etiquetas son correctas para las entradas individuales)
- El formato que utilice también desempeña un papel clave en el rendimiento, incluso si solo usa etiquetas aleatorias, esto es mucho mejor que no tener etiquetas en absoluto.
- Los resultados adicionales muestran que seleccionar etiquetas aleatorias de una verdadera distribución de etiquetas (en lugar de una distribución uniforme) también ayuda.
