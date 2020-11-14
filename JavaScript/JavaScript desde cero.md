[TOC]

# JavaScript desde cero



## Conocimientos para entender JavaScript

Seguramente que ya estas iniciando el tema de desarrollo web, y es que por esto nace este lenguaje  y los conocimientos que yo creo que ya deberías saber para este documento son:

1. HTML 

2. CSS

3. Fundamentos de programación  

   

## Introducción 

En este documento iremos aprendiendo sobre el lenguaje, con ejemplos y un poco de teoría, no soy quien para imponerlas  las bases de JavaScript, es solo para que puedan leer, practicar y tener una referencia cuando algo no se acuerden como se hacia, mi recomendación si quieren profundizar mas sobre el tema, pueden investigar y leer

## Pequeña Historia de JavaScript 

JavaScript fue creada en 1995 por `Brendan Eich` ingeniero de `Netscape` y fue publicado con  `Netscape2`   a principios de 1996. inicialmente se iba a llamar LiveScript, pero fue renombrada en una errónea decisión de marketing para tratar de aprovechar  la popularidad del lenguaje de Java, a pesar que ambos lenguajes tienen muy poco en común. Esto a sido el motivo de confusión que a alcanzado hasta nuestros días, si desean saber mas sobre la historia puede buscar y leer nos centraremos más en el lenguaje 

## Información sobre JavaScript

JavaScript es un lenguaje dinámico, JavaScript tiene la fama de ser un lenguaje de programación más incomprendido. A diferencia de la mayoría de los lenguajes de programación, JavaScript no tiene un concepto de entrada y salida. Esta diseñada para funcionar como un lenguaje de script dentro de un entorno y depende de los mecanismos de este para la comunicación con el mundo exterior. El entorno mas común es el navegador web, también podemos encontrar en lado del servidor como `Node js`  y así en  muchos otras tecnologías,no los menciono para no desviarnos mucho del tema, ya ustedes pueden ir investigando a fondo.

## Variables 

Cuando empiecen con JavaScript, van a escuchar este termino "dinámicamente tipado y estrictamente tipado", y JavaScript es dinamicamente tipado, Por que cuando se habla de variables, estas pueden cambiar el tipo de dato posteriormente en el código, pero también hay lenguajes que no se pueden cambiar el tipo de dato de la variable y a estas se les dice estrictamente tipado

En JavaScript podemos declarar variables con 3 palabras reservadas y estas tiene su diferencia 

- `var`:  Cuando se declara variables con esta palabra reservada, los datos que va almacenar esta variable pueden ser accedidos de cualquier parte archivo 
- `let`: Cuando se declara variable con esta palabra, los datos que va almacenar o la variable solo puede ser llamada desde dentro del scope, ¿que es el scope?, el scope puede definirse el alcance que puede tener una variable, y este seria el inicio de llaves y el fin `{ }`, solo en este rango se puede  utilizar esa variable 
- `const`: Las variables declaradas con esta palabra, son iguales con la palabra `let`, con la diferencia de que estas no pueden modificarse sus datos a lo largo del código 

```javascript
var saludo = "Hola mundo"

{
    let  nombre = "JUAN"
}

{
    const Edad = 20
}
```



## Tipos de datos 

La ultima definición de estándar de de ECMAScript define 7 tipos de datos 

- Tipos de datos primitivos 
  - `Boolean` 
  - `Null`
  - `Undefined`
  - `Number`
  - `String`
  - `Symbol`
-  Objectos
  - `Functions`
  - `Array`
  - `Date`
  - `RegExp`



### Datos primitivos 

- `Boolean`:  Boolean representa una entidad lógica y este almacena dos valores  "True" o "False"

  ```javascript
  let soltero = true
  let casado = false
  ```

  

- `Null`: Variables asignados con este valor es nulo es decir nada 

  

- `Undefined`: Este valor representa que existe pero no tiene valor y generalmente se encuentra cuando se declara una variable pero no se le asigna ningún valor 

  ```javascript
  let nombre 
  
  console.log(nombre) 	//undefined
  
  ```

