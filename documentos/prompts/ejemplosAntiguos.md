<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)[![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/8vP-FFF?style=flat&logo=v8&logoColor=black)](/documentos/prompts/mejoresPracticas/8virtudesDelPrompting.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

</div>

# Ejemplos históricos de mejores prácticas

> **Nota histórica:** Este documento representa la primera versión de ejemplos de prompting de este repositorio, organizada como tablas comparativas ("En lugar de" → "Mejor") segmentadas por audiencia.
>
> **Evolución:** Esta estructura fue reemplazada por:
> - [Ejemplos individuales por tipo de tarea](/documentos/prompts/ejemplos/) - Mayor profundidad pedagógica
> - [Mejores prácticas](/documentos/prompts/mejoresPracticas/) - Técnicas específicas con estructura ¿Por qué?/¿Qué?/¿Para qué?/¿Cómo?
>
> **Valor actual:** Este documento se mantiene como referencia histórica y por su enfoque de "ejemplos por audiencia" (ingenieros, marketing), que sigue siendo pedagógicamente útil para ciertos contextos de enseñanza.
>
> [← Volver a Ejemplos actuales](ejemplos.md)

---

## Versión para ingenieros

||En lugar de|Mejor
|-|-|-|
Escribir instrucciones claras|Explícame sobre las bases de datos|Explícame sobre las diferencias entre bases de datos SQL y NoSQL y sus aplicaciones típicas en el desarrollo de software
La atención al detalle ayuda a obtener respuestas relevantes|¿Cómo se prueba el software?|¿Cómo se aplica el testing unitario en el desarrollo de software utilizando el framework Jest en JavaScript?
Explicítar de qué tamaño queremos la respuesta|Explica el modelo de desarrollo de software ágil|Dame un resumen breve del modelo de desarrollo de software ágil en no más de dos frases
Pedir al modelo el que adopte un rol|Cómo evito la inyección de SQL|Como consultor de seguridad de software, describe las mejores prácticas para prevenir la inyección de SQL en una aplicación web
Un ejemplo ayuda|Escribe un caso de prueba|Escribe un caso de prueba para una función que suma dos números, similar a los casos de prueba que se escribirían usando el framework de pruebas JUnit en Java
Especifica los pasos necesarios para completar un tarea|Como implemento un API Rest|Explica los pasos para implementar una API RESTful utilizando Node.js y Express, desde la creación de un nuevo proyecto hasta la definición de rutas para obtener, publicar, actualizar y eliminar datos
*Divide y vencerás*|¿Cómo se desarrolla una aplicación web?|¿Qué lenguajes de programación se utilizan comúnmente en el desarrollo de aplicaciones web? <br/> ¿Qué es un framework y cómo se utiliza en el desarrollo de aplicaciones web? <br/> ¿Cuáles son los pasos específicos en el proceso de desarrollo de una aplicación web utilizando el framework de React?
Iterativo, incremental...

## Versión para marketing

||En lugar de|Mejor
|-|-|-|
Escribir instrucciones claras|Explícame sobre SEO|Explícame cómo las palabras clave pueden influir en la optimización de motores de búsqueda (SEO) para un sitio web de comercio electrónico
La atención al detalle ayuda a obtener respuestas relevantes|¿Cómo se hace publicidad?|¿Cómo se diseña una campaña de publicidad en Facebook para un producto de belleza destinado a mujeres de 20 a 30 años?
Explicítar de qué tamaño queremos la respuesta|Dime sobre el marketing de contenidos|Dame un resumen breve del marketing de contenidos en no más de tres frases
Pedir al modelo el que adopte un rol|Escribe un plan|Escribe un plan de marketing como si fueras el director de marketing de una startup de tecnología emergente
Un ejemplo ayuda|Escribe un copy de venta|Escribe un copy de venta para un producto de fitness, similar a las técnicas de copywriting utilizadas en las campañas de Peloton
Especifica los pasos necesarios para completar un tarea|Crea una campaña de email marketing|Diseña un plan para una campaña de email marketing de un mes para un nuevo producto, incluyendo la segmentación del público, los objetivos de la campaña, el contenido de los emails y el calendario de envío
*Divide y vencerás*|¿Cómo se realiza una investigación de mercado?|¿Qué es una investigación de mercado?<br/>¿Cuáles son los métodos comunes de recopilación de datos en una investigación de mercado?<br/>¿Cómo se analizan los datos recogidos durante una investigación de mercado?
Iterativo, incremental...

