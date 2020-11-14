

[TOC]



# JavaScript en el navegador 

## DOM

> El DOM es todo el documento del HTML  
>
> El DOM no es parte de especificación de JavaScript 
>
> El DOM es una web API
>
> Es un árbol de documentos 

### Utilizar el DOM

> * `document.doctype` : 
> *  `document.documentElement`
> * `document.head`
>   * `document.charset`
>   * `document.title`
>   * `document.style`
> * `document.body`
>   * `document.links`
>   * `document.images`
>   * `document.getSelection().toString()`
> * `document.scripts`
> * `document.styleSheets`



### Nodos

> cada etiqueta HTML, los atributos, el texto, los comentarios
>
> * `.nodeType` para ver la especificación de los nodos
>
>   	1. Elemento
>    	2. Atributo
>    	3. Texto
>    	4. Comentario
>
>   ```javascript
>   $0.nodeType // para ver el tipo de nodo
>   1
>   $0.childNodes // para ver los nodos de sus hijos
>   $0.nodeName // para el ver el nodo del nombre
>   ```
>
>   * elemento: es toda etiqueta HTML `<div></div>`
>   * atributo: 

Seleccionar nodos

> son selectores de css y funciona igualmente que css
>
> * seleccionar ids
>
>   * ​	`docuement.getElementById('')`: para seleccionar el id  del html
>
> * Selectores de css
>
>   * `document.querySelector` o `element.querySelector()` : estos elementos pueden venir del mas alto que es el DOM  o de un elemento 
>
>     ```javascript
>     console.log(document.querySelector('li'))
>     console.log(document.querySelector('#li'))
>     ```
>
>     `document.querySelectorAll()`: para traerte varios  elementos  y esto devuelve una lista por mas que sea un elemento
>
>     ```javascript
>     console.log(document.querySelectorAll('li'))
>     console.log(document.querySelectorAll('ul li'))
>     console.log(document.querySelectorAll('ul li:nth-child(2)'))
>     ```
>
>     

### Colecciones

> nodeList : Estos generalmente son respuestas cuando llamamos con `document.querySelector('li')` y esto nos devuelve todo los nodos que encuentra o resumen son nodos 
>
> ```javascript
> // lo que estamos haciendo es que  estamos convirtiendo un nodelist a un array para poder aplicarlos como array
> const nodeList = Array.from(document.querySelectorAll('ul li'))
> nodeList.map(el => el.style.background = "yellow")
> ```
>
> ```javascript
> const nodeList = Array.from(document.querySelectorAll('ul li'))
> // recorremos y lo recorremos con map y buscamo el texto
> nodeList.map(el => {
>     if (el.textContent.trim().toUpperCase() == 'ITEM') {
>         el.remove()
>     }
> })
> ```
>
> 

​		

### Atributos	

> * `.getAttribute()` : para obtener atributos de un elemento 
>
>   > ```javascript
>   > const title = document.querySelector('ul')
>   > 
>   > console.log(title.getAttribute('class'))
>   > ```
>   >
>   > 
>
> * `setAttribute('atribute','value')`: define un atributo 
>
>   > ```javascript
>   > const title = document.querySelector('ul')
>   > 
>   > 
>   > title.setAttribute('id', "menuid")
>   > title.id = 'idmenu'
>   > console.log(title.getAttribute('id'))
>   > ```
>   >
>   > 
>
> *  `clasList` : para poder traer la clase de un elemento
>
>   > * `.add()` : para agregar una clase
>   >
>   > ```javascript
>   > const title = document.getElementsByClassName('titulo')
>   > 
>   > title.classList.add('menu-activo')
>   > ```
>   >
>   > * `.remove()` : para eliminar una clase
>   >
>   > ```javascript
>   > const title = document.getElementsByClassName('titulo')
>   > title.classList.remove('menu-activo')
>   > ```
>   >
>   > 
>   >
>   > * `.toggle()` : para eliminar o para agregar una clase este pregunta si es que tiene lo elimina y si no lo tiene lo crea
>   >
>   > ```javascript
>   > const title = document.getElementsByClassName('titulo')
>   > title.classList.toggle('menu-activo')
>   > ```
>
> * `id`: para id
>
>   >```javascript
>   >title.id
>   >```
>   >
>   >
>
> * `value` : para formularios
>
>   >```javascript
>   >title.value
>   >```