- `Number`: Este almacena todo tipo de número y todos los tipos numéricos de otros lenguajes como Integers, Floats, Doubles, o Bigamias. 

  ```javascript}
  let n1 = 2
  let n2 = 3.3
  let n3 = .49
  ```

- `String`: Este es para representar todos los datos textuales o cadena de caracteres, y este se puede representar de 3 maneras. Cada carácter del texto ocupa un número iniciando del cero  hasta la longitud del texto 

  ```javascript
  //Comillas dobles
  let texto = " texto "
  
  //Commilas simples
  let texto1 = ' texto '
  
  //Template string o backtiks
  //esto nos sirve para concatenar variables en un texto
  let texto2 = ` texto ${nombre}`
  
  //Posición del texto 
  
  let nombre = "JUAN"
  			  0234
  console.log(nombre[0])		// J
  console.log(nombre[1])		// U
  ```




Con esto  lo básico de tipos de datos y hacemos un pausa  para tocar otros temas, para poder entender el siguiente tipo de dato, que seria el objecto 

## Operadores 

### operadores aritméticos

- `+` :  Operador de adición o suma 

  ```javascript
  let a = 2
  let b = 4
  let suma = a + b
  console.log(suma) 	// 6
  ```

- `-`: Operador resta o reducción 

  ```javascript
  let a = 2
  let b = 4
  let resta = a - b
  console.log(resta) 	// 2
  ```

- `/`: Operador de división

  ```javascript
  let a = 6
  let b = 2
  let division = a / b
  console.log(division) 	// 3
  ```

- `*`: Operador de multiplicación

  ```javascript
  let a = 2
  let b = 2
  let multiplicacion = a * b
  console.log(multiplicacion) 	// 4
  ```

- `%` Operador de residuo.

  ```javascript
  let a = 10
  let b = 4
  let residuo = a % b
  console.log(residuo) 	// 2
  ```

### Operadores Unarios

Este realizan una operación con un único valor, en este habrá ejemplos que quizá no entiendan, pero esta ahí cuando lo entiendan

- `delete` : Este operador elimina una propiedad de un objeto y devuelve un Boolean

  ```javascript
  const usuario = {
      nombre:"Juan",
    apellido:"Martinez",
      edad:20
  }
  
  delete.usario.edad 		// True
  
  //volvemos a ver nuestro objeto
  console.log(usuario)   // Object { nombre: "Juan", apellido: "Martinez" }
  ```
  
- `typeof(value)`: Este operador determina que tipo de dato del valor pasado

  ```javascript
  typeof({}) 		// "object"
  typeof([]) 		// "object"
  typeof(2)		// "number"
  typeof("")		// "string"
  typeof(true)	// "boolean"
  ```

- `+` : Este operador unario positivo convierte un valor a un tipo numérico 

  ```javascript
  +"3" 	 // 3
  +true 	 // 1
  +false	 // 0
  +[2+2] 	 // 4
  
  ```

- `-` : Este operador convierte su valor a un tipo numérico y luego lo niega, es decir si es positivo lo niega a negativo y así viceversa

  ```javascript
  -"3" 	// -3
  -true 	// -1
  -false	// -0
  - -3	// 3
  ```

- `~`: Operador NOT en modo bit, Este tiene una explicación amplia así que pueden investigar más sobre esto, aquí veremos unos ejemplos, si aplicamos  esto en un valor, convierte a numero y le incrementa +1 después niega este  valor

  ```javascript
  ~true 	// -2 
  ~0		// -1
  ~2 + 5	// 2 
  ```

- `!` :  Operador lógico NOT, Este operador convierte su valor aun Booleano y después este lo cambia a su valor contrario

  ```javascript
  !true		// false
  !false	 	// true
  !""			// true
  ! 0			// true
  !-4			// false
  ```



### Operador de igualdad

Los operadores de igualdad se basan en de comparar dos datos y este va determinar o devolver un tipo de dato Boolean (verdadero o falso) esto dos datos obtendrás cuando hagas una comparación 

- `==` : Operador de igualdad

  ```javascript
  2 == 2  	// true
  3 == 2 		// false
  "2" == 2 	// true
  
  ```

