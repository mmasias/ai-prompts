<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Indique al modelo que responda con citas de un texto de referencia

> Bloque: Proporcionar texto de referencia

## ¿Por qué?

Pedir al modelo que cite directamente de un texto de referencia asegura que la respuesta se adhiera estrictamente a la fuente original. Las citas directas pueden añadir autenticidad y precisión a la respuesta, y garantizar que la información proporcionada esté en línea con la fuente indicada.

## ¿Qué?

Implica solicitar al modelo que, al responder, utilice fragmentos exactos o citas del texto de referencia proporcionado, asegurando así que la información transmitida sea un reflejo fiel de la fuente original.

## ¿Para qué?

- Para garantizar exactitud y fidelidad en la respuesta en relación con el texto original.
- Para proporcionar un respaldo directo y tangible de una afirmación o punto.
- Para evitar interpretaciones erróneas o respuestas que se desvíen del contenido original.

## ¿Cómo?

|||Ejemplo|
|-|-|-|
Proporcione el texto y especifique la intención|Al realizar una consulta, adjunte el texto de referencia y haga explícita la petición de que la respuesta incluya citas directas.|"De acuerdo con el siguiente informe sobre sostenibilidad en la industria textil: [texto del informe], ¿cuáles son los principales desafíos mencionados? Por favor, cita directamente del texto".
Solicite confirmación de datos o hechos|Si tiene una información y desea confirmarla o contrastarla con el texto de referencia, pida al modelo que utilice citas para hacerlo.|"He leído que la producción orgánica ha aumentado en los últimos años. Basándote en el siguiente estudio: [texto del estudio], ¿puedes confirmarlo citando partes relevantes?"
Pida análisis con respaldo de citas|Si desea una interpretación o análisis de un aspecto del texto, solicite que cualquier afirmación se respalde con citas directas.|"Analiza la percepción del público sobre la inteligencia artificial según el siguiente artículo: [texto del artículo]. Asegúrate de incluir citas que respalden tus puntos".

Solicitar al modelo que responda con citas del texto de referencia permite obtener respuestas que reflejen con exactitud y autenticidad el contenido de la fuente original, brindando mayor confianza y precisión en la información compartida.

---

## ¿Y ahora qué?

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Uso texto referencia](usoTextoReferencia.md)<br>Técnica base del bloque|Fundamentos > Prompts > Mejores prácticas > **Pedir referencias**|[Clasificación intenciones](clasificacionIntenciones.md)<br>Inicio del bloque "Divide y vencerás"
|[Mejores prácticas](README.md)<br>Marco metodológico||[Repaso conversaciones](repasoDeVezEnCuando.md)<br>Técnica de gestión de contexto

<i>**Relacionado**: [Tokens](../tokens.md) - Citas y límites de espacio / [Ventana de contexto](../ventanaDeContexto.md) - Gestión de referencias extensas</i>

</div>