### Contenido

> ​	todos estos elementos son de lectura y escritura
>
> * `.textContent` : para mostrar todo el contenido no importa cuantas capas de hijos tenga me va traer el texto 
>
>   >```javascript
>   >// para mostrar
>   >console.log(title.textContent)
>   >// para escritura
>   >title.textContent = 'hola mamá'
>   >```
>   >
>   >
>
> * `innerHTML`: me trae todo el html que tenga como hijos
>
>   >
>   >
>   >```javascript
>   >// para mostrar
>   >console.log(title.innerHTML)
>   >// para escritura
>   >title.innerHTML = `<em>Hola mundo</em>`
>   >```
>
> * `outerHTML` : me transforma todo la etiqueta a un texto y me lo muestra y cuando se utiliza para escritura este lo que hace es remplazar la etiqueta  con los nuevos datos que le das
>
>   >
>   >
>   >```javascript
>   >// para mostrar
>   >console.log(title.outerHTML)
>   >// para escritura
>   >title.outerHTML = `<h1>Hola mundo</h1>`
>   >```

### crear elementos

> * `document.createElemenet()`: para crear elementos 
>
>   >```javascript
>   >const profesor = document.createElement('h3')
>   >profesor.textContent = 'Jerry apaza'
>   >profesor.classList.add('activo')
>   >profesor.id = 'profesor'
>   >
>   >```
>   >
>   >
>
> * `.docuement.appendChild()`: para meter en alguna parte del DOM como ultimo hijo
>
>   >
>   >
>   >```javascript
>   >
>   >document.body.appendChild(profesor)
>   >```
>   >
>   >

## Eventos

> los eventos son los usuarios acciones que hace el usuario en el navegador y todo lo que veas en la consola del navegador y que empieza con on todo estos son eventos 

### addEventListener

> `addEventListener('eventName', evenHandler)`:  este es el escuchador de eventos su primer parámetro es el evento  y el segundo parámetro es la función que va realizar cuando se ejecute el evento
>
> ```javascript
> const title = document.getElementById('titulo')
> 
> const clic = ()  => alert('hola mundo')
> title.addEventListener('click', clic)
> ```

### Eventos del mouse

> * click: el clásico click
>
>   > ```javascript
>   > const title = document.getElementById('titulo')
>   > 
>   > const clic = e => alert(e.target.textContent)
>   > title.addEventListener('click', clic)
>   > ```
>   >
>   > 
>
> * dblclick : el doble click
>
>   >```javascript
>   >const title = document.getElementById('titulo')
>   >
>   >const clic = e => alert(e.target.textContent)
>   >title.addEventListener('dblclick', clic)
>   >```
>
> * mouseenter : cuando entra en área de un elemento es como un hover 
>
>   > ```javascript
>   > const title = document.getElementById('titulo')
>   > 
>   > const clic = e => alert(e.target.textContent)
>   > title.addEventListener('mouseenter', clic)
>   > ```
>   >
>   > 
>
> * mouseleave : cuando sale de un área de un elemento
>
>   > ​	
>   >
>   > ```javascript
>   > const title = document.getElementById('titulo')
>   > 
>   > const clic = e => alert(e.target.textContent)
>   > title.addEventListener('mouseleave', clic)
>   > ```
>   >
>   > 
>
> * contextmenu : para capturar el click derecho
>
>   >```javascript
>   >const title = document.getElementById('titulo')
>   >
>   >const clic = e => {
>   >    alert(e.target.textContent)
>   >    e.preventDefault() // con esto lo que le decimos es que podemos cancelar las acciones que hace ese evento que estamos ejecutando
>   >}
>   >title.addEventListener('contextmenu', clic)
>   >```
>   >
>   >
>
> * mousedown : cuando el click esta presionado mucho tiempo
>
>   >
>   >
>   >```javascript
>   >const title = document.getElementById('titulo')
>   >
>   >const clic = e => {
>   >    alert(e.target.textContent)
>   >    e.preventDefault()
>   >}
>   >title.addEventListener('mousedown', clic)
>   >```
>   >
>   >
>
> * mouseup: cuando se deja de presionar el click
>
>   >
>   >
>   >```javascript
>   >const title = document.getElementById('titulo')
>   >
>   >const clic = e => {
>   >    alert(e.target.textContent)
>   >    e.preventDefault()
>   >}
>   >title.addEventListener('mousedown', clic)
>   >```
>   >
>   >
>
> * mousemove: cuando el puntero del mouse se mueve 
>
>   >```javascript
>   >const title = document.getElementById('titulo')
>   >
>   >const clic = e => {
>   >    alert(e.target.textContent)
>   >    e.preventDefault()
>   >}
>   >title.addEventListener('mousemove', clic)
>   >
>   >```
>
>   
>
>     