- `===`: Operador de igualdad estricto, este es diferente al anterior por que si miramos el anterior este puede comparar un tipo de dato String con un Numérico  a diferencia esta solo compara dos tipos de datos iguales y pueden ir probando con diferentes tipos de datos 

  ```javascript
  2 === 2  		// true
  3 === 2 		// false
  "2" === 2 		// false
  "hola" === "hola"	// true
  
  ```

- `!=`: Operador de desigualdad

  ```javascript
  2 != 2  	// false
  "2" != 2	// false
  ```

- `!==`: Operador de desigualdad estricta al igual que los estricto este solo puede comparar tipos de datos iguales  

  ```javascript
  2 !== 2  	// false
  "2" !== 2	// true
  ```

### Operadores relacionales

Estés operadores son de comparación y retornan un valor Boleano  determinando si es falsa o verdadera, aquí unos ejemplo si no lo entienden, regresen cuando entiendan los objetos 

- `in`:  Este operador determina si un objeto tiene una propiedad devolviendo un Boleano

  ```javascript
  prop in object // sintaxis
  
  // Arrays
  let frutas = ["manzana", "naranja","durazno"]
  0 in frutas 			// true
  "manzana" in frutas 	// false , in solo busca en los indices de los objetos 
  
  
  // in Objectos
  let micoche= {marca: "Honda", modelo: "Accord", año: 1998};
  "marca" in micoche 		// true
  "Honda" in micoche 		// fasle
  ```

- `instanceof`: El operador  determina si un objeto es una instancia de otro objeto, es decir si fué creado con una función constructora determinada.

  ```javascript
  let texto = new String("Tierra")
  texto instanceof String		// True
  
  let fecha = "12/12/12"
  fecha instanceof Date		// false
  
  ```

- `<`:  Menor que 

  ```javascript
  2 < 4 	// true
  4 < 2	// false
  ```

- `>` Mayor que

  ```javascript
  2 > 4 	// false
  4 > 2	// true
  ```

- `<=`  Menor o igual a, valida cualquiera de esas funciones

  ```javascript
  4 <= 4 	// true
  3 <= 4 	// true
  5 <= 4 	// false
  ```

- `>=` mayor o igual a, valida cualquiera de esas funciones

  ```javascript
  4 >= 4 	// true
  3 >= 4 	// false
  5 >= 4 	// true
  ```

  

### Operadores lógicos binarios

Los operadores lógicos son típicamente usados con valores Boleanos 

`&&` :  Ente operador se traduce a (Y) 

```javascript
2 == 2 && 3 == 3 	// true
2 == 2 && 3 == 3 	// true
2 == 3 && 3 == 3 	// false
//Estamos comparando dos comparaciones al mismo tiempo con el operador Y
```

`||` :  Ente operador se traduce a (O) , Este es un poco dificultoso de entender, lo que prioriza  este operador es encontrar un verdadero, y automáticamente este retorna una validación de true o verdadero, pero si ninguna de las comparaciones retorna un verdadero, este recién da el resultado de falso 

```javascript
2 == 2 || 4 == 5	// true
4 == 3 || 2 == 1 	// false
```



### Operadores de asignación

Un operador de asignación, asigna un valor al operando o variable de la izquierda basado en el valor del operando o variable de la derecha. generalmente utilizamos cuando asignamos valor a una variables o reasignamos el valor

- `=` : Asignación

  ```javascript
  let nombre = "JUAN"
  ```

- `+=`: Asignación de suma

  ```javascript
  let numero = 4
  numero += 3		// 7
  ```

- `-=`:  Asignación de resta

  ```javascript
  let numero = 4
  numero -= 1		// 3
  ```

- `*=`: Asignación de multiplicación

  ```javascript
  let numero = 2
  numero *= 2		// 4
  ```

- `/=` Asignación de división

  ```javascript
  let numero = 4
  numero /= 2		// 2
  ```

- `%=`: Asignación de residuo

  ```javascript
  let numero = 10
  numero %= 7	// 3
  ```

### Operador Condicional (ternario)

Este operador como su nombre es de condicional, más adelante iremos explicando las condicionales 

