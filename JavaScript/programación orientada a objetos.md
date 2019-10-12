#  Programación orientada a objetos 

## Conceptos generales 

### ¿Que es la programación orientada a objetos?

> * Es un paradigma de programación 
> * Es el mas usado hoy en día 
> * Aplicable a muchísimos lenguajes

Paradigma 

> * Es una forma de pensar o actuar, una filosofía 
> * Una serie de patrones o modelos a seguir
> * Un planeamiento común 

### Que es un objeto 

* todo es un objeto 

* Es una simple abstracción del mundo real 

* Es representación del estado y las acciones que puede realizar algo /alguien 

  ### Características de un objeto

* Atributos : los atributos de un objeto son como un nombre, edad, correo, teléfono 

  > 1. Características 
  > 2. se refieren al estado actual 
  > 3. son modificables y accesibles 

* Métodos : son las acciones 

  * son las acciones de un objeto 
  * Se refieren  al estado actual 
  * Son modificables y accesibles 

* Objetos literales y prototipos 

  > la sintaxis es 
  >
  > ```javascript
  > const nombreObject =  {
  >     atributo = valor,
  >     atributo = valor,
  >     metodo() =>{}
  > }
  > ```
  >
  > 

* Prototipos 

  *  Es la base de toda la programación en JS
  * Ya que todo es un objeto a la vez todo debe partir de un prototipo 

* This 

  * A partir de ES6 el alcance del this se limita al objeto declarado
  * De un forma global, el this sería igual a window 

### Declaración de objetos

> ​	 
>
> ```javascript
> const cliente = {
>   nombre: 'jerry',
>   apellido: 'Apaza',
>   email: 'jerryapaza8@gmail.com',
>   pass: 'Abcd1234'
> }
> console.log(cliente)
> let = name = "nombre"
> const tabla = {
>   [`${name}`]= 'Jerry'
> }
> // acceder a los objetos 
> cliente.nombre
> cliente["nombre"]
> ```
>
> 

## Clases

> las clases son como objeto que comparten los mismos atributos
>
> * declaración  de clases
>
>   >
>   >
>   >```javascript
>   >class Usuario {
>   >    // para inicializar las atributos 
>   >    constructor(nombre, apellido, email, edad) {
>   >        this.nombre = nombre
>   >        this.apellido = apellido
>   >        this.email = email
>   >        this.edad = edad
>   >    }
>   >    // este tambien tiene métodos
>   >    saludar() {
>   >        return console.log(`Mi nombre es : ${this.nombre}`)
>   >    }
>   >    // para cambiar datos de un objeto
>   >    cambiarDatos(nuevodato) {
>   >        this.nombre = nuevodato
>   >    }
>   >}
>   >```
>   >
>   >* herencia  : heredar los atributos y los métodos de una clase padre  y esto funciona con extends 
>   >
>   >```javascript
>   >class Profesor extends Usuario {
>   >    constructor(nombre, apellido, email, edad, experiencia, lenguaje) {
>   >        super(nombre, apellido, email, edad)
>   >        this.experiencia = experiencia
>   >        this.lenguaje = lenguaje
>   >    }
>   >}
>   >```
>   >
>   >Ejercicios sobre clases
>   >
>   >```javascript
>   >class Forma {
>   >    constructor(ancho, alto, color) {
>   >        this.ancho = ancho
>   >        this.alto = alto
>   >        this.color = color
>   >    }
>   >    dibujar() {
>   >        return document.body.innerHTML = `
>   >        <div
>   >        style="
>   >        width: ${this.ancho}px; 
>   >        height: ${this.alto}px; 
>   >        background-color: ${this.color};"
>   >        >
>   >        </div>
>   >        `
>   >    }
>   >}
>   >
>   >class Circulo extends Forma {
>   >    constructor(ancho, color) {
>   >        super(ancho, ancho, color)
>   >    }
>   >}
>   >
>   >let forma1 = new Forma(40, 40, 'blue')
>   >let circulo = new Circulo(40, 'red')
>   >```
>   >
>   >