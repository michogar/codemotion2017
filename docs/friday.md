# Friday 24th November

## Building APIs with OpenAPIs

	Dr. Pedro J. Molina
	@pmolinam

* OpenSource generators
* [Swagger Editor](https://editor.swagger.io//)
* Casos de uso:
	* **Legacy API**: Una API sin documentar. Un endpoint para obtener el genero de un nombre.
	Se describe la especificación de la API. `Contract`. A partir del `Contract` se puede generar Servers y Clientes
	* **Contract First**: El contrato está escrito en primer lugar. Se puede generar el server y el cliente.
	* **Service Driven**: Empezar con el servicio que es el que define el contrato. La OpenAPI se genera usando reflection sobre el servicio.
* [DEMO](https://openapi3.herokuapp.com/#/login)

* [Swagger UI](http://petstore.swagger.io)

* API Management Tools. [KONG](https://getkong.org/)
	* Una capa extra para la API: Authentication, Role-Based Security...
* API Versioning:
	* Version por URL
	* Version via parametro
	* Version via headers
* API Escalabilidad
	* Sin estado
 
## Clean Architecture

	Alvaro García Loaisa
	@aloaisa

* Arquitectura de software:
	* Enterprise arcchitecture
	* System Architecture
	* Application Architecture
* [¿CQRS?](https://martinfowler.com/bliki/CQRS.html)
### Arquitectura por capas
* Dificilmente escalable
* No acepta bien los cambios
* Facilidad para saltarte las capas
* Ejemplo [Graphite](https://graphiteapp.org/)

### Event Driven Architecture
* Partes de lógica separada que está subscritan a un `broker`
* Muy desacoplada
* Maraña de eventos
* Muy escalable
* `broker` es un único punto de fallo
* Compleja de implementar
* Transacionalidad de operaciones entre unidades de procesado.

### Plug-In Architecture
* Tenemos un core y se van conectando componentes
* Se define una interfaz en el `Core`
* Mala escalabilidad
* Ejemplo, Eclipse

### Microservicios
* Desplegados muchos servicios con una responsabilidad concreta cada uno
* Completamente desacoplada

### Hexagonal Architecture
* Arquitectura de capas, pero como una cebolla
* Puertos y adaptadores, externo e internos.
* Muchas transformaciones de datos entre las capas. Disminuye el perfomance

### Clean Architecture
### Space-Based Architecture
* ZZZZZZzz

### DevOps
* Saber el ecosistema en el que va a vivir.
* Donde se va a desplegar.

## Progressive Web Applications Orientadas a Componentes con VueJS

	Rafael Casuso Romate
	@Rafael_Casuso

* Single File Components

## Oficina de Historias de Usuario y otros memes instrumentales

	Roberto Canales
	@rcanalesmora
	
* 4 Pasos
	* Subir energia
	* Bajar egos
	* Vaciar vasoe JS
	*
* [kahoot.it](https://kahoot.it)
* Te gusta programar o las endorfinas?
* Programadores frustrados -> aeromodelismo y fotografía
* El bueno siempre está jodido
* Hay que aprender los comceptos no los frameworks
	* Orientación a aspectos
* Patrones de diseño:
	* Diseño GoF
	* GRASP
	* Anti-Patrones
* **Refactorización**
* Programación Reactiva [https://www.reactivemanifesto.org/](https://www.reactivemanifesto.org/)
* Integración Continua, generar mierda continuamente.
* [AppDynamics](https://www.appdynamics.com/) & [BELK](https://www.elastic.co/blog/heya-elastic-stack-and-x-pack)
* Es facil que te pierdas entre tanta tecnología
* Aportar valor
* 12 principios del Manifiesto Agil
* Desde el punto de vista de negocio buscan que aportemos valor.
* Iteraciones cortas para que no se organice una orgia tecnológica
* No es que no tengamos memoria, es que no tenemos índices en la base de datos para recuperarla.
* Un programador debe probar y se lo pasa al compañero para probar (*Guia de demostración*)


## Anarchy in the JS (Anarchy.JS)

	Dani Latorre
	@dani_latorre
	
	Alberto Gualis
	@gualison
	
* Test de componentes para Vue, Angular y React.
* Entre Vue y React utiliza un Wrapp en test para usar `mount`.
	
```javascript
	beforeEach(async () => {
	
	})
```

Patrón `builder` se instancia el elemento en la llamada en la que se devuelve

* `Page Object Implementation`
* `SetInmediate` termina todas las promises que estén lanzadas. Para testing.
* Desacoplar el router. Validación...
* E2E - Test de aceptación. [Cucumber](https://cucumber.io/).
* **RETIROS!!!**

## Programación Reactiva con RxJS

	Pablo Magaz
	@pablo_magaz

* Programacion orientada al manejode streams
* Se representan los streams como secuencias observables.
* Operadores LINQ
* [http://rxmarbles.com](http://rxmarbles.com)

### Patron Observer
* Un productor de información `Observable` y un consumidor, `Observer`.
* Diagramas de canicas
* TODO es un stream, y TODO es un Observable
* Observables:
	* Finitos: `range`
	* Inifinitos: `fromEvent`
	
* El `observer` es el consumidor de información:
	* `next`: notifica un valor emitido por el `Observable`
	* `error`
	* `complete`
* La suscripción es que permite que el Observer reciba notificaciones del stream
* ¿Quien tiene la iniciativa de obtener información?:
	* PULL
	* PUSH: es la que usa RxJS
	
### Patron Iterator
Podemos recorrer elementos de una lista mediante el método `next`

### Programación Funcional
* Todo está pensado al empleo de funciones
* Funciones Puras y Funciones de Orden Superior (HOC)

No generan estructuras de datos intermedias. 

### Operators Everywhere
* Operadores de filtrado:
	* `filter`
	* `take`
	* `first`
* Operadores Matemáticos
	* `count`
	* `max`
* Operadores de transformación
	* `mapTo`
	* `pluck`
	* `map`
Operadores de combinación

* Un Observable puede emitir otros Observables
* Muchos operadores que acaban en Map, combinación de Map con otros operadores:
	* `mergeMap`
	* `switchMap`
	* ...
* [El Blog Isomórfico](https://pablomagaz.com/blog)

## Sobrevive al inframundo de los tests end-to-end

	Gustavo Marin
	@guumaster
	
* Ventajas:
	* Mas fiables que los unitario
	* Visión general del funcionamiento
	* Se detectan errores más rápidamente
	* Casos de usos reales
	* Automatización
	* Desatendidas
	* Velocidad

* Inconvenientes
	* Complejidad, alta curva de aprendizaje
	* Frágiles
	* Son lentos
	* Ventajas a medio / largo plazo
	
* [Gherkin 101](https://docs.hiptest.net/writing-scenarios-with-gherkin-syntax/)

### Buenas prácticas
* Desarrollo con el dueño de producto
* Happy Paths, caminos de todo va a ir bien.
* No reutilizar nada, ser independientes
* Mas declarativos menos imperativos

### Patron de PageObject
* Encapsular las APIs de webdriver/HTML
* No 100% testeo de la App
