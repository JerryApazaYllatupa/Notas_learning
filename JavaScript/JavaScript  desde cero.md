# JavaScript  desde cero

[TOC]



## características 

- Dinámicamente tipado
- Interpretado
  	* navegador
   * Servidor (Node.js)

* Prototipado 
* Multiparadigma 

 ## Variables y constantes 

las variables son un espacio reservado en memoria,

### let 

> Cuando se define con la palabra `let ` los datos de esta variable solo van existir en el bloque de código donde se a declarado, ósea que solo va ser accesible en el Scope 

### var

> Cuando se define con la  palabra `var` los datos podrán ser accesibles desde fuera de Scope 

### const

> Variables definidas con `const` se comporta como las variables definidas con `let` solo que estas variables no se puede cambiar sus valores

## Sintaxis 

### comentarios

> ​	comentario de línea `//Comentario` y `/*Comentario */`

### punto y coma 

> los puntos y comas son opcionales siempre en cuando sepas manejar el código  de javascript

### case sensitiva

> ​	Diferencia las mayúsculas  y minúsculas 

### expresiones 

> las expresiones son variables de códigos declaradas como por ejemplo `let nombre = 'nombre'` este línea es  una expresión 

## Tipo de datos 

### Primitivos

* Números : 1 , 3 ,5

* String 

  * > En JavaScript ` '', "", `` ` los reconoce como string 	

* Bolean : `true` o `false`

* Undefined : si existe una variable pero no tiene valor

  * por ejemplo `let nombre` solo esta declarada pero no tiene valor 

* Null :  que no existe

### Compuestos

* Array :`let frutras =['naranja','pera', 'manzana','plátano']` 
* Object : `let persona ={ nombre:"nombre", apellido:"apellido" `

## Como funciona javascript

* en javascript podemos cambiar el tipo de dato asignado a una variable como asi

  > `let nuermo = 1` y luego podemos decirle que sea un boolean `numero = true`

* Type Coerción :  Es transformar implícitamente el tipo de dato como así

  ```javascript
  let letra = "2"
  let numero = 1
  let suma = letra + numero //y esto daria una suma de 3 por que lo que hace javascipt es que transforma el código implícitamente
  ```


* Asignación o por referencia 

  * primitivos : por valor 

  * compuestos : por referencia 

  * asignación 

    > esto de la variables por asignación son cuando le asignamos a una variable otra variable por valor 
    >
    > `let a = 3`  y mas adelante creamos otra variable  `let b = a`
    >
    > y cuando cambiamos  el valor de la variable b esto no afecta al la variable b

  * referencia 

    > como sabemos las variables compuestas son los arreglos y objetos por lo tanto cuando vemos esto de un variable esta cogiendo un arreglo para sus datos esto lo que hace cuando modificamos un valor en la variable b seria modificar al  la variable y por eso se dice por referencia que si se puede modificar el valor de donde esta cogiendo la referencia 
	

### Operadores 

#### asignación 

* =
* +=
* -=
* *=
* /=

#### comparación

* ==
* ===
* !=
* !==
* '>'
* <
* '>='
* <=

#### unarios

* typeof
* !

#### aritméticos 

* +
* -
* *
* /
* %
* ++
* '- -'

#### ternario 

* Expresión ? si es verdadero : si es falso `let validarEdad = edad >= 18 ?'eres mayor':'eres menor'`

#### corto circuito 

* ||

* && 

### Números 

* .tofixed() : especifica el número de decimales `let numero = 10.00000000` y con tofixed() seria  `numero=10.00`

* parseInt(string,10) : convierte un texto a número 

* parseFloat(string): Para convertir un texto que tenga decimales a números decimales 

* Math.floor() = >  redondea un número hacia abajo

* Math.ceil() = > redondea siempre hacia arriba

* Math.round() = >redondea a los dos lados

* Math.random() = > devuelve un número entre 0 y 1

### String

#### Propiedades 

* `.length` : nos devuelve la cantidad de un texto

#### Métodos

* sin parámetros
  *  `.trim()` : quita los espacios en blanco 
  * `.toUpperCase()` : convierte todo a mayúsculas
  * `.toLowerCase()` : convierte todo a minúsculas 