### Eventos del teclado 

> * keydown : cuando presionas una tecla 
>
>   >```javascript
>   >const input = document.getElementById('input')
>   >addEventListener('keydown', e => {
>   >// para prevenir contral a 
>   >    if (e.key === 'a' && e.ctrlKey === true) {
>   >        e.preventDefault()
>   >        alert(e.key)
>   >    }
>   >})
>   >
>   >```
>   >
>   >
>
> * keyup : cuando la sueltas una tecla
>
>   > ```javascript
>   > const input = document.getElementById('input')
>   > input.addEventListener('keyup', e => {
>   >     alert(e.key)
>   > 
>   > })
>   > 
>   > ```
>   >
>   > 
>
> * keypress : cuando dejas presionado un tecla u no la suelteas
>
>   > ```javascript
>   > 
>   > ```
>
>   
>



### Eventos de formulario

> * submit : detecta el submit de todo el formulario
>
>   > ​	
>   >
>   > ```javascript
>   > const form = document.getElementById("form")
>   > 
>   > form.addEventListener('submit', () => {
>   >     console.log("a enviado el formulario")
>   > })
>   > ```
>   >
>   > 
>
> * change: ocurre cuando el input cambia de valor 
>
>   > ​	
>   >
>   > ```javascript
>   > 
>   > const form = document.getElementById("name")
>   > 
>   > form.addEventListener('change', e => {
>   >     console.log(form.value)
>   > })
>   > ```
>   >
>   > 
>
> * focus : cuando estoy con la selección en un campo
>
> * blur : cuando suelto esa selección del campo 
>
> * reset : cuando reseteas el formulario 

### Eventos del DOM y WINDOW

> * DOMContentloaded: cuando el DOM carga esto es importante cuando tu no sabes en que momento existirá al elemento al que vas a llamar 
>
> por ejemplo cuando necesitamos que un elemento se llame cuando exista  y para esto aplicamos este evento
>
> y cuando el script que llamamos esta antes que se cargue el elemento 
>
> > ```javascript
> > addEventListener('DOMContentLoaded', () => {
> >     const form = document.getElementById("name")
> > 
> > 
> >     form.addEventListener('change', e => {
> >         console.log(form.value)
> >     })
> > })
> > 
> > ```
>
> * load : esto ocurre cuando deja de cargar la pagina es decir cuando ya haya cargado todos los elementos y componentes 
>
>   > ```
>   > 
>   > ```
>   >
>   > 
>
> * scroll : Cuando se hace scroll en la pagina 
>
> * resize: Cuando redimensionamos la pantalla 
>
>   > ​	
>   >
>   > ```javascript
>   > addEventListener('resize', e => {
>   >     console.log(innerHeight)
>   >     console.log(innerWidth)
>   >     console.log(outerHeight)
>   >     console.log(outerWidth)
>   > })
>   > ```

### Eventos multimedia

