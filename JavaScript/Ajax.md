[TOC]

# Ajax



## El protocolo HTTP

HTTP, sus siglas en ingles: "Hypertext Transfer Protocol", el es nombre de un protocolo el cual nos permite realizar una petición de datos y recursos, Como pueden ser documentos HTML, Es la base de cualquier intercambio de datos en la web, Para entender mejor sobre el protocolo vean lo de esta forma, Cuando cargamos un  pagina web ya sea online o local, en general cargamos un archivo  `index.html` o `index.php` es el servidor quien nos responde nuestra petición, en el momento de cargar este `ìndex.html` este hace otras peticiones como las estilos, imágenes, videos , archivos JavaScripts, etc. Y el encargado de responder estas peticiones es el servidor.

Cliente servidor se comunican mediante mensajes y cuando un usuario carga un pagina este abre una comunicación con el servidor  a este se le llama ***peticiones***  y cuando el servidor responde se le llama ***respuestas***.

HTTP es un protocolo ampliable, que a ido evolucionando con el tiempo. Gracias a que es un protocolo capaz de ampliarse, se usa no solo para transmitir documentos (HTML), si no que además se usa para transmitir imágenes o videos o enviar datos o contenido a los servidores, como en el caso de formularios, HTTP puede incluso para transmitir partes de documentos, y actualizar paginas sin recargar.



## Características clave del protocolo HTTP

HTTP esta pensado y desarrollado para ser leído y fácilmente comprendido por las personas, haciendo más fácil la depuración de erros con los códigos de respuestas 

HTTP es extensible  presentadas en la versión HTTP/1.0 las cabeceras de http han echo de que este protocolo sea mas fácil de ampliar y experimentar con él, Ofreciendo nuevas funcionalidades que puedan desarrollarse tan solo con un cliente y su servidor y estos comprenden la misma semántica sobre las cabeceras 

### HTTP es un protocolo con sesiones, pero sin estado

HTTP es un protocolo sin estados, es decir: no guarda ninguna dato entre dos peticiones en la misma sesión, esto trae una problemática, pero el uso de HTTP cookies si permite guardar datos con respecto  a la sesiones 

### ¿Que se puede controlar con HTTP?

Se presenta a continuación una lista de los elementos que se pueden controlar con el protocolo HTTP

- Cache .- El como se van almacenar los documentos en la cache, pueden ser especificados por HTTP, el servidor puede indicar a los proxies y clientes, que se va almacenar y durante cuanto tiempo 
- Flexibilidad del requisito de origen .- Para prevenir invasiones de privacidad de los usuarios, los navegadores solo permiten a la paginas del mismo origen, compartir la información o datos mediante las cabeceras HTTP 
- Autentificación .- Hay paginas web, que pueden estar protegidas, de manera que solo los usuarios autorizados puedan acceder  HTTP provee de servicios básicos de autentificación, como por ejemplo mediante el uso de cabeceras `www-Authenticate` o estableciendo una sesión especifica mediante el uso de sesiones en HTTP cookies 
- Sesiones .-  El uso de  HTTP cookies permite guardar peticiones que no necesitan de constante cambio en la web 



## Métodos de peticiones http

Es un conjunto de métodos de petición para indicar la acción que se deba realizar para un recurso determinado, estos son los mas utilizados 

- `GET`: El método `GET` solicita   solo peticiones de recuperar datos 

- `HEAD`: El método `HEAD` pide un respuesta idéntica a la petición GET pero sin el cuerpo de la respuesta
- `POST`: El método POST se utiliza para enviar información a un recurso especifico, causando un cabio a menudo en el estado o efectos secundarios en el servidor 
- `PUT`: Este método se utiliza para actualizar información del servidor
- `DELTE`: Borra un recurso especifico
- `CONNECT`: Este método establece un túnel hacia el servidor identificado por el recurso 
- `OPTIONS`: Este método es utilizado para describir las opciones de comunicación para el recurso de destino 
- `TRACE`: Este método realiza una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino 
- `PATH`: Este método es utilizado para hacer modificaciones parciales a un recurso 



## Códigos de estado HTTP

Estés códigos regresar cuando se hacen las peticiones 

- `100 a 199`: Cuando regresar códigos entre este rango son respuesta informativos 
- `200 a 299`: Si el código regresa entre este rango,  son repuesta correctas
- `300 a 399`: Si el código regresa entre este rango, son repuestas de redirecciones 
- `400 a 499`: Si el código regresa entre este rango, son errores de clientes como por ejemplo cuando entra a una ruta que no existe los famosos `404`
- `500 a 599`: Si el código regresa entre esta rango, son errores del servidor algo que no se haya procesado correctamente 

