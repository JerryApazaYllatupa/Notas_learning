# Ajax y WebSockets



## Protocolo http

> **Definición** 
>
> todas las peticiones de web necesitan un protocolo, es un conjunto de reglas que tienes que seguir para obtener un resultado, nos permite intercambiar información del servidor hacia el cliente 
>
> **Métodos de petición** 
>
> * `GET`:  para obtener información,`get` no podemos enviar un cuerpo el body
> * `POST`: para enviar información, con post si puedo enviar el body 
> * `PUT`: es igual que  `post`para actualizar información en el servidor que esta en el servidor
> * `DELETE`: para borrar información 
> * `OPTIONS` : nos permite hacer peticiones entre dominios diferentes
>
> y estos son como MVC que utilizamos para manejo de datos
>
> **Código de respuesta** 
>
> > el código de respuesta trata de como fue trata la solicitud enviada hacia el servidor  y estas información lo devuelve en código 
>
> * repuestas informativas : son las que empiezan de 1 al 199 
> * repuestas correctas: 200 a 299
> * redirecciones : 300
> * Errores del cliente : 400
> * Errores del servidor: 500
>
> más información [https://es.wikipedia.org/wiki/Anexo:C%C3%B3digos_de_estado_HTTP](https://es.wikipedia.org/wiki/Anexo:Códigos_de_estado_HTTP)
>
> 
>
> **Cabeceras**
>
> las  cabeceras son las informaciones extras que nos manda el servidor como lo meta datas y cookies y otras informaciones 

Objeto XMLHttpRequest

> https://developer.mozilla.org/es/docs/Web/API/XMLHttpRequest
>
> es un objeto javascript fue diseñado por Microsoft con esto lo que podemos hacer es peticiones de pequeños trozos  de una pagina web y sin que no recargue toda la pagina   y esto es ajax
>
> ` var req = new XMLHttpRequest();`
>
> Este el código HTML
>
> ```html
> 
> <!-- index.html-->
> <!DOCTYPE html>
> <html lang="en">
> 
> <head>
>     <meta charset="UTF-8">
>     <meta name="viewport" content="width=device-width, initial-scale=1.0">
>     <meta http-equiv="X-UA-Compatible" content="ie=edge">
>     <title>Mi primer XRM</title>
>     <!-- <link rel="stylesheet" href="css/styles.css"> -->
> </head>
> 
> <body>
>     <h2>hola mundo </h2>
>     <div id="myContent">
> 
>     </div>
>     <form action="./data.html" method="GET">
>         <button>Cargar clasicamente</button>
>     </form>
>     <button id="btnLoad">Cargar via ajax</button>
>     <script src="index.js"></script>
> </body>
> 
> </html>
> ```
>
> Esto va ser nuestra data
>
> ```html
> <!-- data.html -->
> <table>
>   <thead>
>     <tr>
>       <th>Nombre</th>
>       <th>Edad</th>
>     </tr>
>   </thead>
>   <tbody>
>     <tr>
>       <td>Carol</td>
>       <th>20</th>
>     </tr>
>     <tr>
>       <td>Diana</td>
>       <th>20</th>
>     </tr>
>     <tr>
>       <td>Juan</td>
>       <th>20</th>
>     </tr>
>     <tr>
>       <td>Carol</td>
>       <th>20</th>
>     </tr>
>     <tr>
>       <td>Carol</td>
>       <th>20</th>
>     </tr>
>   </tbody>
> </table>
> ```
>
> Este el código JS
>
> ```javascript
> const b = document.getElementById('btnLoad')
> const contendio = document.getElementById('myContent')
> 
> b.addEventListener('click', evt => {
>   const xhr = new XMLHttpRequest() // este el objeto
>  // xhr.open('por que tipo', 'la data', asincrona o no )
>   xhr.open('GET', './data.html', true)
>   // Que se deve hacer con la data
>   xhr.addEventListener('load', e => {
> 
>     contendio.innerHTML = e.target.responseText
>   })
>   //  realizar la peticion 
>   xhr.send() // esto en su ciclo de vida esto ya tiene que saber donde le va asignar esa información por eso es que le asignamos donde y luego lo ejecutamos 
> 
> })
> ```

## Procesando respuestas

### readState

> tenemos que entender cual es el ciclo de vida de esa petición para saber cuando tenemos que reaccionar a un evento de dicha petición  
>
> **XMLHttpRequest**
>
> este objeto tiene estos métodos 
>   https://developer.mozilla.org/es/docs/Web/API/XMLHttpRequest
>
> `responseText` : que nos  trae en si el contenido de  de la respuesta 
>
> `readyState`: tiene 5 estados 
>
> > * `UNINITIALIZED`  su valor es 0: cuando todavía no hemos llamado al método `open()` 
> >
> > * `LOADING` su valor  es 1: es cuando no se a llamado al método `send()` es decir que ya se llamó al método `open()`  
> >
> > * `LOADED` su valor es 2 : que nos informa que que ya se realizo la petición y ya se llamo la petición al método `send()` y los encabezados y los estados ya están disponibles   
> >
> > * `INTERACTIVE` su valor es 3:  Es cuando esta descargando la información `responseText`  de respuesta de nuestro servidor  
> >
> > * `COMPLETED` su valor es 4: el estado completed nos informa que la petición ya se a terminado y que ya recibimos toda la información 
> >
> >   ejercicios 
> >
> >   ```javascript
> >   // alert('hola mundo')
> >   const b = document.getElementById('btnLoad')
> >   const contendio = document.getElementById('myContent')
> >   
> >   b.addEventListener('click', evt => {
> >     const xhr = new XMLHttpRequest()
> >     console.log('Objeto creado ', xhr.readyState)
> >   
> >     xhr.open('GET', './data.html', true)
> >     console.log('Objeto abierto ', xhr.readyState)
> >   
> >     // Que se deve hacer con la data
> >     xhr.addEventListener('load', e => {
> >       console.log('Objeto cargado ', xhr.readyState)
> >   
> >       contendio.innerHTML = e.target.responseText
> >     })
> >     //  realizar la peticion 
> >   
> >     xhr.send()
> >     console.log('accion solicitado ', xhr.readyState)
> >   
> >   })
> >   ```

## Procesar data

> 
>
> AHAH: traer html que se encuentra en el servidor y ponerlo este ejemplo lo hicimos ya mar arriba traer texto plano que html

### Procesar data con JSON 







## Promesas

### Callback

> Es una función que puede ser llamada por otra función para poder ejecutar un proceso de manera síncrona es decir nosotros enviarle una función a otra función para que sea ejecutada durante el proceso de la función inicial 
>
> ```javascript
> const setText = data => {
>   myContent.textContent = data
> }
> 
> const getData = callback => {
>   setText('solicitando autorizacion')
>   setTimeout(() => {
>     callback(true)
>   },2000)
>     
> }
> 
> 
> const sowData = callback => {
>   setText('Esperando a mostrar la información')
>   setTimeout(() => {
>     callback({name: 'Jerry' })
>   },2000)
> }
> 
> 
> btn.addEventListener('click',() =>{
>   getData(auto => {
>     if(auto){
>       sowData(user=>{
>         setText(user.name)
>       })
>     }
>   })
> })
> 
> // este es el código que se ejecuta sincrona por que espera que cada 
> ```
>

### Promises

> nos permiten ejecutar funciones de manera síncrona nos van asegurar la ejecución de nuestros procesos terminen antes de ejecutar otros procesos 	una promesa es un objeto , las promesas siempre reciben una función que tendrá dos objetos de manera interna  uno que nos va permitir resolver  la promesa continuar con el proceso que  se esta realizando o rechazar la promesa es decir detener todo los procesos que se están llevando 
>
> `new Promise((resolve, reject))`
>
> ```javascript
> const setText = data => {
>   myContent.textContent = data
> }
> 
> const getData = () => {
>   return new Promise((resolve, reject)=>{
>     
>       setText('solicitando autorizacion')
>       setTimeout(() => {
>         resolve(true)
>       },2000)
>     }
>   )
> }
> 
> 
> const sowData = () => {
>   return new Promise((resolve, reject)=>{
>     setText('Esperando a mostrar la información')
>     setTimeout(() => {
>       resolve({name: 'Jerry' })
>     },2000)
>     
>   })
> 
> }
> 
> 
> btn.addEventListener('click',() =>{
>   getData()
>     .then(auto => {
>      if(auto){
>       return sowData()
>      }
>   })
>     .then(user=>{
>       setText(user.name)
>   })
> })
> ```



### async await

> esta se utiliza antes de la ejecución de la función  para indicarle a javascript  que dentro de esta función boya utilizar la palabra reservada `await` para recibir valores de promesas  sintaxis
>
> ```javascript
> const ejecutar  = async () =>{
>     console.log('saludar hola mundo')
>     await unaPromesa() // le decimos que espere a que se ejecute esta promesa 
> }
> ```
>



### Fecth

> 