>  los eventos también los puedes ejecutar y no solo escuchar en estos ejemplos te mostramos como:
>
> * play
>
>   > ```javascript
>   > const video = document.getElementById("video"),
>   >       playButon = document.getElementById('play'),
>   >       pauseButon = document.geElementById('pause');
>   > 
>   > playButon.addEventListener('click', ()=>{
>   >     video.play();
>   > })
>   > pauseButon.addEventListener('click', ()=>{
>   >     video.pause();  
>   >     playButon.click();  // un claro ejemplo
>   > 
>   > })
>   > 
>   > ```
>   >
>   > 
>
> * pause 



### Propagación de eventos 

> cada vez que ocurre un evento este ocurre en lo mas profundo del DOM y esto se propaga como burbujas o como señal 
>
> y esto ocurre cuando tenemos 2 click en bloque y cuando damos click los dos se ejecutan  para esto tenemos un método `.stopPropagation()`
>
> ```javascript
> const div1 = document.getElementById('div_1'),
>     div2 = document.getElementById('div_2'),
>     div3 = document.getElementById('div_3');
> 
> document.querySelectorAll('div').forEach(el => {
>     el.addEventListener('click', e => {
>         console.log(e.target);
>         e.stopPropagation(); // y con esto le decimos que no se proprage el evento y se quede alli
>     })
> 
> })
> 
> ```



### Delegación de eventos

> la delegación de eventos es para escuchar en donde se hizo click
>
> ```javascript
> const img = document.querySelectorAll('img')
> document.getElementById('galeria').addEventListener('click', e => {
>     const posi = e.target,
>         ima = Array.from(img),
>         i = ima.indexOf(posi)
> 
>     console.log(`hiciste click en la imagen${i + 1}`);
> })
> ```
>
> 

​	



## Recorrer y transformar el DOM



### DOM traversing 

es moverse de un lugar a otro atravesar el DOM

* Hijos

  >* `childNodes` : devuelve todos los nodos hijos
  >	
  >	>
  > >  	>  > ```javascript
  > >  	>  >   	>  > const parent = document.getElementById("parent")
  > >  	>  > ```
  >> console.log(parent.childNodes)
  >> ```
  >> 
  >> ​	
  >> ```
  >
  >* `children` : nos devuelve solo elementos hijos solo hijos no nos trae a los nietos 
  >
  >* `firstChild` : nos trae un nodo o un elemento 
  >
  >*  `firsElementChild` : nos trae el primer elemento 
  >
  >* `lastChild` : nos trae el ultimo nodo o elemento
  >
  >* `lastElementChild` : nos trae el ultimo elemento
  >
  >> ​	
  >>
  >> ```javascript
  >> const parent = document.getElementById("parent")
  >> console.log(parent.firstElementChild.textContent)
  >> // lasElementChild
  >> const parent = document.getElementById("parent")
  >> console.log(parent.lastElementChild.textContent)
  >> // lasElementChild
  >> 
  >> ```
  >>
  >> 
  >
  >
  >
  >* `hasChildNodes()`: es  un método nos devuelve true o false si es que el elemento padre tiene hijos 
  >
  >> ​	
  >>
  >> ```javascript
  >> const parent = document.getElementById("parent")
  >> console.log(parent.hasChildNodes())
  >> ```
  >>
  >> 
  >
  >* 
  >
  >

* Hermanos

  > * `nextSibling ` : Hermano siguiente o elemento siguiente o nodo 
  >
  > * `nextElementSibling` : el siguiente hermano que es un elemento 
  >
  > * `previousSibling` : El elemento previo o nodo
  >
  > * `previusElementSibling`: El hermano anterior que es un elemento
  >
  >   

* Padres

  	>  * `parentNode`: el nodo del padre
  >    	
  >    	
  >    	>  * `parentElement`: el elemento padre
  >
  >  



### Insertar elementos 

