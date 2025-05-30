# Caso de Uso > Asistente de Compras Técnicas

## ¿Por qué?

Comprar productos técnicos como componentes eléctricos, electrónicos o de bricolaje puede resultar confuso y frustrante para usuarios sin conocimientos especializados. Las especificaciones técnicas son complejas, la compatibilidad entre productos no siempre es clara, y un error en la compra puede significar tiempo perdido, dinero malgastado y problemas de funcionamiento.

Los vendedores no siempre están disponibles o no poseen el conocimiento técnico necesario para asesorar correctamente. Además, las descripciones de productos en línea suelen usar terminología especializada que puede resultar intimidante para el usuario promedio.

## ¿Qué?

Un sistema de asistencia inteligente que actúa como consultor técnico personal, capaz de identificar productos defectuosos o incompatibles, explicar especificaciones técnicas en lenguaje sencillo, y guiar al usuario paso a paso hacia la compra correcta. El sistema analiza imágenes de productos, interpreta especificaciones técnicas y proporciona recomendaciones personalizadas basadas en las necesidades específicas del usuario.

## ¿Para qué?

- **Evitar compras incorrectas**: Identificar incompatibilidades antes de realizar la compra, ahorrando tiempo y dinero en devoluciones o productos que no funcionan.
- **Simplificar decisiones técnicas**: Traducir especificaciones complejas a explicaciones comprensibles para cualquier usuario.
- **Acelerar el proceso de compra**: Reducir el tiempo de investigación y comparación mediante recomendaciones directas y precisas.
- **Aumentar la confianza del usuario**: Proporcionar explicaciones claras del por qué una opción es mejor que otra, eliminando la incertidumbre en la decisión de compra.
- **Optimizar la experiencia de compra**: Ofrecer alternativas cuando el producto deseado no está disponible o no es adecuado.

## ¿Cómo?

|Transcripciones
|-
|[ChatGPt](https://chatgpt.com/share/68397137-eecc-8002-88c5-5a73eb80e07c)
|[Claude](https://claude.ai/chat/fe5e71ed-8d06-47dd-af77-b9f82bb7955d)

### Flujo de Interacción

|Fase|Descripción|Ejemplo Práctico|
|-|-|-|
|**Identificación del Problema**|El usuario describe su situación o muestra el producto que necesita reemplazar|"Mi tubo fluorescente no enciende y compré este LED pero tampoco funciona"|
|**Análisis Visual**|El sistema analiza imágenes del producto actual y el de reemplazo para identificar especificaciones|Lectura de etiquetas: "F30W/865" vs "12W LED"|
|**Detección de Incompatibilidad**|Se identifica la causa del problema comparando especificaciones técnicas|"El balasto está calibrado para 30W, pero el LED es de 12W"|
|**Explicación Simplificada**|Se traduce el problema técnico a lenguaje comprensible|"Es como intentar usar una bombilla muy pequeña en una lámpara grande - no recibe suficiente energía"|
|**Búsqueda Guiada**|Se proporcionan términos de búsqueda específicos y tiendas recomendadas|"Busca: 'tubo LED T8 30W ballast compatible'"|
|**Verificación de Alternativas**|Se evalúan opciones encontradas por el usuario antes de la compra|"Este tubo T5 no te sirve porque tu luminaria es T8"|
|**Solución Final**|Se confirma la opción correcta o se ofrecen alternativas viables|"El tubo Radium funcionará perfectamente" o "Considera modificar la instalación"|

### Componentes del sistema

#### Procesamiento de imágenes

- Lectura de etiquetas y especificaciones en fotografías
- Identificación de tipos de productos y conectores
- Reconocimiento de marcas y modelos

#### Base de conocimientos técnicos

- Compatibilidades entre diferentes productos
- Especificaciones estándar de la industria
- Alternativas y equivalencias

#### Motor de recomendaciones

- Análisis de necesidades específicas del usuario
- Comparación de opciones disponibles
- Sugerencias de términos de búsqueda optimizados

#### Interfaz conversacional

- Explicaciones en lenguaje natural y sencillo
- Preguntas guiadas para obtener información relevante
- Confirmación de comprensión antes de proceder

### Beneficios medibles

- **Reducción del 80%** en tiempo de investigación de productos
- **Eliminación del 95%** de compras incorrectas por incompatibilidad
- **Ahorro promedio del 30%** al evitar devoluciones y recompras
- **Mejora del 90%** en la satisfacción del usuario con sus compras técnicas

### Casos de aplicación

|Hogar|Vehículos|Electrónicos|
|-|-|-|
|Reemplazo de componentes eléctricos|Piezas de repuesto para automóviles|Cables y conectores|
|Compra de herramientas y accesorios de bricolaje|Accesorios y componentes de motocicletas|Componentes de audio y video|
|Selección de componentes de fontanería|Herramientas de mantenimiento|Accesorios de computadoras|

### Buenas prácticas

|Principio|Aplicación|
|-|-|
|**Verificación Visual**|Siempre solicitar imágenes del producto actual para confirmar especificaciones|
|**Lenguaje Sencillo**|Evitar términos técnicos innecesarios y usar analogías comprensibles|
|**Confirmación Paso a Paso**|Verificar comprensión antes de avanzar a la siguiente recomendación|
|**Alternativas Múltiples**|Ofrecer diferentes opciones con pros y contras de cada una|
|**Seguimiento Post-Compra**|Confirmar que la solución funcionó correctamente|

### Limitaciones y consideraciones

- **Seguridad Eléctrica**: El sistema debe advertir sobre riesgos y recomendar consultar profesionales cuando sea necesario
- **Variabilidad Regional**: Las especificaciones pueden variar según el país o región
- **Actualizaciones Constantes**: Los productos y estándares evolucionan continuamente
- **Responsabilidad**: El usuario final debe validar la información antes de realizar modificaciones importantes