* Encontrar caracteres 
  * indexOf(string[i]) : para encontrar caracteres y si no encuentra nos devuelve -1 ejemplo `hola amigos .indexOf('0', 2)` les indico que palabra y cual de las posiciones 
  * `lastIndexOf(string[i])`: para que encuentre el final 
  * `includes(string[,i])`: pregunta si el texto contiene el carácter
  * `startsWith(string[,i])` : para preguntar si inicia con 
  * `endsWith(string[,i]) `: para preguntar si termina con 



#### Manipular String 

* `.replace('original','reemplazar')`: para reemplazar contenido de un texto ` 'Hola mundo'.replace('Hola','Buen dia')`
* `.split('separador')` : lo que hace split es que crea un nuevo array con los parámetros que le mandamos `'Hola mundo'.split(' ')` y tendríamos un array  de dos índices de hola y mundo
* `['indice']`: para obtener el carácter de un texto `'jerry'[1]` = `e`
* `.substring(star[,end])`: lo que hace substring es traernos el contenido de un texto desde una posición y hasta una posición pero el end es opcional `'Hola mundo'.substring(4)` = ` " mundo"` tal cual con el espacio 
* `.substr(indice,cantidad)`: para obtener carácter desde una cierta posición hasta cuantos caracteres `'Hola mundo'.substr(2,5)`  = ` "la mu"` si quieres los 4 últimos caracteres solo se ingresa con numero negativos `-4`

## Condicionales

### if

* en un línea

  > ```javascript
  > if (condicion) // hacer algo	 
  > ```

* con bloque 

  > ```javascript
  > if (condicion) {
  >   // hacer algo
  > }
  > ```

* con más condicionales 

  > ```javascript
  > if (condicion1) {
  >   // hacer algo
  > } else if (condicion2) {
  >   // hacer otra cosa
  > } else if (condicion3) {
  >   // hacer otra cosa
  > } else {
  >   // si nada se cumple hacer esta cosa
  > }
  > ```

### condiciones múltiples 

* && (y)
* || (o)

### truthy and falsy values 

* falsy
  * 0
  * ""
  * NaN
  * undefined
  * null
* truthy
  * string no vacío
  * numero diferente de cero
  * arrays
  * objects 

### switch

son para validar varias opciones 

```javascript
let answer = prompt("Esgo un número de 1 a 5");
switch (answer){
  case '1': alert("eres tímido")
    break
  case '2': alert("eres extrovertido")
    break
  case '3': alert("eres muy feliz")
    break
  default:alert("te pasaste")
}

```

## Ciclos

### for

```javascript
for (let i = 0; i < 10; i++) {
  // hacer algo en cada iteración
}
```

### while

```javascript
// repetir mientras la condición se cumpla
while (condicion) {
  // hacer algo
}
//ejemplo
a= 1;
while (a <=10){
    console.log(a)
	a = a+1
}
	

```

### do while

```javascript
//repetir mientras que la condición se cumpla la diferencia es que el mientras que siempre va recorrer una vez el ciclo
do {
  // hacer algo
} while (condicion)
    
//ejemplo
let password="jerry";
let pass;
do{
  pass = prompt("ingresa la contraseña")
}while(pass !== password)

```

### romper y saltar un for

```javascript
//break
// el break lo que haces que rompe el ciclo y cancela todo
for(let i =0; i<10; i++){
  if(i % 7===0) break 
  console.log(i)
}

//continue
//continue lo que hace es saltar la línea de código que estas validando
for(let i =0; i<10; i++){
  if(i % 7===0) coninue
  console.log(i)
}


```

## Funciones 

### ¿Que es una función?

> Las funciones son bloques de códigos reutilizable en el que hay un conjunto de instrucciones

### Formas de declarar una función 

#### Declaración

```javascript
function nombreFuncion(parametros) {
  // instrucciones de la funcion
  return valor
}
```



#### Expresión 

* Con función de uso

  > ```javascript
  > var nombreFuncion = function() {
  >   // instrucciones de la función
  >   return valor
  > }
  > ```