```javascript
//(condition ? ifTrue : ifFalse)

let casado = true

casado === true ? "casado" : "no esta casado"		// casado

```



## Incremento y decremento

Estés son las peculiaridades que encontramos en JavaScript

- **Pre Incremento**: Este tipo de incremento, asigna un "1 " antes de asignarse a una variable y este retorna su valor final, veamos ejemplos

  ```javascript
  let a = 0
  ++a				// 1
  console.log(a) 	// 1
  ```

- **Pos Incremento**: Este incremento, asigna un "1"  después de la variable, cosa que esto retorna el mismo valor, pero si volvemos a llamar a la variable este tendrá ese +1 

  ```javascript
  let a = 0
  a++				// 0 
  console.log(a) 	// 1
  ```

- **Pre Decremento** : Al igual que pre incremento, pero este decrementa en -1

  ```javascript
  let b = 4
  --b				// 3
  console.log(a) 	// 3
  ```

- **Pos Decremento**: Ya sabes los pos y pre, sabiendo que es incremento y decremento, pueden entender esto

  ```javascript
  let b = 4
  b--				// 4
  console.log(a) 	// 3
  ```

  

## Estructuras de control

Las estructuras de control permiten modificar el flujo de ejecución de las instrucciones de script o código, en si del programa 

Las estructuras de control nos permiten validar nuestro algoritmo, es decir indicarle al programa cual es flujo que va seguir cuando se ejecute nuestro código 

### Condicionales

Una condicional es un instrucción o grupo de instrucciones que se pueden ejecutar en función a la condición que se desea validar. Si están siguiendo atentamente el documento ya vimos sobre los operadores que retornaban tipos de datos boleanos y en las condicionales solo podemos validar estos tipos de datos, que son boleanos( true o false)

- `if(condici+on)` : (si) cumple la condición

  ```javascript
  // condicional en linea
  if(true) 2 + 2		// 4
  
  // Condicional de bloque
  if(true){ 
  	2 + 2 			// 4
  }
  ```

- `if else`:  si cumple hacer algo y si no cumple hacer otra cosa

  ```javascript
  let edad = 20
  
  if (edad >= 18){
      console.log('Eres mayor de edad')
  }else{
      console.log('Eres menor de edad')
  }
  
  //Respuesta: 'Eres mayor de edad'
  ```

- condicional ternario

  ```javascript
  // (condition ? si es verdadero : si es falso)
  let edad = 15
  edad >= 18 ?  console.log('Eres mayor de edad') :  console.log('Eres menor de edad')
  
  //pueden averiguar la respuesta
  ```



- Condicionales múltiples: En este ejemplo veremos sobre los operadores **lógicos binarios**,(&&) (||) ustedes ya saben la teoría. y con estos operadores podemos hacer condicionales múltiples

  ```javascript
  if(3 >= 2 && 4 <= 7){
   // Evaluen si la expresión pasa por este comentario
   }
  
  if(2 >= 3 || 7 <= 4){
   // Evaluen si la expresión pasa por este comentario
   }
  ```



### Truthy  

En JavaScript tenemos propiedades verdaderas y falsas  y estos aplicar cuando necesitemos realizar condicionales

- cadenas de textos
- números diferentes de cero
- objetos

```javascript
true	//true	
4 		//true
"text0"	//true
{}	//true
[] 	//true
new Date() //true
-4 	//true
```

### Falsy

Al igual que truthy pero propiedades falsas 

```javascript
false 	//false
0  	//false
"" 	//false
undefined 	// false
NaN 		// false
null 		// false
```

### switch

Este evalúa una expresión, comparando el valor de la expresión con una de sus instancias **case** y ejecuta las declaraciones asociadas a ese **case**.

```javascript
switch (expresion) {
	case value:
		// expresiones 
		break;

	default:
		// expresiones si no encuentra el valor en niguna de sus instancias del case
		break;
}


//ejemplo


let dia = 4
switch (dia) {
	case 1:
		console.log('Lunes')
		break
	case 2:
		console.log('Martes')
		break
	case 3:
		console.log('Miercoles')
		break
	case 4:
		console.log('Jueves')
		break
	case 5:
		console.log('Viernes')
		break
	case 6:
		console.log('Sábado')
		break
	default:
		console.log('No es un dia de la semana')
		break
}

// Resuesta:'Jueves'
```