> * `appendChild()`: para insertar al final de un elemento 
>
> * `insertBefore(new,nexNode)`: insertar elementos antes de una posición 
>
>   >
>   >
>   >```javascript
>   >
>   >const parent = document.getElementById("parent")
>   >const hijo2 = document.getElementById("hijo2")
>   >// console.log(parent.hasChildNodes())
>   >
>   >const newElement = document.createElement('h2')
>   >newElement.textContent = 'Este es un nuevo elemento'
>   >
>   >const nieto = document.getElementById('nieto3')
>   >
>   >hijo2.insertBefore(newElement, nieto)
>   >```
>   >
>   >
>
> * `insertAdjacent`: coges un elemento y metes un hijo diciéndole un posición 
>
>   	> posiciones
> 	>
>   >   	> * `beforebegin`: antes de que comience un elemento  como un hermano anterior 
>   > * `afterbegin`: después de que comienza un elemento  seria como su primer hijo
>   > * `beforeend`: antes de  que acabe su ultimo hijo 
>   > * `afterend`: después de que acabe como un hermano siguiente
> 	> 
>   >métodos
> 	> 
>   >* `insertAdjacentElement(position, el)`: para insertar elementos
>   > * `insertAdjacentHTML(position, html)`: para insertar html
>   > *  `insertAdjacentText(position, text)`: para insertar texto 
> 	> 
>   >ejercicios 
> 	> 
>   >```javascript
>   > // creamos un nuevo elemento
>   > const newElement = document.createElement('h2')
>   > // le llenamos de contenido
>   > newElement.textContent = 'Este es un nuevo elemento'
>   > // llamamos al padre
>   > const parent = document.getElementById("parent")
>   > 
>   > // utilizarmos todas las posiciones 
>   > // insertamos el nuevo elemento que seria como su hermano anterior
>   > parent.insertAdjacentElement('beforebegin', newElement)
>   > // este seria como su primer hijo
>   > parent.insertAdjacentElement('afterbegin', newElement)
>   > // este seria como su ultimo hijo
>   > parent.insertAdjacentElement('beforeend', newElement)
>   > // este seria como su hermano siguiente
>   > parent.insertAdjacentElement('afterend', newElement)
>   > 
>   > 
>   > // para insertar un texto 
>   > parent.insertAdjacentText('afterend', 'hola mundo ')
>   > // para insertar un html 
>   > parent.insertAdjacentHTML('afterend', `<h1>Hola mundo</div>`)
>   > ```
> 	> 
>   
>   * `replaceChild(newChild,oldChild)` : nos remplaza un hijo 
> 
>  >```javascript
>   >const newElement = document.createElement('h2')
>   >newElement.textContent = 'Este es un nuevo elemento'
>   >const parent = document.getElementById("parent")
>   >
>   >parent.replaceChild(newElement, parent.children[0])
>   >```
> 
>* Métodos tipos jQuery o jQuery like
> 
>  >
>   >
>   >estos son métodos que trabajan igual que `insertAdjacent` 
>   >
>   >* `before()`: hermano anterior
>   >* `after()`:  hermano siguiente
>   >* `prepend()`: primer hijo
>   >* `append()`: ultimo hijo
>   >* `child.replaceWith(newChild)`: esto viene del hijo tienes que encontrar al hijo y remplazar con un nuevo hijo  
>   >* ejercicios para estos nuevos métodos
>   >
>   >```javascript
>   >const newElement = document.createElement('h2')
>   >newElement.textContent = 'Este es un nuevo elemento'
>   >const parent = document.getElementById("parent")
>   >const title = document.querySelector('h2')
>   >
>   >// parent.before(newElement)
>   >// parent.after(newElement)
>   >parent.prepend(newElement)
>   >
>   >// para replaceWith
>   >parent.children[0].replaceWith(newElement)  
>   >```
> 
>* Clonar y eliminar elementos
> 
>  > * `cloneNode()`: para clonar elementos  o  sacar una copia de elementos 
>   > * `remove()`: para remover eliminar elementos
>   >
>   > ```javascript
>   > // ejercicio de remover()
>   > $0.remove()
>   > // ejercicio de cloneNode()
>   > const newElemen = $0.cloneNode(true) // estamos clonando un elemento y le decimos  true por que queremos que nos traiga sus hijo y si le pondriamos false esto ya no traeria  a sus hijos 
>   > $0.append(newElemen) // de esta forma lo agregamos en cualquier lugar 
>   > ```
>   >
>   > ​	
> 
>* Crear elementos 
> 
>  >* `createElement()`: para crear elementos 
>   >* `createElementFragment()`: nos permite guardar elementos en memoria, guardar estructuras html antes de pintarlo eso mejora muchísimo el rendimiento  
>   >
>   >```javascript
>   >
>   >//este ejercicio es más para cuando tienes que crear elementos recorriendo un lista o objeto 
>   >
>   >const alumnos = ['jerry', 'juan', 'pedro', 'maria']
>   >const list = document.createElement('ul'),
>   >  alumContainer = document.getElementById('alumList'),
>   >  alumFragment = document.createDocumentFragment()
>   >// agregamos el nuevo elemento 
>   >alumContainer.appendChild(list)
>   >// creamos un nuevo elemento por cada indice del arreglo  y lo guardamos el createDocumentFragment
>   >for (let alum of alumnos) {
>   >  const li = document.createElement('li')
>   >  alumFragment.appendChild(li)
>   >  li.textContent = alum
>   >}
>   >// y al final esto lo agregamos donde querramos 
>   >list.appendChild(alumFragment)
>   >```
> 
>* Template HTML
> 
>  >
>   >
>   >`<template>`: nos permite crear plantillas para luego utilizarlas 
>   >
>   >y con esto lo que haríamos el llamar al template  y obtener las posiciones y luego llenarlas desde javascript ejemplo 
>   >
>   >```html
>   >
>   >    <template id="template">
>   >        <h2></h2>
>   >        <p></p>
>   >    </template>
>   >
>   >    <div id="container">
>   >
>   >    </div>
>   >```
>   >
>   >```javascript
>   >const template = document.getElementById('template'),
>   >  myNewTemplate = template.content.cloneNode(true)
>   >
>   >myNewTemplate.querySelector('h2').textContent = 'Titulo principal'
>   >myNewTemplate.querySelector('p').textContent = 'Titulo principal y esto es la descripcion'
>   >
>   >document.getElementById('container').appendChild(myNewTemplate)
>   >```
>   >
>   >