* funciones de flecha (recomendado desde ES6)

  > ```javascript
  > const nombreFuncion = (parametros) => {
  >   // instrucciones de la funcion
  >   return valor
  > }
  > //si la función de flecha retorna directamente un valor sin instrucciones a sintaxis se reduce 
  > const nombreFuncion = (parametros) => valor
  > const sumar = (a,b) => a + b;
  > ```
  >
  > 

* Parámetros y argumentos 

  > 1.  **Parámetros** : son valores locales que se definen en la declaración de la función, se pueden asignar valores por defecto a los parámetros 
  >
  > 2. **Argumentos** : Son valores asignados a los parámetros al ejecutar la función,
  >
  >    1. Si hay más argumentos que parámetros, los adicionales se ignoran
  >    2. Si hay menos argumentos que parámetros
  >       * los faltantes son undefined
  >       * A menos que tengan un valor por defecto
  >
  > 3. parámetros rest (spread operator)
  >
  >      son parámetros res son 3 puntos para indicarle múltiples parámetros
  >
  >    ```javascript
  >    funcion(...arguments)
  >    const sumarTodos =(...numeros) =>{
  >      
  >      let resultado = 0;
  >      for (let i =0; i< numeros.length; i++){
  >        resultado += numeros[i];
  >      }
  >      return resultado
  >    }
  >    console.log(sumarTodos(1,2,3,4,5,6,7))
  >    // este seria un claro ejemplo de parámetros rest
  >    ```
  >
  >    

### Las funciones son ciudadanos de primera clase

#### pueden ser almacenadas  en variables y constantes 

> `unción por expresión
> const c = console.log`

#### Pueden ser pasadas como argumento de otra función 

>callbacks
>
>```javascript
>const multiplicar = (a,b) => a+b
>let edad = multiplicar(multiplicar(2,4),2)
>console.log(edad)
>// le estamos pasando una función como argumento a eso se les llama callbacks
>```
>
>

#### Pueden ser retornadas por otra función 

> closures
>
> ```javascript
> //funciones por expresion
> function sumar(x){
>   return function(y){
>     return x+y;
>   }
> }
> // para ejecutar esa funcion seria de esta forma
> console.log(sumar(5)(2))
> //funcion de flecha
> const sumar = x => y =>x+y
> 
> ```

#### Funciones de múltiples funciones 

```javascript
const c = console.log
const sumar = x => y =>x+y
c(sumar(2)(4))

const doSomething = x => y => x * y

const a = doSomething(2)(2)
const b = doSomething(3)
c(doSomething(a)(b(3)));

```

### Tipos de funciones 

#### Funciones puras

> No causa un efecto secundario, y siempre devuelve los mismos valores para los mismos parámetros.
>
> ```javascript
> const c = console.log
> let a = "hola";
> const saludo = (saludo,persona) => `${saludo} ${persona}`
> c(saludo(a, "jerry"))
> 
> ```
>
> 

#### Funciones no puras 

> estas funciones son funciones que cambian datos a variables externas
>
> ```javascript
> const c = console.log
> let a = "hola";
> const saludo = persona => {
>   a = a + " "+ persona
>   return a
> }
> c(saludo("jerry"))
> c(a)
> 
> ```

#### Funciones auto invocadas

> son funciones que no tienen nombre un ejemplo en función de callbacks
>
> ```javascript
> setTimeout(()=>{
>   alert("alert")
> }, 3000)
> 
> ```



### Scope

> Es el contexto en el que  una variable existe 

#### This

> representa al objeto de cual se ejecuta la función
>
> ```javascript
> let user = {
>    nombre:"jerry",
>    edad: 20,
>    getEdad(){
>      console.log(this.edad)
>    }
>  }
>  user.getEdad()
> 
> ```
>
> 

#### Closures

> las arrow functions permiten acceder al this superior  dentro de una closure 
>
> ```javascript
> function aumentar(){
>     let numero = 0;
>     return function(){
>         numero++;
>         console.log(numero)
>     }
> }
> 
> // lo ejecutamos de esta forma 
> const incrementar = aumentar()
> incrementar()
> incrementar()
> incrementar()
> incrementar()
> incrementar()
> // " todo esto devolveria la suma en cada iteración "
> ```
>
> 

## Array

### concepto 