### Bucles

Los bucles se utiliza cuando generalmente necesitamos hacer algo varias vece

- `for`: Este bucle se repite hasta que la condición evalúe a falso

  ```javascript
  // sintaxis
  for ([expresionInicial]; [condicion]; [expresionIncremento]){
      // sentencia o imprimir algo varias veces
  }
      
  //Ejemplo
  for(let i = 1; i <= 10; i++){
  	console.log(i)
  }
  //Resultado seria una serie de numeros
  1 
  2 
  3 
  4 
  5 
  6 
  7 
  8
  9
  10
  ```

  

- `do while`: al igual que for ese tiene una peculiaridad que recorre una vez la sentencia.

  ```javascript
  let i = 0
  do {
    i += 1;
    console.log(i);
  } while (i < 5);
  
  //Resultado seria una serie de numeros
  1 
  2 
  3 
  4 
  
  ```

- `while` : Esta sentencia se ejecuta mientras la condición sea evaluada  como  verdadera 

  ```javascript
  let i = 0
  while(i<=5){
      console.log(i)
      i++
  }
  //Resultado seria una serie de numeros
  1 
  2 
  3 
  4 
  5 
  
  ```

- `break and continue`: Estos serian la la opciones de romper o continuar un ciclo 

  ```javascript
  // break : romper el cilo o cancelar todo
  for(let i =0;i<=5; i++){
  	if(i == 2) break
    	console.log(i)
  }
  
  //respuesta: 
  0
  1
  
  
  //continue: saltar el valor que hagas en una validación, es decir continuar
  for(let i =0;i<=5; i++){
  	if(i == 2) continue
    	console.log(i)
  }
  //respuesta: 
  0
  1
  3
  4
  5
  
  ```



## Funciones

En términos generales una función es un "subprograma" con instrucciones o sentencias, que conforman el llamado cuerpo de la función. Se pueden pasar valores a una función y una función puede devolver un valor. 

Expliquemos a profundo lo que son la funciones en JavaScript y la importancia en la programación , Para entender mejor, véanlo de este modo. Las funciones son bloques de código re utilizables, un ejemplo de la funciones en la vida real, seria algo así como una licuadora, donde podamos ingresar muchas frutas y tendríamos un resultado que seria un jugo, Las funciones son algo así podemos ingresar o no  datos  para obtener un solo resultado o que devuelva un resultado, como el jugo.

### Cosas que debemos saber sobre las funciones

- las funciones tienen un identificador que es su `nombreFuncion` 

Una función tiene un nombre, tiene parámetros, y devuelve datos, hay entender eso sobre las funciones  

```javascript
//sintaxis basica de una funcion
function nombreFuncion(parametro1, parametro2) {
   //instrucciones
    return valor
}

// un ejemplo 
```



### Conceptos de  iremos escuchando en funciones

- **Parámetros**: Son valores locales que se definen en la declaración de la función se puede asignar valores por defecto a los parámetros 
- **Argumentos**: Son los valores que pasamos a la función al momento de llamarlos



### Formas de declarar una función

- función inicial

  ```javascript
  function nombreFuncion(parametro1, parametro2) {
     //instrucciones
      return valor
  }
  ```

- función de uso

  ```javascript
  var nombreFuncion = function() {
      // instrucciones de la función
      return valor
  }
  ```

- función de flecha

  ```javascript
  const nombreFuncion = (parametros) => {
      // instrucciones de la funcion
      return valor
  }
  ```

### Parámetros rest(spread operator)

Son 3 puntos para indicarle múltiples parámetros, en si lo que hace el `spread operator` es convertir todo el conjunto de argumentos en un array y sabiendo que es un array ya puedes manipular los datos a tus necesidades, si no entiendes sobre los arreglos vuelve cuando lo hagas

```javascript
let sumarTodos =(...numeros)=>{
    console.log(numeros)
}

sumarTodos(1,2,3,4,5) 		//[1,2,3,4,5]
```