### CSSOM

> ​	es el modelo de objetos de css
>
> * `sytle`: para manipulas los estilos 
>
>   >
>   >
>   >```javascript
>   >const h1 = document.querySelector('h1'),
>   >  p = document.querySelector('p')
>   >
>   >h1.style.backgroundColor = 'blue'
>   >```
>   >
>   >
>
> * `matchMedia()`: nos permite evaluar  breakponit de css
>
>   >
>   >
>   >```javascript
>   >const h1 = document.querySelector('h1'),
>   >  p = document.querySelector('p')
>   >
>   >
>   >h1.style.backgroundColor = 'blue'
>   >const query = () => {
>   >  const mediaBp = matchMedia('(min-width: 640px)')
>   >  if (mediaBp.matches) {
>   >    document.body.style.backgroundColor = "yellow";
>   >  } else {
>   >    document.body.style.backgroundColor = "red";
>   >
>   >  }
>   >}
>   >
>   >
>   >addEventListener('resize', query)
>   >addEventListener('DOMContentLoaded', query)
>   >```
>
> * `getComputedStyle(element)`:  nos trae los estilos del documento 
>
>   > ```javascript
>   > console.log(getComputedStyle(h1).color)
>   > ```
>   >
>   > 
>
> * `getBoundingClientRect()`: es un método que nos devuelve las coordenadas y posición de un elemento 
>
>   > ```javascript
>   > 
>   > //comando
>   > $0.getBoundingClientRect()
>   > // respuesta 
>   > bottom: 59.43333435058594
>   > height: 38
>   > left: 8
>   > right: 1358
>   > top: 21.433334350585938
>   > width: 1350
>   > x: 8
>   > y: 21.433334350585938
>   > ```
>   >
>   > 



## El navegador

### Objeto window	

> Es el objeto window es el mas alto del nivel de javascript en el navegador 
>
> cada vez que nosotros utilizamos métodos para mostrar algo en el navegador como por ejemplo y `console.log() `o por ejemplo un `alert()` todos estos métodos descienden del objeto Window, por eso no es necesario llamar al objeto window  