> 1. Lista separada por comas y encerrados entre corchetes `let array=['hola', [1,2,3,4,5,6],1 , "jerry"]`
> 2. acceder `array[0]`
> 3. Desestructuración de arrays
>
> > ```javascript
> > let arr5 =['hola','amigos', 'de', 'eteam']
> > let [s1,s2,s3,s4] = arr5
> > s1
> > "hola"
> > 
> > ```
>
> 4. Propiedades `length` para mostrar el tamaño del array `array.length`

### métodos 

> cuando vemos .y algo todos estos son métodos 
>
> * `.push(value)` : agrega value como nuevo elemento al final el array
>   retorna el nuevo length
>
> * `.pop()` : quita y retorna el último elemento del array
>
> * `.unshift(value)` : agrega value como nuevo elemento al inicio del array
>   retorna el nuevo length
>
> * `.shift()`: elimina y retorna el primer valor
>
> * `.splice(startIndex,quantity,value1,value2,value3)` ejemplo  
>
>   > **startIndex:** índice en el que se insertarán elementos
>   > si es negativo cuenta desde el final
>   >
>   > **quantity**: 
>   >
>   > Cantidad de elementos que serán remplazados (0 si ninguno se remplazará)
>   >
>   > **values**: Valores que serán añadidos al array 
>   >
>   > `pais.splice(2,0,'Chile','Ecuador')` : para gregar
>   >
>   > `pais.splice(1,1):`   : seria para eliminar
>   >
>   > `let paises = pais.slice(2,4):` para crear un nuevo array con las posiciones de otro array
>
> * `.slice(star[,end])`
>
> * `.reverse()`: para poner al rebes el contenido 
>
>   > ```javascript
>   > let num = [1,4,5,3,2,6,7,0]
>   > num.reverse()
>   > Array(8) [ 0, 7, 6, 2, 3, 5, 4, 1 ]
>   > 
>   > ```
>
> * `.sort()` : Para ordenar texto de A a Z
>
> * `.sort((a,b) => a-b)`: Para ordenar números 
>
> * `.join()`: convierte en un array a un string ` let arr2 = nombre.join("-")`
>
> * `.concat()` : recibe como parámetro un array o un lista de valores separadas por comas estos valores no modifican la variable original 
> * `.indexOf('value')` : Para encontrar datos de un array  `array.indexOf("nombre")` esto devuelve el índice del array  del primer dato que encuentra 
> * `.find(callbacks)`:  esto nos devuelve el valor del índice  que cumpla la condición ` numbers.find( number => number > 100) `
> * `.findIndex(callback)`: esto nos devuelve el primer condición  y esto nos devolverá el índice 

### Spread operator 

> lo que nos da spread operator es para eliminar elementos duplicados en un array
>
> * `[...new Set(numbers)]`: para eliminar elementos duplicados de un array
> * `Math.min(...numbers3)`: para encontrar el número mínimo de un array y esto solo funciona con el spread operator 
> * `Math.max(...numbers3)` : e igual para encontrar el número máximo de un array

### Recorrer un array

> * `for()` : `for(let i = 0; i< arr.length; i++){console.log(i)}`
>
> * for of : `for(let element of arr){console.log(element); }`
>
> * `.forEach(callback)`:
>
>   > ```javascript
>   > nombre.forEach((element,index)=>{
>   > console.log(element, index); 
>   > })
>   > // respuesta de esto
>   > Hola 0 
>   > mundo 1
>   > jerry 2 
>   > Hola 3
>   > 
>   > ```
>
> * `.some(callbakc)`: esto lo que hace es que recorre un arreglo y  pregunta si el elemento tiene este índice y esto devuelve true si es que la condición se cumple `saludo.some(el => el == 'Hola')`
>
> * `.every(callback)`: lo que hace esto es que si todo el arreglo tiene la validación y si esto se cumple entonces esto devolverá un true y no se cumple esto devolverá un false `saludo.every(el => el == 'Hola')`
>
> * `.map(callback)`: lo que hace este método es que crea un nuevo elemento  y esta se aplica a cada índice del array y te crea un nuevo array  un ejemplo 
>
>   > ```javascript
>   > let number = [ 2, 4, 8]
>   > number.map(el => el * el)
>   > number = [ 4, 16, 64 ]
>   > ```
>
> * `.filter(callback)` : Filtra los elementos que cumplan con la condición del callback
>
>   >```javascript
>   >let otherArray = number.filter(el => el > 5) // y esto nos filtraria todo los elemento mayores de 5
>   >```
>
>   `.reduce(callback)` : 
>
>   > ```javascript
>   > let sum = number.reduce((a,b) => a + b )// estomos sumando todo a un solo valor
>   > ```
>
>   

