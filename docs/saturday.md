# Saturday 25th Nov

## Javascript asíncrono y la (no) concurrencia

	Víctor Calzón
	@kungfunk
	
	Alberto Para
	@albpara
	
* Funcionamiento del `Call Stack`. Las funciones se van metiendo en la pila de llamadas según se necesitan. 
* El event loop está pendiente de la pila. Si esta estáa vacia, coje elementos de la cola de callbacks.
* La pila siempre tiene que estar vacia para que el `Event Loop` ejecute algo de la cola.

## Callbacks

* Los `callbacks` son síncronos
* Si diagonalizamos el código perdemos el control sobre la gestión de errores

### Promises

* Una `promise` es como un ticket de comida de un restaurante de comida rápida, tienes el ticket y en el futuro será una hamburguesa.
* Mejora el manejo de errores.
* Son inmutables
* Explicaciones sobre `Promise.all`

### Generators
* Empieza la fiesta...

	function *generator() {
		yield 1;
	}
	
	const g = generator
	console.log(g.next())
	
* En un generador podemos parar la ejecución de nuestro código
* Puedes generar código que no sea muy legible, hay que tener cuidado

### async / await

[![IMAGE ALT TEXT](http://img.youtube.com/vi/_LBmUwi6mEo/0.jpg)](https://www.youtube.com/watch?v=_LBmUwi6mEo)


## Los programadores no tienen porque ser malos diseñadores de interfaces

	Sebastian Hermida
	@sbastn

[https://howdns.works](https://howdns.works)

* Wireframes, esqueleto de una pantalla. Comunicar una idea.
* Accesibilidad, software para todo tipo de capacidades y discapacidades físicas
* Branding, tono y coherencia de la imagen de tu producto
* Personas, abstracción del usuario. Entender para quien estás creando esta app
* UI, ayudar al usuario a realizar una tarea
* Usabilidad, quitar problemas, barreras
* Diseño visual
* Entrevistas de usuarios. Te ayuda a saber si estás construyendo el producto para las personas correctas. *¿Qué quieren conseguir y porqué?*, y *¿Cómo lo haces ahora?*
* Diseño de la interacción
* Prototipos, wireframes que testean un flujo concreto
* Perfomance

Como influimos los desarrolladores en la UX
* Diseño de la APIs influye en la experiencia del usuario
* Docs

* Single Responsability Principle: crear pantallas con pocas tareas
* Newspaper Code Structure: Lo más importante se tiene que ver rápido. 
* YAGNI: No diseñes para todas las posibilidades solo para las mas probables
* Good Names: texto real
* DRY: Confirmaciones de las actividades. Repite, repite...
* TDD: Armar, actuar, afirmar comentado en el test
* Mock, Stub: stubea lo que no te importa
* Abstractions: buscar para un usuario tiene un nivel de abstracción que seleccionar
* Exception handling: Error en la base de datos en la pantalla es mal, dale opciones si las hay y si no feedback
* Delaying: no preguntar todo a la vez. Tener una conversación
* Consistency: Se debe definir un catálogo

**DEMO**: A partir de una interfaz terrible se va refactorizando a una interfaz limpia

* No explotes los datos al usuario, deja que el usuario vea los datos como magia
* Que no te moleste el whitespace
* Alienado todo.
* Coherencia, como le hablas al usuario
* Squint, ponte vizco a ver si ves lo que se tiene que ver.
* Copia, pero entendiendo

**No diseñes para todos los casos, solo para los más probables**

## De RESTful a GraphQL: revolucionando la forma de comunicación entre cliente y servidor

	José María Rodríguez Hurtado
	@durbon
	
### REST

* Breve repaso de REST
* Problemas que tiene REST:
	* Mas peticiones
	* Exceso de datos
	* Documentar es un dolor
	* Pobremente tipada

### GraphQL

* Lo desarrolló Facebook desde 2012, lo liberó en 2015 y lo usan muchas empresas
* Es una especificación
* single endpoint
	
		/graphql

* Vemos los recursos como un grafo
* La `mutation` es como un POST en REST. Sirve para crear o modificar un recurso

#### Core Principles
* Es fuertemente tipado 
* El servidor expone los datos que quiere mostrar. Lo hace a través de la definición de `schema`
* Estructura vs Comportamiento
* La función `resolver` es la encargada de obtener los datos al cliente. Se encarga de comprobar si los datos están en el contexto.
* Los requerimientos de datos los está definiendo el cliente.	
* GraphQL Servers desacoplado `Stitching`
* [GraphQL.org](http://graphql.org/)
* [graphql-js](https://github.com/graphql/graphql-js)

## GraphQL ha muerto: Vivan las APIs REST con Hypermedia

	Jorge Ferrer
	
	José Manuel Navarro
	@jmnavarro
	
* Primero conoce bien tu contexto y tus necesidades
* Conoce las herramientas que tienes a tú mano
* No permitas que otros elijan por ti no más (X is dead)
* API Economy
* Vuelve a salir la metáfora del enchufe en las APIs.
* Como se pueden evolucionar APIs

* REST:
	* Hypermedia
	* Shared Vocabulary
* [Richardson Maturity Model](https://martinfowler.com/articles/richardsonMaturityModel.html)

* URL de entrada
* Tipos de control estandar [IANA](https://www.iana.org/)
* [HAL](https://en.wikipedia.org/wiki/Hypertext_Application_Language)
* Se puede proporcionar una lista de acciones
* [Siren](https://github.com/kevinswiber/siren)
* Se pueden pasar por la API los campos de un formulario
* REST no tiene tipos pero se pueden definir. [schema.org](http://schema.org/) es una web de tipos de cosas que se pueden encontrar en internet. 
* En casi cualquier API vas a necesitar crear tus propios tipos. Que no sea el modelo de datos ni el modelo de negocio ya que si cambias, obligarás a cambiar a los clientes.
* Aislando los clientes de nuestros modelos haciendo un mapeo con `schema.org`
* Requieren muchas peticiones, se puede manejar con parámetros. El número de peticiones depende de tú API REST
* [RESTful Web APIS](http://shop.oreilly.com/product/0636920028468.do)

![](https://covers.oreillystatic.com/images/0636920028468/lrg.jpg)

### Claves
* Atención al mapeo de conceptos
* Estudia y aplica tipos de datos
* No ates la API a un formato de respuesta específico

### Desarrollo en el cliente
* Cada vez hay más cantidad de tipos de clientes
* Se programan clientes como un game Loop
* [RESTful Web Clients](http://shop.oreilly.com/product/0636920037958.do)

![](https://covers.oreillystatic.com/images/0636920037958/lrg.jpg)

* [evolvable-apis.org](https://evolvable-apis.org/)

## La programación funcional en la práctica ... con todas sus consecuencias.

	Juan Manuel Serrano Hidalgo
	
* Desarrollo de una App de Geofence
* Hay que detectar:
	* Descripción de las funciones
	* Comorl!!
	* Se traduce una descripción puramente declarativa
* Las descripciones se realizan como DSL

### Implementar los DSL
* `trait` define una interfaz en Scala.
* Después de la definición del interfaz, empieza la implementación con un framework. Y llega a un punto en el que se muestra que nos hemos acoplado a una interpretación asíncrona.
* Constructor de tipos se añade a la interfaz.