### Objeto Location

> te devuelve la información sobre la url  y todas estas propiedades son de escritura y lectura 
>
> * Propiedades 
>
>   * `href`: url actual, se puede cambiar para cambiar la pagina actual 
>
>     > ```javascript
>     > location.href
>     > // esto devuelve 
>     > "https://ed.team/cursos"
>     > ```
>     >
>     > 
>
>   * `host`: para obtener el dominio y el puerto `location.host` y esto devuelve `"ed.team"`
>
>   * `hostName`: nos devuelve solo el nombre del dominio 
>
>   * `port`: nos devuelve el puerto `location.port `
>
>   * `protocol` nos devuelve http o https `location.protocol`
>
>   * `origin`: protocolo + dominio `location.origin`
>
>   * `hash` #
>
>   * `pathname`: ruta interna luego del dominio `location.pathname` seria igual a `"/cursos"` ruta interna
>
> * Métodos
>
>   * `reload()`: recarga la página `location.reload()`
>   * `assing(url)`: es como rescribir el href `location.assing(ed.team/cursos)`
>   * `replace(url)`: cambia la pagina actual sin guardar en el historial 
>
> * History
>
>   * `back()`: te manda atrás `history.back()`
>   * `forward()`: te manda hacia adelante `history.forward()`
>   * `go(positionactual)` te permite navegar de la posición actual hacia adelante o hacia atrás  indicándole con -2 o 2 para navegar el menos es para atrás y el positivo para adelante `history.go(-2)`

### Objeto navigator 

* Detectar navegador  : no es buena idea 
* Detectar características : 
  * CSS : para esto tenemos @suports
  * JavaScript : tenemos el operador in `'Promise' in window`
  * Modernizr : es un librería para preguntar si un navegador le falta características 





### Tymer

> * `setTimeout(callback, ms)`: ejecuta lo que esta en el callback después de cierta cantidad de tiempo de milisegundos 
>
>   >
>   >
>   >```javascript
>   >setTimeout(() => {
>   >  alert('Hola mundo')
>   >}, 2000)
>   >```
>   >
>   >
>
> * `setInterval(callback, ms)`: ejecuta una función varias veces con un intervalo indicado en el segundo parámetro que son los segundos 
>
>   > ```javascript
>   > let contador = 0
>   > const saludarMuchasVeces = setInterval(() => {
>   >   contador++
>   >   if (contador > 1) {
>   >     console.log(`hola ${contador} vez`);
>   >   } else {
>   >     console.log(`Hola ${contador} veces `)
>   >   }
>   >   if (contador == 5) {
>   >     clearInterval(saludarMuchasVeces) // con esta propiedad podemos romper el flujo  del setInterval 
>   >   }
>   > }, 1000)
>   > // otro ejemplo de reloj con setInterval 
>   > 
>   > const hour = document.getElementById('hour')
>   > 
>   > let contador = 0
>   > const saludarMuchasVeces = setInterval(() => {
>   >   contador++
>   >   let date = new Date()
>   >   hour.value = date.toLocaleTimeString()
>   >   // console.log()
>   >   if (contador == 5) {
>   >     clearInterval(saludarMuchasVeces)
>   >   }
>   > }, 1000)
>   > 
>   > ```



### Date

> * Instanciar
>
>   * `new Date()`: 
>
>     > ```javascript
>     > const now = new Date()
>     > console.log(now)
>     > ```
>
>   * `new Date(year, mon, day)`
>
>   * `new Date(year, mon, day, hour, minutes, seconds)`: los meses son de 0 a 11
>
>   * `new Date(string)`
>
> * Métodos
>
>   * `getDay()`: nos devuelve de 1 a 7
>   * `getFullYear()`:  Nos devuelve el año 
>   * `getMinutes()`: nos devuelve el minuto
>   * `getSeconds()`: nos devuelve los segundos
>   * `getDate()`  : El número del día del mes 1 al 30 o 31
>   * `getMonth()`: El mes
>   * `getTime()`:  nos devuelve  milisegundos desde 1 de enero 1970
>   * `getTimezoneOffset()`: