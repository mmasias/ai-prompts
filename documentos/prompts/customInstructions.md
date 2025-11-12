<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Custom instructions de ChatGPT

## ¿Por qué?

La capacidad de personalizar la interacción y su estilo es crucial para una experiencia de usuario satisfactoria y enriquecedora.

Dado que existe una ventana de contexto que es propia de cada conversación, aparece un "problema": se tenía que empezar cada conversación desde cero.

## ¿Qué?

Custom instructions son una forma de establecer preferencias o proporcionar información específica una sola vez, de modo que el modelo las tenga en cuenta en cada respuesta posterior.

> **Nota sobre evolución (2024-2025):** Custom Instructions fue el precursor de funcionalidades más avanzadas. Actualmente se integra con la creación de [GPTs personalizados](GPTs.md), que ofrecen mayor control y capacidades. Otros modelos han desarrollado funcionalidades similares o superiores (ver comparativa más abajo).

## ¿Para qué?

Dado que cada usuario tiene necesidades y contextos únicos que desean ver reflejados en la interacción con el modelo, las instrucciones personalizadas permiten orientar la conversación de acuerdo a términos y preferencias personalizadas.

## Equivalentes en otros modelos (2024-2025)

La idea de "personalización persistente" ha evolucionado de formas distintas en cada plataforma:

|Modelo|Funcionalidad|Capacidades|Ventajas vs Custom Instructions original|
|-|-|-|-|
|**ChatGPT** (OpenAI)|Custom Instructions + GPTs|Instrucciones globales o por GPT<br>Integración con herramientas<br>Knowledge base|GPTs permiten compartir configuraciones<br>Acceso a plugins y Actions
|**Claude** (Anthropic)|Projects + Styles|Contexto compartido por proyecto<br>Base de conocimiento (hasta 200K tokens)<br>Estilos de comunicación|Projects permiten colaboración<br>Mayor ventana de contexto para conocimiento
|**Gemini** (Google)|Gems|GPTs personalizados de Google<br>Instrucciones específicas por Gem<br>Integración con Google Workspace|Integración nativa con ecosistema Google<br>Acceso a datos en tiempo real
|**Copilot** (Microsoft)|Copilot GPT Builder|Personalización integrada<br>Acceso a datos de Microsoft 365<br>Plugins empresariales|Integración empresarial profunda<br>Acceso a documentos corporativos

### Migración de Custom Instructions

Si usas Custom Instructions y quieres aprovechar funcionalidades más avanzadas:

1. **Para uso general:** Migra a [GPTs personalizados](GPTs.md) - más potentes y compartibles
2. **Para proyectos:** Usa Claude Projects si necesitas gran contexto documental (200K tokens)
3. **Para trabajo corporativo:** Copilot con integración M365
4. **Para integración Google:** Gemini Gems con Workspace

## ¿Cómo? (Custom Instructions original en ChatGPT)

### Paso 0

![](/documentos/imagenes/customInstructions0000.png)

### Paso 1

![](/documentos/imagenes/customInstructions0001.png)


A partir de la configuración de custom instructions, ChatGPT notifica que la respuesta probablemente esté *sesgada*: [*Exceso*](https://chat.openai.com/share/b505d7b7-c852-4987-bfc0-af7d800fae11)

### Limitaciones y consideraciones

- **Longitud limitada:** ~1500 caracteres por campo (mucho menos que la knowledge base de un GPT)
- **No compartibles:** Solo aplicables a tu cuenta (vs GPTs que puedes compartir)
- **Aplican globalmente:** Afectan todas las conversaciones (puede no ser deseable)
- **Cuentas gratuitas:** Funcionalidad puede estar restringida o deshabilitada
- **No persisten en modo temporal:** Se desactivan en navegación privada/guest

**Recomendación:** Para necesidades avanzadas de personalización, considera migrar a [GPTs personalizados](GPTs.md), que ofrecen mayor flexibilidad, capacidad de compartir, y knowledge bases extensas.

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[¿Qué son los prompts?](README.md)<br>Conceptos básicos|Fundamentos > Prompts > **Custom Instructions**|[GPTs](GPTs.md)<br>Personalización avanzada automatizada
|[Ventana de contexto](ventanaDeContexto.md)<br>Limitaciones técnicas||[Mejores prácticas](mejoresPracticas/README.md)<br>Optimización sistemática

<i>**Relacionado**: [Componentes](componentes.md) - Contexto persistente / [Elementos](elementos.md) - Rol y audiencia personalizados / [Casos de uso](../casosDeUso/README.md) - Aplicaciones personalizadas</i>

</div>