## Objetos

> ​	Es una estructura de datos los objetos tienen propiedad y valor  y estos valores pueden ser cualquier tipo de dato 
>
> ```javascript
> {
>   propiedad: valor,
>   propiedad2: valor2,
>   propiedad3: valor3,
>   metodo() {
>     // codigo del metodo
>   }
> }
> ```

### Acceder a un objeto

para acceder a estos propiedades tenemos dos formas

> ​	`usuario["nombre"] `o `usuario.nombre` 

* igualar a variables

  > ```javascript
  >  let a= 'Hola'
  >  let b = 'Mundo'
  >  let ar = {[a]: 'saludo'}
  >  Object { Hola: "saludo" }
  > 
  > // y tambien tenemos de esta forma
  > 
  > let myObjet = {a,b}
  > Object { a: "Hola", b: "Mundo" }
  > 
  > ```

### Eliminar propiedades de un objeto 

> `delete usuario.nombre`

### Agregar propiedades

> `usuario.apellido = "Apaza"`
>
> `usuario[“apellido”]= "Apaza"`

Prototype

> ` String.prototype`,`Number.prototype` etc
>
> Todo los datos vienen de un objeto  Javascript tiene objetos y todo esos objetos vienen con letra mayúscula al principio  y los prototipos son como moldes del cual se crea un objeto 
>
> `Object.getPrototypeof('string',1,boolean,object)` esto es para acceder al objeto de javascript y hay veremos todo los métodos que existen para cada tipo  y algo muy importante que también podemos crear nuestros métodos utilizando el modelo de javascript  



### Operadores

* in

> Para acceder a las propiedades de un objeto y devuelve true si es que existe la propiedad 
>
> ```javascript
> let persona ={
>   nombre:"jerry",
>   edad: 20,
>   saludar(){
>     console.log(`hola ${this.nombre}`)
>   }
> }
> // y utilizar el operador in
>  'nombre' in persona
>  true
> ```

* for in

  > 
  >
  > ```javascript
  > //esto nos esta recomendado para recorrer un objeto por que trae los métodos de un objeto
  > for(let property in usuario) {
  >     console.log(property)
  > } 
  > // //Esta opcion seria lo correcto para imprimir datos de un objeto  y no nos traiga todos sus métodos 
  > for(let property in usuario) { 
  >     if(usuario.hasOwnProperty(property)){
  >         console.log(property) } 
  > }
  > 
  > ```
  >
  > 



### Mutabilidad

> en la mutabilidad tenemos que conocer estos conceptos 
>
>  todos los objetos asignados por valor en general son variables primitivas y todos lo variables asignadas por referencia son objetos 
>
> La diferencia entre estas dos conceptos es que cuando agregamos nuevos datos a una variable en asignados por valor este no modifica a la primera variable pero cuando es por referencia este si cambia al primer objeto o array 
>
> * `Object.assign({},object)`  Y con esto le decimos que nos saque una copia del objeto original y nos guarde en otra variable entonces cuando queramos agregar nuevos datos al nuevo objeto e está no modificara al objeto original  por el tema de mutabilidad `let usuario2 = Object.assign({},usuario)`

### Recorrer un objeto

* for in

  > Devuelve los nombres de las propiedades de un objeto. Pero devuelve también las propiedades en la cadena de prototipos. 
  >
  > ```javascript
  > for(let property in usuario) {
  >     console.log(property)
  > } 
  > ```

* for of

  > No recorre un objeto, porque un objeto no tiene índices (no es iterable). 
  >
  >  

* `Object.entries(object)`

  > Devuelve como arrays cada una de las entradas del objeto (propiedad,valor) 

* `Object.keys(objeto)`

  > Devuelve un object (array like) con todas las propiedades 

* `Object.values(objeto)`

  >Obtiene los valores de un objeto 

 