## Cabeceras HTTP

las cabeceras en ingles (headers HTTP)  son parámetros que se pueden enviar en una petición o respuesta  `HTTP` al cliente o servidor, son información adicional que puede ser esencial sobre la transacción en curso. 

La cabeceras se envían mediante la esta sintaxis `"Cabecera:valor"`. Las cabeceras pueden ser agrupadas de acuerdo a sus contextos 

- Cabecera general : Cabeceras que se aplican tanto como a las peticiones o respuestas, pero sin relación con los datos que finalmente se transmiten en el `body`.
- Cabeceras de consulta:  Cabeceras que contienen más información sobre el contenido que va obtenerse o sobre el cliente 
- Cabeceras de respuesta: Cabeceras que contienen más información sobre el contenido como su origen o el servidor (nombre, versión, etc.)
- Cabeceras de entidad: Cabeceras que contienen sobre el cuerpo de la entidad, como el tamaño del contenido o su MIME.

## El objeto y constructor headers()

Las cabeceras tienen el Objeto `Headers()` , vamos a ver este objeto más a detalle 

```javascript
let myHeaders = new Headers(init);
```

### Sus Métodos

`myHeaders.append('clave','valor')`: Agregar un nuevo valor al encabezado o reemplazar un valor si existe 

```javascript
myHeaders.append('Content-Type', 'image/jpeg');
```

`myHeaders.delete()`: Elimina un valor del encabezado

```javascript
myHeaders.delete('Content-Type');
```

`myHeader.entries()`:  Devuelve un `iterador`, En general un objeto y cada valor en un array

```javascript
var myHeaders = new Headers();
myHeaders.append('Content-Type', 'text/xml');
myHeaders.append('Vary', 'Accept-Language');

for (var values of myHeaders.entries()) {
   console.log(values); 
   // Array [ "content-type", "text/xml" ]
  //  Array [ "vary", "Accept-Language" ]
}

for (var values of myHeaders.entries()) {
   console.log(values[0]+ ': '+ values[1]);
   // content-type: text/xml   
   // vary: Accept-Language
}


```

`myHeaders.forEach()`:  Se puede ejecutar una función por cada elemento 

```javascript
myHeaders.forEach(el=>{
  console.log(el)
})
```

`myHeaders.get('clave')`:  Devuelve una secuencia ``ByteString`` de todos los valores de un encabezado dentro de un objeto ``Headers ``. 

```javascript
var myHeaders = new Headers();
myHeaders.append('Content-Type', 'text/xml');
myHeaders.append('Vary', 'Accept-Language');


console.log(myHeaders.get('Content-Type')) 	// text/xml
console.log(myHeaders.get('Vary')) 	// Accept-Language
```

`myHeaders.has('clave')` :  Devuelve un booleano si el objeto ``Headers`` contiene el encabezado

```javascript
var myHeaders = new Headers();
myHeaders.append('Content-Type', 'text/xml');

console.log(myHeaders.has('Content-Type'))  // true
```

` myHeader.keys() `: Devuelve un ``iterador `` con todas las claves del objeto 

```javascript
var myHeaders = new Headers();
myHeaders.append('Content-Type', 'text/xml');
myHeaders.append('Vary', 'Accept-Language');


for (let value of myHeaders.keys()){
  console.log(value)
}
```

`myHeaders.set('clave', 'valor')`: Establece un nuevo valor para un encabezado existente dentro de un objeto ``Header `` o agregar si no  existe .

```javascript
var myHeaders = new Headers();
myHeaders.append('Content-Type', 'text/xml');
myHeaders.append('Vary', 'Accept-Language');
myHeaders.set('Content-Type', 'text/xml')

for (let value of myHeaders.keys()){
  console.log(value) 
   // content-type
   // vary
}
// Algo importante no confundan con en método .append('clave','valor'), .set('clave','valor') es como actualizar y agregar pero con el método append() solo puedes agregar una vez y si lo haces 2 veces esta arrojara un error pero con .set() puedes agregar o actualizar un valor.
```

`myHeaders.values`: Devuelve un `iterador` con todos los valores de las propiedades, en este caso de las "claves"

```javascript

var myHeaders = new Headers();
myHeaders.append('Content-Type', 'text/xml');
myHeaders.append('Vary', 'Accept-Language');


for (let value of myHeaders.values()){
  console.log(value) 
   // text/xml
   // Accept-Language
}
```



