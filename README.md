# Estrategias de Modelado y Granularidad
## Maria Jose Garcia, Santiago Torres Porras, Juan Diego Rojas Espitia. 
---
## ¿Ques es la granularidad?
Las estrategias de modelado y granularidad en microservicios buscan definir límites claros del dominio con DDD y bounded contexts. Usando Event Storming se descubren eventos y dependencias para dividir servicios cohesionados y autónomos. La clave es evitar units demasiado finas o demasiado gruesas, reducir el acoplamiento y alinearlos con los cambios del negocio para escalar con seguridad y rapidez.
La granularidad determina qué tan grande o pequeño debe ser un microservicio en términos de las responsabilidades que maneja. La granularidad de los servicios es un aspecto fundamental al diseñar arquitecturas de microservicios. Una correcta granularidad nos permite aprovechar al máximo las ventajas de dicha arquitectura o por el contrario, terminar con una arquitectura llena de problemas y difícil de mantener [1]
## Principios de diseño para definir la granularidad de los microservicios
La definición de la granularidad en los microservicios debe centrarse en alcanzar un equilibrio adecuado, evitando caer en extremos como servicios demasiado grandes que terminan siendo un monolito disfrazado, o servicios demasiado pequeños que se convierten en nano-servicios difíciles de gestionar. Para guiar este diseño, se destacan principios fundamentales: la alta cohesión, que asegura que cada servicio tenga una responsabilidad clara; el bajo acoplamiento, que reduce dependencias entre servicios; la escalabilidad independiente, que permite crecer según las necesidades específicas; y la autonomía, que garantiza que cada microservicio pueda operar y evolucionar por sí mismo.
## Domain-Driven Design (DDD)
El enfoque de diseño de aplicaciones busca alinear la arquitectura del software con los objetivos del negocio. La idea central es que los desarrolladores construyan modelos directamente relacionados con los dominios específicos de la organización, utilizando un lenguaje ubicuo que unifique términos técnicos y de negocio. De esta manera, se facilita la comunicación entre equipos, se evitan malentendidos y se logra que el software refleje con mayor fidelidad las necesidades reales del negocio; La idea es modelar el software según cómo funciona realmente el negocio, no solo según la tecnología.
### ¿Cómo funcionan los microservicios de diseño impulsado por dominio?
Se dividen en dos fases:
#### Fase estratégica
Es una fase de lluvia de ideas donde los propietarios de productos, expertos en el dominio, desarrolladores y analistas se reúnen para compartir conocimientos, diseñar estrategias y crear un plan inicial.
#### Fase táctica
Acabamos de determinar los contextos delimitados y sus relaciones en la fase estratégica. Ahora bien, esta etapa del diseño orientado al dominio se centra en el modelado con la ayuda de contextos.
## Bounded Context
En Domain Driven Desing, un Bounded Context es poner límites para que un modelo del negocio tenga un significado claro y no se confunda con otras partes del sistema. El uso de Bounded Context o contextos limitados hace referencia a una buena práctica a nivel de diseño que cada día esta más en uso.

<img width="958" height="502" alt="image" src="https://github.com/user-attachments/assets/a9e76718-caf5-408d-81fd-47c8d33d02e3" />

Un modelo de clases nos ayuda a representar mejor la lógica del negocio. A partir de aquí podemos ver qué partes del sistema forman un mismo contexto y cuáles deben separarse. Cuando los modelos de clases crecen llega un momento que su tamaño es excesivo y uno de los patrones de diseño que se implementa es el de Bounded Context por el cual el modelo se divide en “submodelos” cada uno especializado en un área concreta. [3]

<img width="1157" height="632" alt="image" src="https://github.com/user-attachments/assets/76b02994-1d8f-433c-9ca9-cd986aac057c" />

Cuando el modelo de dominio se separa siempre quedan lo que se denominan los límites . ES decir por ejemplo cuando gestionamos el contexto A más orientado a Personas es posible que necesitemos tener un conocimiento muy genérico de que esa persona realiza compras y la clase que se implemente será algo como:

<img width="241" height="180" alt="image" src="https://github.com/user-attachments/assets/e2f8ce6c-7754-4c74-82f9-c8a42bbc6719" />

En cambio dentro del Bounded Context, un mismo concepto (como "Compra") puede estar mucho más detallado y con relaciones que en otros lugares del sistema donde solo necesitan una versión simple.

<img width="718" height="291" alt="image" src="https://github.com/user-attachments/assets/f5598c3e-585d-4531-9957-db4fdf4d2557" />

### Event storming
Es una técnica colaborativa que ayuda a descubrir cómo funciona un negocio y cuáles son sus requerimientos, identificando eventos, actores, servicios externos y acciones relacionadas con las reglas de negocio. Event storming proporciona un entendimiento común y un lenguaje ubicuo. Es decir, todo problema lo podemos plasmar en diferentes esquemas o modelos y todos los miembros son capaces de entenderlo. En ningún momento entra en detalles técnicos, esa es la gran ventaja.
#### ¿Porque usarlo?
Porque todo los involucrados participan, opinan y deciden con el mismo objetivo y con el mismo lenguaje. Comparte visiones diferentes, opiniones y sobre todo con la misma meta.
### Errores comunes
Diseñar microservicios demasiado pequeños provoca exceso de comunicación entre servicios, mayor latencia y dificultad para orquestar procesos, lo que termina creando un “monolito disfrazado” sin autonomía ni escalabilidad. Además, cuando los límites se definen desde la tecnología y no desde los procesos del negocio, los servicios pierden cohesión y claridad en sus responsabilidades.

Por otro lado, una mala división genera duplicación de información o procesos, inconsistencias y pérdida de eficiencia, sobre todo si se requieren demasiadas llamadas para completar una tarea. Si, además, los servicios no están preparados para crecer o dividirse, se convierten en un obstáculo para la escalabilidad y evolución del sistema.
## Referencias
- [1] “Domain Driven Design: principios, beneficios y elementos — Primera Parte”, Víctor Martínez.[https://naylampmechatronics.com/blog/45_tutorial-mpu6050-acelerometro-y-giroscopio.html](https://medium.com/@vandresmartinez/granularidad-de-microservicios-3d58f3002120)
- [2] “Granularidad de microservicios”, Jonathan Loscalzo. [https://medium.com/@jonathanloscalzo/domain-driven-design-principios-beneficios-y-elementos-primera-parte-aad90f30aa35](https://medium.com/@jonathanloscalzo/domain-driven-design-principios-beneficios-y-elementos-primera-parte-aad90f30aa35)
- [3] “¿Que es un Bounded Context?”, Cecilio Álvarez Caules. [https://www.arquitecturajava.com/que-es-un-bounded-context/](https://www.arquitecturajava.com/que-es-un-bounded-context/)
