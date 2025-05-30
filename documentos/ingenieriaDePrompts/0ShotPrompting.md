<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

<div align=right>

|Requisitos|Estás en|Sigue...|
|-|-|-|
|[Ingeniería de Prompts](README.md)<br>Base metodológica necesaria|Metodología > Ingeniería de Prompts > **0-Shot Prompting**|[x-Shot Prompting](xShotPrompting.md)<br>Aprendizaje con ejemplos
|[Tokens](../prompts/tokens.md)<br>Comprende limitaciones técnicas||[Chain of Thought](chainOfThought.md)<br>Razonamiento paso a paso

<i>**Relacionado**: [Priming](priming.md) - Guiar sin ejemplos específicos / [Patrones](patrones/README.md) - Aplicaciones estructuradas / [Mejores prácticas](../prompts/mejoresPracticas/README.md) - Optimización general</i>

</div>

# 0 Shot prompting

## ¿Por qué?

En el ámbito de la inteligencia artificial y el aprendizaje automático, la capacidad de generalizar y adaptarse a tareas nuevas sin entrenamiento previo específico es una frontera crítica. Tradicionalmente, los modelos de aprendizaje automático requieren una cantidad significativa de datos etiquetados específicos para el entrenamiento antes de poder realizar predicciones o clasificaciones efectivas. Sin embargo, esta necesidad limita su aplicabilidad en situaciones donde la obtención de datos etiquetados es difícil, costosa, o lenta. Aquí es donde entran los prompts sin entrenamiento previo (zero-shot), que permiten a los modelos realizar tareas de procesamiento de lenguaje, reconocimiento de imágenes, y más, sin necesidad de ajuste o entrenamiento previo en esos específicos escenarios de uso.

## ¿Qué?

Un prompt sin entrenamiento previo (zero-shot) se refiere a la capacidad de un modelo de inteligencia artificial, particularmente en el campo del procesamiento del lenguaje natural (PLN) y visión por computadora, de entender y completar una tarea sin haber sido explícitamente entrenado en esa tarea específica. Esto se logra mediante el diseño de modelos de aprendizaje profundo altamente generalizables que pueden aplicar conocimientos adquiridos en un contexto a una amplia variedad de otros contextos, basándose en su entrenamiento previo en tareas y datos generales, no específicos.

## ¿Para qué?

El uso de prompts zero-shot es crucial para:

- Reducir la necesidad de datos etiquetados: Permite el uso efectivo de modelos en dominios donde la recopilación de grandes volúmenes de datos etiquetados es impracticable.
- Aumentar la flexibilidad y escalabilidad de los modelos: Facilita la aplicación de modelos de IA a una gama más amplia de tareas sin necesidad de reentrenamiento, lo que reduce los costos y el tiempo de desarrollo.
- Fomentar la innovación en aplicaciones de IA: Alivia las barreras de entrada para experimentar y desarrollar nuevas aplicaciones de IA, democratizando el acceso a la tecnología de punta.

## ¿Cómo?

Para implementar y aprovechar los prompts zero-shot, se pueden seguir estos pasos:

- Desarrollo de modelos generales: Entrenar modelos en una amplia gama de datos y tareas para mejorar su capacidad de generalización. Los modelos como GPT (Generative Pre-trained Transformer) y BERT (Bidirectional Encoder Representations from Transformers) son ejemplos que han demostrado capacidades significativas en zero-shot learning debido a su diseño y preentrenamiento exhaustivos.
- Utilización de técnicas de aprendizaje por transferencia: Aprovechar el conocimiento adquirido en tareas relacionadas para mejorar el desempeño en nuevas tareas, aplicando técnicas de aprendizaje por transferencia que ajustan modelos preentrenados a tareas específicas con mínima intervención.
- Diseño de prompts inteligentes: Crear prompts bien diseñados que guíen a los modelos para aplicar su conocimiento preexistente a la nueva tarea. Esto incluye la formulación de preguntas o tareas de manera que el modelo pueda entender y aplicar sus conocimientos generales.
- Evaluación rigurosa: Probar los modelos en una variedad de escenarios para asegurar que su capacidad de generalización sea robusta y consistente.