### Negociación de contenido

`Accept`: Informa al servidor los diferentes tipos de datos se pueden retornar. El el tipo MIME.

```javascript
let headers = new Headers()
headers = {
	Accept: text/plain | text/html | application/xhtml+xml |application/xml |  | text
}

```

### Por terminar

- MIME = https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types
- HTTP headers = https://developer.mozilla.org/es/docs/Web/HTTP/Headers

## Ajax

JavaScript Asíncrono y XML , AJAX es un nombre engañoso. Las aplicaciones no solo pueden transportar datos XML, sino que también se puede transportar datos en texto plano y formatos JSON  

Ajax permite que las aplicaciones web se actualicen de forma asíncrona mediante el intercambio de datos con un servidor web sin tener que actualizar toda la pagina.

- Ajax no es un lenguaje de programación 
- Ajax es un técnica para acceder a servidores web desde una pagina web
- Ajax significa Asíncronos JavaScript y XML 

## Como es el proceso de Ajax

1. Se produce un evento en la pagina web 
2. JavaScript crea un objeto ``XMLHttpRequest``
3. El objeto `XMLHttpRequest` enviar una solicitud hacia el servidor web
4. El servidor procesa la solicitud 
5. El servidor envía una respuesta hacia la pagina web
6. La respuesta es leída por JavaScript 
7. La acción final y adecuada es mostrar esa información en alguna parte de la pagina web mediante JavaScript 

##  AJAX: el objeto XMLHttpRequest 

La base de Ajax es el objeto `XMLHttpRequest` Todos los navegadores modernos admiten el objeto `XMLHttpRequest`. Este objeto nos permite intercambiar datos mediante un servidor web sin tener que actualizar la pagina web 

### Como crear el objeto 

```javascript
let xhttp = new XMLHttpRequest();
```



### Accesos a través de dominios 

Por razones de seguridad los navegadores modernos no permiten transmitir  datos a través de dominios diferentes, eso significa que los archivos que desea cargar deben estar  ubicados en el mismo servidor 

### Métodos del Objeto `XMLHttpRequest`

- ` new XMLHttpRequest() `: Crea un nuevo objeto ` XMLHttpRequest `
- `abort()`: Cancela la petición actual 
- ` getAllResponseHeaders() `: Retorna toda la información del encabezado 
- ` getResponseHeader() `: Devuelve la información especifica del encabezado
- ` open(method, url, async, user, psw) `: Para abrir la solicitud 
  - ` method `:  La solicitud o petición por que método se va a realizar puede ser `GET`, `POST`
  - `url`: La ubicación del archivo 
  - ``async``: True (Asíncrono) o False(Síncrona)
  - `user`: Esté parámetro es opcional es un usuario
  - `pass`: Esté parámetro es opcional es la contraseña del usuario
- `send()`: Envía la solicitudes utilizando para las solicitudes `GET`
- `send(string)`: Envía la solicitudes al servidor, utilizado para solicitudes `POST`
- `setRequestHeader()`: Agrega un par de etiquetas al encabezado que se enviará 

### Propiedades del objeto `XMLHttpRequest`

- ` onreadystatechange `: Define una función que se llamará cuando haya un cambio en la propiedad `readyState`
- ` readyState `:  Mantiene el estado del `XMLHttpRequest`
  - 0: `UNITIALIZED`: Todavía no se llamó al método ``open()`` 
  - 1: `LOADING`: Todavía no se llamó al método `send()`
  - 2: `LOADED`: ``send()`` ya fue invocado , los encabezados y el estado ya esta disponibles 
  - 3: `INTERACTIVE`: Descargando; responseText contiene información parcial 
  - 4: `COMPLETE`: Solicitud terminada, la operación ya esta terminada 
- ` responseText `: Devuelve los datos de respuesta con una cadena 
- ` responseXML `:  Devuelve los datos de repuesta con un XML
- ` status `: Devuelve el número de estado de una petición 
- ` statusText `: Devuelve el texto del estado ejemplo('OK' o 'Not Found')



Hasta este momento ya sabemos los conceptos básicos del objeto ``XMLHttpRequest``. Para entender mas sobre esto y trabajar a profundidad con ajax necesitamos entender sobre `callbacks` `promesas` `Async await`.

## Asincronía 

La asincronía es uno de los pilares de JavaScript, afirmación JavaScript es asíncrono, pasemos a explicar sobre esto:

### Concurrencia y Paralelismo 

Concurrencia y Paralelismo son conceptos relacionados pero con una importante matriz de diferencia 

- **Concurrencia**: La concurrencia es la capacidad del CPU para procesar mas de un proceso al mismo tiempo ¿simple no?. Pero que implica realmente esto. Pues bien, para comprender esto en necesario entender como funciona un procesador. Un procesador puede al mismo tiempo el mismo números de procesos que el números de CORES que tiene, si un procesador tiene un CORE, entonces solo podrá ejecutar un proceso  a la vez, por otra parte si tenemos 8 CORES, entonces podemos ejecutar 8 procesos al mismo tiempo. Y  estos procesos no tienen por que estar relacionados. Es decir cualquiera puede iniciar terminar en el momento que desea, y el resultado de uno no afecta al otro.
- **Paralelismo**: El paralelismo sigue la filosofía de "***divide y vencerás*** " ya que consiste en tomar un único problema, y mediante concurrencia llegar a una solución más rápido. El paralelismo lo que hace es tomar tomar el problema inicial, divide el problema en fracciones mas pequeñas y luego cada fracción es procesada de forma concurrente, aprovechando al máximo la capacidad del procesador para resolver el problema. La principal diferencia del paralelismo contra la concurrencia es que en le paralelismo, todos los procesos concurrentes están íntimamente relacionados a resolver el mismo problema, de tal forma que el resultado de los demás procesos afecta al resultado final. Nota: En el paralelismo debe de haber un paso final que se encargue de unir los resultados de todos los procesos para poder arrojar un resultado final.

Conclusiones:

Podrás observar que si bien, la concurrencia y  el paralelismo está muy relacionados, no son la misma cosa, por lo  tanto, la concurrencia ayuda a procesar varias tareas al mismo tiempo,  mientras que el paralelismo resuelve una única tarea de una forma mucho  más eficiente.

### Bloqueante y no bloqueante

- **Bloqueante**: Es una llamada u operación bloqueante. Es decir no devuelve el control a la aplicación hasta que no se haya completado la operación, por lo tanto queda bloqueado y en estado de espera 
- **No bloqueante**: Una llamada no bloqueante devuelve inmediatamente el resultado de una operación si importar la respuesta que devuelva 

###  Síncrono vs Asíncrono

- **Síncrono** : Es programación  bloqueante y síncrono son similares por que trabajan en el mismo contexto, lo que nos da a entender que el código se ejecuta de manera secuencialmente y por tanto, se espera a que se complete una operación o peticiones, que es en lo que más lo utilizamos la sincrónica, bueno continuamos, la repuesta que devuelva la primera petición se puede utilizar en otra operación y así continuar con nuestro algoritmo  
- **Asíncrono**: Este concepto también es empleada como no bloqueante, es decir que si tenemos en  función en donde esa función esta haciendo una petición a una api o una petición a la base de datos, de seguro que estas peticiones requieren de un cierto tiempo para procesar esa petición y devolver una respuesta. Entonces cuando se dice que es *no bloqueante*. esa función que esta haciendo la petición no esperara a que se complete la operación simplemente mandara la petición y script continuara con el siguiente instrucción. Por eso se dice que JavaScript es asíncrono y actúa de esta forma 



Bueno ya entendimos por que JavaScript trabaja de esta forma, entonces pasemos  a temas de `callback` ,`promesas`y `Async await` . Antes de entrar a estas funciones. quiero que entiendan que estamos en tema de ajax y las peticiones, Entonces lo que hacen estos temas es que podamos hacer peticiones de manera síncrono ya que JavaScript es asíncrono, vamos a ello 

## Función Callback

Las funciones como callback, son funciones que se pasan como argumentos de otras funciones y se ejecutan de estas. Este tipo de funciones se utilizan constantemente en JavaScript, Por ejemplo cuando trabajamos con arreglos y utilizamos métodos como `forEach` o `map` estamos pasando una función como parámetro de otra, que se ejecuta por cada uno de los ejemplos del array. Empecemos viendo unos ejemplos 

```javascript
function saludar(mensaje){
  mensaje() // Hola mundo
}

saludar (function(){
  console.log('Hola mundo') 
})
```

Esto seria una clara representación de un callback, no solo podemos hacer eso si no que también podemos pasar parámetros 

```javascript
function saludarUsuario(fn) {
  let nombre = "Juan"
  fn(nombre) // Hola Juan
}

saludarUsuario(e => {
  let mensaje = `Hola: ${e}`
  console.log(mensaje)
})
```

