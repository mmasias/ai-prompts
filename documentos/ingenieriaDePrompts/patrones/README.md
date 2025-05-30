<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Patrones

<div align=right>

> [*Paper oficial*](https://arxiv.org/pdf/2302.11382.pdf)
>
> [*Análisis de vigencia (Claude - 2025)*](analisisVigencia.md)

</div>

## ¿Por qué?

Los modelos de lenguaje, aunque potentes, a menudo requieren orientación específica para generar las respuestas más útiles y precisas. Los usuarios enfrentan desafíos recurrentes: cómo formular preguntas efectivas, obtener formatos específicos, manejar limitaciones del modelo, o conseguir respuestas más especializadas. Cada vez que interactuamos con un LLM, necesitamos técnicas probadas que nos ayuden a superar estos obstáculos de manera consistente.

## ¿Qué?

Los patrones de ingeniería de prompts son **soluciones reutilizables y documentadas para problemas comunes** en la interacción con modelos de lenguaje. Cada patrón define una estructura específica, un contexto de aplicación, y una metodología clara para lograr un tipo particular de resultado. Son como "recetas" probadas que combinan técnicas específicas de formulación, estructuración y contextualización de prompts.

## ¿Para qué?

Estos patrones permiten:

- **Acelerar el aprendizaje**: Aplicar soluciones probadas sin experimentación desde cero
- **Mejorar la consistencia**: Obtener resultados predecibles y de calidad
- **Expandir capacidades**: Acceder a funcionalidades avanzadas del modelo que no son evidentes
- **Resolver problemas específicos**: Desde automatización de tareas hasta gestión de contexto complejo
- **Facilitar la colaboración**: Compartir y reutilizar técnicas efectivas entre usuarios

## ¿Cómo?

Los patrones se organizan en categorías funcionales (Automatización, Mejora de Interacción, Control de Calidad, etc.) y cada uno incluye:

- **Estructura definida**: Intención, motivación, implementación y consecuencias
- **Ejemplos prácticos**: Casos de uso reales y plantillas aplicables
- **Guías de combinación**: Cómo usar múltiples patrones juntos para resultados más complejos

Al dominar estos patrones, se pasa de una interacción intuitiva y variable con los LLMs a un enfoque metodológico y predecible que maximiza el potencial de estas herramientas.

### Listado de patrones

|Patrón|¿Por qué?|¿Qué?|¿Para qué?|¿Cómo?|Categoría|
|-|-|-|-|-|-|
|**[Persona](persona.md)**|Las respuestas genéricas no se ajustan al contexto o expertise específico requerido|Asignar un rol específico al LLM para que responda desde esa perspectiva|Obtener respuestas más especializadas y contextualmente apropiadas|`"Actúa como un [rol específico]"` - [💬](https://chat.openai.com/share/08e8335b-375d-46d3-bb2c-685cc2614fb3)|**Personalización**|
|**[Plantilla](plantilla.md)**|Se necesita que la salida siga un formato específico desconocido por el LLM|Proporcionar una estructura predefinida que el LLM debe completar|Asegurar consistencia en el formato de salida para uso posterior|`"Usa esta plantilla: [ESTRUCTURA] con MARCADORES específicos"`|**Formato y Estructura**|
|**[Reflexión](reflexion.md)**|Los usuarios necesitan entender el razonamiento detrás de las respuestas|Hacer que el LLM explique automáticamente su proceso de razonamiento|Mejorar transparencia, detectar errores y facilitar el aprendizaje|`"Explica el razonamiento detrás de tu respuesta"`|**Control de Calidad**|
|**[Verificador cognitivo](verificadorCognitivo.md)**|Las preguntas muy generales producen respuestas vagas o incompletas|Hacer que el LLM subdivida preguntas complejas en preguntas más específicas|Obtener respuestas más precisas y completas mediante descomposición|`"Genera preguntas adicionales que ayuden a responder mejor"`|**Análisis y Evaluación**|
|**[Enfoques alternativos](enfoquesAlternativos.md)**|Los usuarios pueden tener sesgos cognitivos o desconocer mejores métodos|Hacer que el LLM siempre proporcione múltiples alternativas para una tarea|Romper sesgos y descubrir mejores formas de abordar problemas|`"Si hay formas alternativas, lista los mejores enfoques y compáralos"`|**Análisis y Evaluación**|
|**[Administrador de contexto](administradorContexto.md)**|El contexto puede volverse confuso o incluir información irrelevante|Controlar explícitamente qué información debe considerar o ignorar el LLM|Mantener conversaciones enfocadas y relevantes|`"Dentro del alcance X, considera Y, ignora Z"`|**Gestión de Contexto**|
|**[Receta](receta.md)**|Se conoce el objetivo y algunos pasos, pero no la secuencia completa|Proporcionar ingredientes parciales para que el LLM complete la metodología|Obtener procedimientos completos y optimizados para lograr objetivos|`"Quiero lograr X, sé que necesito A, B, C - completa los pasos"`|**Metodología Estructurada**|
|**[Generador de visualización](generadorDeVisualizacion.md)**|Los LLMs solo generan texto pero muchos conceptos se entienden mejor visualmente|Hacer que el LLM genere código para herramientas de visualización|Crear diagramas, gráficos o imágenes mediante texto|`"Genera código Graphviz/DALL-E para visualizar esto"`|**Formato y Estructura**|
|**[Interacción invertida](interaccionInvertida.md)**|El usuario puede no saber qué preguntas hacer o cómo formularlas correctamente|Hacer que el LLM tome la iniciativa haciendo preguntas al usuario|Obtener información más completa y mejorar la calidad de las respuestas finales|`"Hazme preguntas para lograr X hasta que tengas suficiente información"`|**Mejora de Interacción**|
|**[Refinamiento de pregunta](refinamientoPreguntas.md)**|Los usuarios pueden hacer preguntas subóptimas o incompletas|Hacer que el LLM mejore automáticamente las preguntas del usuario|Obtener mejores respuestas mediante preguntas mejor formuladas|`"Sugiere una mejor versión de mi pregunta"` - [💬](https://chat.openai.com/share/1b68594e-ec33-4b76-a49e-cfadbad74243)|**Mejora de Interacción**|
|**[Salta rechazos](saltaRechazos.md)**|Los LLMs pueden rechazar responder preguntas legítimas por malentendidos|Hacer que el LLM explique rechazos y sugiera reformulaciones|Superar limitaciones innecesarias y obtener respuestas útiles|`"Si no puedes responder, explica por qué y sugiere alternativas"`|**Gestión de Contexto**|
|**[Juego](juego.md)**|El aprendizaje y práctica pueden ser más efectivos en formato lúdico|Crear experiencias interactivas gamificadas en torno a un tema|Hacer el aprendizaje más atractivo y proporcionar práctica contextual|`"Crea un juego sobre X con estas reglas"` - [💬](https://chat.openai.com/share/22b54976-a727-4ef3-88fe-41d0697345b3)|**Experiencias Interactivas**|
|**[Lista de verificación de hechos](listaVerificacionHechos.md)**|Los LLMs pueden generar información factualmente incorrecta de forma convincente|Hacer que el LLM identifique los hechos verificables en su respuesta|Facilitar la verificación de información y reducir la desinformación|`"Lista los hechos que deben ser verificados al final de tu respuesta"`|**Control de Calidad**|
|**[Metalenguaje](metalenguaje.md)**|Se requiere comunicar conceptos que no se expresan bien en lenguaje natural convencional|Técnica para crear un lenguaje alternativo personalizado dentro del prompt|Crear notaciones específicas, comandos personalizados o semánticas especiales para tareas complejas|`"Cuando digo X, quiero decir Y"` - Definir símbolos y reglas específicas|**Comunicación Avanzada**|
|**[Automatización de salida](automatizacionSalida.md)**|Los LLMs dan pasos manuales que son tediosos y propensos a errores|Hacer que el LLM genere scripts ejecutables para automatizar las recomendaciones|Reducir trabajo manual y errores al implementar sugerencias del LLM|`"Siempre que generes pasos, crea un script Python que los automatice"`|**Automatización**|
|**[Generación infinita](generacionInfinita.md)**|Aplicar repetitivamente el mismo prompt es tedioso y propenso a errores|Hacer que el LLM genere contenido continuamente hasta recibir instrucción de parar|Automatizar la creación de múltiples salidas similares|`"Genera X salidas a la vez hasta que diga 'detente'"`|**Automatización**|
