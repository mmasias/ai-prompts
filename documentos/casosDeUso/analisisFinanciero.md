<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Caso de Uso > Análisis Financiero

## ¿Por qué?

xQ'

## ¿Qué?

||||
|-|-|-|
El análisis financiero es un proceso de evaluación de negocios, proyectos, presupuestos y otras iniciativas financieras para determinar su rendimiento y adecuación.|Implica el uso de estados financieros para tomar decisiones sobre las operaciones y la viabilidad futura de una entidad.|Este análisis se realiza mediante la revisión de los estados financieros de la empresa, como el balance general, el estado de resultados (o cuenta de pérdidas y ganancias) y el estado de flujos de efectivo, entre otros. 

## ¿Para qué?

Los analistas financieros utilizan ratios financieros, análisis de tendencias y otras herramientas para evaluar la salud financiera de una empresa, su rentabilidad, liquidez, solvencia y eficiencia operativa.

## ¿Cómo?

### Datos necesarios

#### 1. Estados financieros

- Balance general: Información sobre activos, pasivos y patrimonio neto.
- Estado de resultados: Información sobre ingresos, costos y gastos durante un período.
- Estado de flujos de efectivo: Detalles sobre cómo entra y sale el efectivo de la empresa.

#### 2. Datos históricos

Para análisis de tendencias, sería útil tener los estados financieros de varios períodos anteriores (por ejemplo, los últimos tres a cinco años).

#### Formato de los datos:

Los datos pueden ser suministrados en formato tabular, idealmente como hojas de cálculo (Excel, Google Sheets) o en texto plano con los valores claramente especificados.

Cada estado financiero debe estar completo, incluyendo todas las líneas y categorías relevantes como activos circulantes, activos no circulantes, pasivos a corto plazo, pasivos a largo plazo, ingresos, costos de bienes vendidos, gastos operativos, entre otros.

#### Información adicional útil

Sector de la industria y tamaño de la empresa para contextualizar el análisis.

Información sobre inversiones significativas, cambios en la estructura de capital o cualquier evento no recurrente que podría haber afectado los estados financieros.

#### Con estos datos, se pueden realizar cálculos como

- Ratios de liquidez (por ejemplo, razón corriente, prueba ácida).
- Solvencia (deuda a patrimonio, deuda a activos totales).
- Rentabilidad (retorno sobre activos, retorno sobre el patrimonio).
- Eficiencia (rotación de activos, período de cobro de cuentas por cobrar).
- Entre otros...

Estos indicadores pueden proporcionar una visión general del estado financiero y el desempeño de una empresa.

### Propuesta de prompts

|Momento|Usuario|LLMs|
|-|-|-|
Prompt 1: Inicio del Análisis Financiero|Me gustaría realizar un análisis financiero de mi empresa. ¿Por dónde empezamos?|¡Perfecto! Para comenzar, necesitaré que me proporciones los estados financieros más recientes de tu empresa. Específicamente, necesito el balance general, el estado de resultados y el estado de flujos de efectivo. ¿Podrías proporcionarme esos datos?
Prompt 2: Suministro de Datos del Balance General|Aquí tienes los datos del balance general al `31 de diciembre de 202X`: activos circulantes `$X`, activos no circulantes `$Y`, pasivos a corto plazo `$Z`, pasivos a largo plazo `$A`, y patrimonio neto `$B`.|¡Gracias por la información! Ahora, ¿podrías proporcionarme los datos del estado de resultados y el estado de flujos de efectivo?
Prompt 3: Suministro de Datos del Estado de Resultados y Flujos de Efectivo|Claro, los ingresos totales fueron de `$C`, el costo de bienes vendidos fue de `$D`, los gastos operativos fueron de `$E` y el beneficio neto fue de `$F`. En cuanto al estado de flujos de efectivo, el flujo de efectivo de actividades operativas fue `$G`, de actividades de inversión `$H`, y de actividades de financiación `$I`.|Excelente, tengo toda la información necesaria. Voy a calcular algunos ratios financieros claves para evaluar la liquidez, solvencia, rentabilidad y eficiencia de tu empresa. Un momento, por favor.
Prompt 4: Análisis y Cálculo de Ratios Financieros|¿Qué ratios financieros calcularás?|Calcularé varios ratios importantes, como la razón corriente, el ratio de endeudamiento, el retorno sobre activos (**ROA**), el retorno sobre el patrimonio (**ROE**), y la rotación de activos. Estos ratios nos ayudarán a entender mejor la salud financiera de tu empresa.
Prompt 5: Presentación de Resultados|¿Qué indican los resultados?|Basándome en los ratios calculados, **[aquí explicaría los resultados de los cálculos, por ejemplo, si la empresa tiene buena liquidez, si está sobreendeudada, cómo es su rentabilidad en comparación con el sector, etc.]**. Esto sugiere que **[daría una breve interpretación de lo que estos resultados podrían significar para la salud financiera y las perspectivas futuras de la empresa]**.
Prompt 6: Consejos y Pasos Siguientes|¿Qué deberíamos hacer a continuación para mejorar nuestra situación financiera?|Basado en el análisis, te recomendaría **[aquí ofrecería consejos específicos, como mejorar la gestión del capital de trabajo, considerar refinanciar deuda, buscar formas de aumentar la eficiencia operativa, etc.]**. También sería útil revisar estos indicadores regularmente y considerar [cualquier consejo adicional específico para la situación de la empresa].

### Transcripciones

|Motor|Comentario|
|-|-|
[ChatGPT]
[Perplexity]
[Claude]
[Bard]
[NeuroFlash]