Esto seria un claro ejemplo de un callback,  ejecutando una función con parámetros, talvez en este momento te preguntes por que hacer tanta cosa si puedo simplificar ese código, bueno veamos otro ejemplo como realmente es útil esto del callback  

### Creando nuestra propia función `` map()`` 

```javascript

function myMap(array, fn) {
  let returnArray = [];
  for (let i = 0; i < array.length; i++) {
    returnArray.push(fn(array[i]))
  }
  return returnArray
}
let arrayNumber = [1,2,3,4,5]
console.log(myMap(arrayNumber, e=>e*2)) // Array(5) [ 2, 4, 6, 8, 10 ]


let arrayText = ['Juan', 'Pedro', 'Elicoptero', 'manzana', 'pera']
myMap(arrayText, e => console.log(e)) 
/*
Jerry
juana
elicoptero
manzana
pera
*/

```

Como vemos hemos creado una función ``map()`` a código puro y así es como podemos representar muchas cosas 

## El objeto `Promise()`

El objeto  `Promise ` o (promesa ) es usado para computaciones síncronas, una promesa representa un valor que puede estar disponible ahora, en el futuro, o nunca 

Veamos esto mas a profundo, las promesas en JavaScript son muy similares  a las promesas en la vida real, veamos promesas en la vida real 

### ¿Que es una promesa?

una promesa es una garantía de que uno hará algo o que sucederá algo en particular. 

¿Entonces que sucede cuando alguien te hace una promesa? 

1. Una promesa le garantiza que se hará algo, no importa si ellos lo aran o si otros lo hacen, pero le brinda una garantía de que se cumplirá esa promesa o esa planificación
2. Una promesa se puede cumplir o romperse 
3. Cuando se cumple una promesa,puede esperar algo de esa promesa, ese resultado se puede puede utilizar para acciones o planes adicionales 
4. Cuando se rompe una promesa, le gustaría saber por que esa persona no pudo cumplir con su promesa del trato. Una vez que sepa la razón y tenga una confirmación de que la promesa se a roto, puede planificar que hacer a continuación o como manejarla 
5. Al momento de hacer una promesa, todo lo que tengamos es solo una garantía, No podemos actuar de inmediato. Podemos decir o formular que hacer cuando se cumple la promesa. Por lo tanto estamos esperando el resultado o se cumple o se rompe la promesa, en los dos casos tenemos un planificación de que se debe hacer después 
6. También existe el caso de que no reciba noticias de la persona que hizo la promesa. En tales casos preferirías mantener un umbral de tiempo. Digamos que la persona que hizo la promesa no devuelve la respuesta en 5 días, ya no le importa la respuesta después si es el caso de que le devuelva la respuesta en 10 días 



Todos estos puntos es exactamente como trabaja una promesa entonces sigamos. Hay dos partes principales para entender una promesa en JavaScript. 1.**Creación de promesas ** 2.**Manejo de promesas**

### sintaxis

```javascript
new Promise( /* ejecutor */ function(resolver, rechazar) { ... } );
```

### Parámetros

El constructor acepta una función llamada ejecutador. Esta función ejecutador acepta dos parámetros `resolve` y `reject`  que también son funciones. Las promesas se usan generalmente para un manejo más fácil de las operaciones síncrono  el código bloqueante, generalmente se utilizan para peticiones, peticiones a las apis, peticiones a base de datos, etc. como ya explicamos en este documento.  El inicio de esta operaciones ocurre dentro de la función ejecutador, si las operaciones asíncronas son exitosas, devuelve la respuesta, en la función `resolve`, si hubo algún error inesperado, el resultado se devuelve, llamando la función `reject`.

Y es  de esta forma que trabaja una promesa 

### Métodos del objeto ``Promise`` 

`Promise.all(iterable)`

Devuelve una de dos promesas: una que se cumple cuando todas las promesas en el argumento iterable han sido cumplidas, o una que se rechaza tan pronto como una de las promesas del argumento iterable es rechazada. Si la promesa retornada es cumplida, lo hace con un arreglo de los valores de las promesas cumplidas en el mismo orden definido en el iterable. Si la promesa retornada es rechazada, es rechazada con la razón de la primera promesa rechazada en el iterable. Este método puede ser útil para agregar resultados de múltiples promesas 

`Promise.race(iterable)` 

