<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Elementos

![](/documentos/imagenes/modelosUML/promptRecetaComponentesElementos.svg)

## De los componentes a los elementos, un ejemplo (Parte I)

[🔗](https://chat.openai.com/share/214692d5-7e24-4ec2-8f31-ff0bd2c4aec3)

*Quiero que me des 5 puntos principales sobre el siguiente tema. Luego quiero que escribas sobre cada punto. ¿Cuáles son algunas formas de superar el síndrome del impostor y sentirme más seguro de mis habilidades? Incluye como tema general la importancia de la autoconservación y la tenacidad mental, así como ejemplos agradables de la vida real. Cada punto debe tener sus propios títulos. Los puntos deben fluir de forma lógica. Escribe en un estilo conversacional 1 a 1, entrando en detalle. Para cada punto agrega tu propio conocimiento sobre el tema. Haz que el contenido sea impactante y atractivo utilizando un tono conversacional, usando ejemplos para ilustrar cada punto y adoptando un enfoque narrativo. No utilices jerga. No menciones nada sobre ti ni tu función. Escribe a la manera de Les Brown. Escriba desde la perspectiva de un entrenador motivacional que habla individualmente con una persona deprimida y confundida. Esto será enviado como un mensaje a personas que pueden estar experimentando este síndrome, profesionales de 30 años, con experiencia en el sector pero con dudas razonables sobre su capacidad.*

## Detalle

### Rol

Se refiere al papel o función que desempeña el usuario o el modelo en una conversación o tarea. Por ejemplo, el usuario puede asumir el rol de estudiante y el modelo el de tutor.

### Tópico

Tema o asunto principal que se está abordando o discutiendo.

### Consulta

Pregunta o solicitud de información que el usuario presenta al modelo.

### Comando

Instrucción directa dada al modelo para realizar una acción específica.

### Acciones

Acción o conjunto de acciones que se espera que el modelo lleve a cabo en respuesta a un comando o consulta.

### Restricciones

Limitaciones o condiciones que deben ser respetadas en una tarea o respuesta.

### Objetivos

Las metas o resultados deseados que se buscan alcanzar a través de una tarea o interacción.

### Estructura

Organización o disposición de elementos en una respuesta o documento.

### Formato

Presentación estilística o disposición en la que se entrega la respuesta, como listas, párrafos, puntos, etc.

### Ejemplos

Casos representativos o ilustrativos que se brindan para clarificar o demostrar un punto.

### Audiencia

El grupo demográfico o segmento de usuarios al que está dirigida una respuesta o contenido.

### Probabilidad

Probabilidad asignada a una respuesta específica basada en el entrenamiento del modelo.

### Documento

Un texto escrito que presenta información o datos sobre un tema específico.

### Guión

Un texto que proporciona una narrativa o estructura a seguir, generalmente usado en contextos de representaciones o presentaciones.

### Temperatura

Se refiere a un parámetro que controla la aleatoriedad de las respuestas del modelo. Una temperatura alta produce respuestas más variadas, mientras que una temperatura baja produce respuestas más deterministas y centradas.

### Tokens

Segmentos de texto que el modelo reconoce. Un token puede ser tan corto como un carácter o tan largo como una palabra.

### Imagen

En algunos contextos, especialmente cuando los modelos se integran con otros sistemas, puede referirse a una representación visual o gráfica que se espera generar o sobre la cual se busca información.

## De los componentes a los elementos, un ejemplo (Parte II)



### Proceso de creación:

[🔗](https://chat.openai.com/share/214692d5-7e24-4ec2-8f31-ff0bd2c4aec3)

*Quiero que me des 5 puntos principales sobre el siguiente tema. Luego quiero que escribas sobre cada punto. ¿Cuáles son algunas formas de superar el síndrome del impostor y sentirme más seguro de mis habilidades? Incluye como tema general la importancia de la autoconservación y la tenacidad mental, así como ejemplos agradables de la vida real. Cada punto debe tener sus propios títulos. Los puntos deben fluir de forma lógica. Escribe en un estilo conversacional 1 a 1, entrando en detalle. Para cada punto agrega tu propio conocimiento sobre el tema. Haz que el contenido sea impactante y atractivo utilizando un tono conversacional, usando ejemplos para ilustrar cada punto y adoptando un enfoque narrativo. No utilices jerga. No menciones nada sobre ti ni tu función. Escribe a la manera de Les Brown. Escriba desde la perspectiva de un entrenador motivacional que habla individualmente con una persona deprimida y confundida. Esto será enviado como un mensaje a personas que pueden estar experimentando este síndrome, profesionales de 30 años, con experiencia en el sector pero con dudas razonables sobre su capacidad.*

**Proto-prompt:** Quiero ser más útil para mis subordinados en el trabajo y ayudarles a crecer. Uno de los problemas que he identificado con el que algunos luchan es el síndrome del impostor. Quiero ofrecer algunos consejos útiles.

|Componente|Elemento||
|-|-|-|
|Tarea|Comando|Quiero que me des 5 puntos principales sobre el siguiente tema. Luego quiero que escribas sobre cada punto.
||Tópico|¿Cuáles son algunas formas de superar el síndrome del impostor y sentirme más seguro de mis habilidades?
|Instrucciones|Formato|Incluye como tema general la importancia de la autoconservación y la tenacidad mental, así como ejemplos agradables de la vida real.
||Estructura|Cada punto debe tener sus propios títulos. Los puntos deben fluir de forma lógica. Escribe en un estilo conversacional 1 a 1, entrando en detalle. Para cada punto agrega tu propio conocimiento sobre el tema. Haz que el contenido sea impactante y atractivo utilizando un tono conversacional, usando ejemplos para ilustrar cada punto y adoptando un enfoque narrativo.
||Restricciones|No utilices jerga. No menciones nada sobre ti ni tu función.
||Objetivo|Escribe a la manera de Les Brown.
|Contexto|Rol|Escriba desde la perspectiva de un entrenador motivacional que habla individualmente con una persona deprimida y confundida.
||Audiencia|Esto será enviado como un mensaje a personas que pueden estar experimentando este síndrome, profesionales de 30 años, con experiencia en el sector pero con dudas razonables sobre su capacidad.