Devuelve una promesa que se cumple o rechaza tan pronto como una de las promesas del iterable se cumple o rechaza, con el valor o razón de esa promesa 

`Promise.reject(reason)` 

Devuelve un objeto `promise` que es rechazado con la razón dada 

`Promise.resolve()`

Devuelve un objeto `Promise` que es resuelto con el valor dado, Generalmente, si se quiere saber si un valor es una promesa o no, se podría usar `Promise.resolve(value)` y trabajar con el valor devuelto como una promesa. 

### Prototipo Promise

`Promise.prototype.construcctor`

Devuelve la función que creo el prototipo de una instancia esta es la función promesa por defecto 

### Métodos del prototipo 

`Promise.prototype.catch()`

Agrega una devolución de llamada del controlador de rechazo a la promesa, y devuelve una nueva promesa resolviendo el valor de devolución, o su valor de cumplimiento original si la promesa se cumple 

`Promise.prototype.then()`

Anexa cumplimientos y rechazos de una promesa, y devuelve una nueva promesa resolviendo el valor de retorno del manejador llamado o devuelve el valor original si no se manejo la promesa 

`Promise.prototype.finally()`

Agrega un controlador a la promesa y devuelve una nueva promesa que se resuelve cuando se resuelve la promesa original. Se llama al controlador cuando se cumple la promesa, ya cumplida o rechazada 

Ahora que ya sabemos toda la teoría vamos a la practica que iremos profundizando a detalle 

### Crear una promesa 

```javascript
let promesa = true;

let miPrimeraPromesa = new Promise((resolve, reject)=>{
  if(promesa){
    resolve('La petición se ha resolvido correctamente')
  }else{
    reject('La petición no se ha completado')
  }
})
console.log(miPrimeraPromesa)  
// Promise { <state>: "fulfilled", <value>: "La petición se ha resolvido correctamente" }

miPrimeraPromesa.then(success => {
  console.log(success)  //La petición se ha resolvido correctamente
})
```

Y que pasa si la promesa  o la petición no se ha completado 

```javascript
let promesa = false; //

let miPrimeraPromesa = new Promise((resolve, reject)=>{
  if(promesa){
    resolve('La petición se ha resolvido correctamente')
  }else{
    reject('La petición no se ha completado')
  }
})

miPrimeraPromesa
.then(success => {
  console.log(success)
})
.catch(error=>{
  console.log(error) //  La petición no se ha completado
})
```

### Async await

la declaración de la función `async` define a una función asíncrona, es decir que tenemos  cuando utilizamos la palabra clave `async` antes de una función indicamos que esa función es síncrona y podemos utilizar la otra palabra clave que es `await`  donde vamos a esperar respuestas de promesas, `async` solo trabaja con respuestas de promesas 

```javascript
let peticion = true;

let miPrimeraPromesa = new Promise((resolve, reject) => {
  if (peticion) {
    resolve('La petición se ha resolvido correctamente')
  } else {
    reject('La petición no se ha completado')
  }
})

const mostrardato = async () => {
  try {
    const response = await miPrimeraPromesa
    console.log(response)

  } catch (error) {
    console.log(error)
  }
}

mostrardato() 	// La petición se ha resolvido correctamente

```

## Fetch

Es una reemplazo moderno de para el objeto `XMLHttpRequest`, proporciona una interfaz para obtener recursos y proporciona un conjunto de características mas potentes y flexibles y la principal diferencia es que ya trae incluido las promesas  

El corazón de `fecth` están las abstracciones de interfaz de cargas `HtttpRquest` :`response`,  `headers` y  `body` lo que nos permite realizar peticiones de manera asíncrono 

```javascript
Fetch puro 
const fetchAjax = request => {
  let init = {
    method: request.method || 'POST',
    body: request.body,
    cache: 'default'
  }

  fetch(request.url, init)
    .then(res => {
      if (res.status == 200) {
        console.log(res)
        res.json()
      } else {
        return 'error';
      }
    })
    .then(res => res)
    .catch(err => console.error('ERROR:', err))
}
 // fetch con  Async await 
const ajax = async request => {
  let init = {
    method: request.method || 'POST',
    headers: {
      Accept: "text/plain",
    },
    body: request.body,
  }

  const response = await fetch(request.url, init)
  if (response.status == 200) {
    return await response.text()
  } else {
    return response
  }
}
```

### Por  Terminar 

-  fetch = https://javascript.info/fetch,  https://developer.mozilla.org/es/docs/Web/API/Fetch_API/Utilizando_Fetch