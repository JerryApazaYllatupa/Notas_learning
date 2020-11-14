[TOC]

# Go desde cero	

En este tema aprenderemos todo sobre go sera un experimento de cuanto estoy aprendiendo el lenguaje y explicaremos con nuestras propias palabras, y tengo una super idea para que un buen texto o un documento sobre algo pueda ser explicado mejor y que cada persona que pueda entender y aprender cuando lean documento, para ello aplicaremos estos conceptos.

1. Explicar claramente los conceptos 
   1. lo que podemos hacer es hacer comparaciones con la vida real, sobre lo que estamos explicando 
   2. hacer metáforas 
   3. simplificar los conceptos 
   4. buscar ejemplos del mundo real 
   5. utilizar gráficos
   6. buenos ejemplos separan de buenos y los malos 
   7. carisma y pasión 
   8. poner ejemplos de casos reales 

## Tipos de datos 

Que son los tipos de datos, Si tu vienes de otros lenguajes de programación ya tienes noción sobre los tipos de datos, pero en cada lenguaje esto varia no tan distintos del otro de todas manera vamos a explicar que son los tipos de datos y que siempre los vamos a tener donde sea que queramos aprender un lenguaje de programación.

Los tipos de datos categorizan un conjunto de valores, describen las operaciones que se puedan hacer con ellas y definen la forma en que son almacenados en la memoria , parece complicado de entender pero entraremos mas en detalle para comprender sobre esto y que es importe en el tema de la programación.

Vamos a generalizar un poco sobre los lenguajes de programación, cada lenguaje de programación tiene diferentes formas de los tipos de datos y aquellos datos son

- Numeros (Numbers)
- Cadenas (String)
- Booleanos  (Boolean)

prácticamente hay muchos mas en los otros lenguajes, pero aquí vamos a centrarnos solo de go ya toca investigar cuales son sobre los otros lenguajes

### Números (Numbers)

Go tiene varios tipos de números para representar y lo vamos clasificar en dos los números enteros y números flotantes 

#### Enteros (Integers) 

Como ya saben de 0 al infinito y del -0 al -infinito, mostraremos una tabla y es el rango de datos que puede almacenar cada tipo de dato entero

```go
tipo -------------------------- rango
uint8                            8-bits (0 a 255)
uint16                           16-bits (0 a 65535)
uint32                           32-bits (0 a 4294967295)
uint64                           64-bits (0 a 18446744073709551615)

int8                           	 8-bits (-128 a 127)
int16                            16-bits (-32768 a 32767)
int32                            32-bits (-2147483648 a 2147483647)
int64                            64-bits (-9223372036854775808 a 9223372036854775807)


```

### Números de punto flotante

Son Números que contienen componentes decimales (números reales ) como por ejemplo `1.001` pero puede tener el infinito de decimales, podemos clasificar en dos  y arriba ya sabemos cuantos decimales puede almacenar : 

```go
float32
float64
complex64
complex128
```

Go también nos proporciona otras implementaciones con sus tamaños específicos  

```go
tipo -------------------------- rango
byte                            8-bits (0 a 255)
rune                            32-bits (-2147483648 a 2147483647)
uint                            32 o 64 bits
int                           	32 o 64 bits
uintptr                         Entero guarda los bits no interpretados de un puntero


```

### Cadena (String)

Una cadena es una secuencia de caracteres que se utiliza para representar texto, prácticamente cualquier texto y como ya sabemos las cadenas siempre van con un comillas `" "`  pero en go también tenemos las comillas inversas  ` (``)`  veamos unos ejemplos ,no se preocupen si no entienden que esta en el código pero así se utiliza las cadenas.

```go
texto := `Hello world`
texto1 := "Hola mundo"
fmt.Println(texto, texto1)
```

#### Algunas cosas a tener en cuenta

- Cada cadena osea cada texto tiene una posición cada cadena tiene un tamaño y dentro de esto los espacios también son considerados 
- La longitud de la cadena inicia en cero 
- Con el signo `+` podemos concatenar cadenas 

### Booleanos (Booleans)

Booleanos son dos tipos `true` que es Verdadero, `false` que es falso, estos también son representados por 1 verdadero y o falso  o encendido y apagado 

## Variables 

Una variable es una ubicación de almacenamiento en memoria con un nombre asociado y un tipo de dato asociado y la información que almacena son de muchos tipos de datos, entonces a esto llamamos," tipos de datos", cada lenguaje de programación tiene diferentes tipos de datos pero no tan distintos del otro.	

Bueno veamos las variables en `go` , las variables en `go` se declaran con las palabra `var`  seguido del nombre `nombre_variable` y el tipo de dato que va almacenar por ejemplo `int`,`string`,`bool`, etc. que iremos explicando a lo largo del documento.

Si vienes de otros lenguajes, como por ejemplo `JavaScript` , no tienen la opción de estar indicando que tipo de dato va almacenar, te sugiero que leas sobre "que es  estrictamente tipados y débilmente tipados en lenguajes de programación " y `go` es uno de los lenguajes de "estrictamente tipado".



```go

package main

import "fmt"

func main() {
    
    // Declaración de variables 
	var nombre string
}
```

De esta forma declaramos una variable, pero veamos solo declaramos la variable y ya en go esto no da un error, por que no estamos cumpliendo la regla, y la regla de go es que cada variable debe pasar por esto; "ser declarada, ser asigna un dato  y ser llamada o ser utiliza", hasta ahora solo hemos echo la declaración de variable, veamos como podemos pasar por estas 3 faces

```go

package main

import "fmt"

func main() {
    
    // -- Declaración de variables --
	var nombre string
    
    // -- Asignar dato a la variable -- 
	nombre = "Juan"
    //nota: tenemos que tener en cuenta que solo va almacenar el tipo de dato que hemos indicado que va almacenar
    
    // -- Utilizar la variable --
    fmt.Println(nombre) // respuesta: Juan
}
```

si eres nuevo en la programación, al momento de **asignar el valor a la variable** con el `=` estamos diciendo que: la variable tiene ese valor o es igual a ese valor, veamos en nuestro ejemplo tenemos una variable `nombre = "Juan"`,  ahora `nombre` vale `"Juan"` por eso al final al **utilizar la variable** al momento de imprimir esa variable, esta imprime ese valor.

Las variables puedes ser modificadas su valor en el transcurso del programa 

También go nos permite simplificar estos pasos en una sola linea,veamos

```go
nombre := "Juan"
fmt.Println(nombre)
// respuesta: Juan
```

Esto seria todo, con los `:` antes del `=` le decimos a go, go asignale  el   **tipo de dato** a mi variable de acuerdo al valor que le paso , y entonces go verifica el valor de la variable, y le asigna el tipo de dato, que en este caso seria un string , si queremos ver el tipo de dato de una variable tenemos esta opción `fmt.Printf("%T \n", nombre)`, por lo general se utiliza este ultimo modo.

## constantes

Go también tiene soporte para las constantes, en si que son las constantes, las constantes son básicamente **variables que no pueden cambiar su valor** , estos se declaran con la palabra reservada `const` seguido del `nombre_constante` y el tipo de dato.

```go

package main

import "fmt"

func main() {
    
 const db string = "dbtieneda"
 println(db)
 //respuesta : dbtieneda
    
}
```

que pasa si queremos asignar  otro valor a la variable `db`  esto daría error y el mismo editor te dará el error antes de compilar, recuerda que las constantes en los lenguajes están para eso, que no se puede reemplazar el valor de la variable, recuerda eso

### Definición de múltiples variables 

Go también tiene otra forma de definir muchas variables

```go
package main
import "fmt"

func main() {
	var (
		nombre = "Juan"
		edad   = 20
		casado = true
	)
    
    fmt.Println(nombre, edad, casado)
    //respuesta: Juan 20 true
    
    
   // -- otra forma seria esta --
    nombre, edad, casado := "Juan", 20, true
	fmt.Println(nombre, edad, casado)
   //respuesta: Juan 20 true
}
```

Esto también podemos hacer con las constantes, véanlo ustedes mismos, en el caso de las constante si quieren en una sola linea se hace de esta forma

```go
const nombre, edad, casado = "Juan", 20, true
fmt.Println(nombre, edad, casado)
```



Un ejemplo de un programa para el momento con todo lo que hemos aprendido  

Pregunta 1:  declare 3 variables y 3 constantes en una sola linea con los nombres "nombre, edad y lugar", llénalos con tus datos e imprimirlos 

## Operadores 

Todos los lenguajes de programación necesitan de operadores para realizar tareas o instrucciones. Los operadores son símbolos o conjunto de símbolos que especifican alguna operación o alguna relación matemática. y vamos a clasificar los operadores 

### Operadores Aritméticos 

Estos operadores como su nombre dice solo vamos a trabajar con todo lo que es aritmética, y alguno que otro lo explicaremos mas a detalle

| Operador | Descripción                                               | Ejemplo   |
| -------- | --------------------------------------------------------- | --------- |
| +        | Operador de Suma, es el único que trabaja con las cadenas | 2 + 3 = 5 |
| -        | Operador de Resta                                         | 3 - 2 = 1 |
| *        | Operador de Multiplicación                                | 2 * 2 = 4 |
| /        | Operador de división                                      | 6 / 3 = 2 |
| %        | Operador de Modulo o de residuo de la división            | 5 % 3 = 2 |
| ++       | Operador de incremento, incrementa en 1                   | x++       |
| --       | Operador de decremento, decrementa en -1                  | x--       |

Si no te entiendes los 3 últimos operadores vamos a explicar mas adelante a detalle, por ahora puede pasar

### Operadores Relacionales

Los operadores relaciones son aquellos que devuelven un valor booleano (verdadero o falso) cuando se resuelve una expresión veamos la tabla

| Operador | Descripción                                                  | Ejemplo     |
| -------- | ------------------------------------------------------------ | ----------- |
| ==       | Operador de" idéntico a ..." , devuelve verdadero cuando ambos operandos son iguales | 2 == 2 true |
| !=       | Operador de "diferente a ...", devuelve verdadero cuando los operandos son distintos | 2 != 3 true |
| >        | Operador de "mayor que ...", devuelve verdadero cuando el operando de la izquierda es mayor que el de la derecha | 3 > 2 true  |
| <        | Operador de "menor que ...", devuelve verdadero cuando el operando de la izquierda es menor que el de la derecha | 2 < 3 true  |
| >=       | Operador de "Mayor o igual que ..." devuelve verdadero cuando el operando de la izquierda es mayor o igual que el de la derecha | 3 <= 3 true |
| <=       | Operador de "Menor o igual que ..." devuelve verdadero cuando el operando de la izquierda es menor o igual que el de la derecha | 2 <= 2 true |

### Operadores lógicos a nivel de bits (bit a bit)

Los operadores de bits, trabajan sobre bits, 0 es falso y 1 es verdadero, veamos en la tabla 

| Operador | Nombre                            | Descripción                                                  | Ejemplo                                        |
| -------- | --------------------------------- | ------------------------------------------------------------ | ---------------------------------------------- |
| &        | Conjunción (AND)                  | Verdadero(1)  mientras ninguno de los operandos sea falso    | (0011 0011 & 1100 0011) es igual a: 00000011   |
| \|       | Disyunción (Or)                   | Verdadero mientras algunos de los operandos sea verdadero.   | (0011 0011 \| 1100 0011) es igual a: 1111 0011 |
| ^        | Disyunción exclusiva (Xor)        | Verdadero mientras los operandos sean distintos              | (0011 0011 ^ 1100 0011) es igual a: 1111 0000  |
| <<       | Corrimiento de bit a la izquierda | Los bits son movidos a la izquierda la cantidad de posiciones que se especifique | (0011 0011 << 2) es igual a: 1100 1100         |
| >>       | Corrimiento de bit a la derecha   | Los bits son movidos a la derecha la cantidad de posiciones que se especifique | (0011 0011 >> 2) es igual a: 0000 1100         |

### Operadores Lógicos

Estos operadores lógicos son parecidos a los operadores de bits, pero también son de comparación



| Operador | Descripción                                                  | Ejemplo                |
| -------- | ------------------------------------------------------------ | ---------------------- |
| &&       | Devuelve verdadero, cuando los dos operandos son verdaderos o sea (true) | true && true = true    |
| \|\|     | Devuelve verdadero, cuando uno de los dos operandos es verdadero | true \|\| false = true |
| !        | Operador de Negación, invierte o niega el valor booleano     | !false = true          |

### Operadores de asignación

Estos operadores nos permiten modificar el valor de las variables, mientras que desarrollamos nuestros programas 

| Operador | Descripción                                                  | Ejemplo                              |
| -------- | ------------------------------------------------------------ | ------------------------------------ |
| =        | Operador de asignación, le asigna un valor al operador de la izquierda, el valor del operador de la derecha | x = "texto" = "texto"                |
| +=       | Operador de suma y asignación. Reasigna al operador de la izquierda su valor de si mismo, mas el valor del operador derecho | x += 2 =  2                          |
| -=       | Operador de resta y asignación. Reasigna al operador de la izquierda su valor de si mismo, restando el valor del operador derecho | x -= 2 =  2                          |
| *=       | Operador de multiplicación y asignación. Reasigna al operador de la izquierda su valor de si mismo, multiplicando con el valor del operador derecho | x *= 2 =  2                          |
| /=       | Operador de división y asignación. Reasigna al operador de la derecha su valor de si mismo, dividiendo con el valor del operador derecho | x /= 2 =  2                          |
| %=       | Operador de modulo y asignación. Reasigna al operador de la derecha guardando el residuo de la división del valor de si mismo con el valor del operador derecho | x %= 2 =  2                          |
| <<=      | Operador de desplazamiento de bits a la izquierda y asignación. Asigna al  operando de la izquierda el resultado de aplicarle un desplazamiento de n bits a la izquierda. | X <<= 2 es igual a escribir X = X<<2 |
| \>>=     | Operador de desplazamiento de bits a la derecha y asignación. Asigna al operando de la izquierda el resultado de aplicarle un desplazamiento de n bits a la derecha. | X >>= 2 es igual a escribir X = X>>2 |
| &=       | Operador de conjunción de bits y asignación. Asigna al operando de la izquierda  el resultado de aplicar una conjunción con el operando de la derecha. | X &= Y es igual a escribir X = X&Y   |
| \|=      | Operador de disyunción de bits y asignación. Asigna al operando de la izquierda  el resultado de aplicar una disyunción con el operando de la derecha. | X ^= Y es igual a escribir X = X&Y   |
| ^=       | Operador de disyunción exclusiva de bits y asignación. Asigna al operando de la  izquierda el resultado de aplicar una disyunción exclusiva con el  operando de la derecha. | X ^= Y es igual a escribir X = X^Y   |

### Operadores de Dirección

Estos últimos operadores de go, son de dirección de variables y apuntadores, algo nuevo en este lenguaje

| Operador | Descripción                                  | Ejemplo                              |
| -------- | -------------------------------------------- | ------------------------------------ |
| &        | Regresa la dirección en memoria del operando | &x regresa la dirección en memoria x |
| *        | Apuntador a una variable                     | *P apunta a una variable             |
|          |                                              |                                      |

### Precedencia de los operadores

La precedencia de los operadores nos indica el orden en el que los operadores serán evaluadas

En una ecuación cuando no asociamos precedencia de operadores, este por defecto lo hace de acuerdo a la precedencia de los operadores de izquierda a derecha, por ejemplo `2 + 2*3 = 8`,  veamos la tabla de precedencia.

| Precedencia | Categoría      | Operador                             |
| ----------- | -------------- | ------------------------------------ |
| 15          | Posfijo        | ()  [] ->  .  ++  --                 |
| 14          | Unitario       | +  -  !  ~  ++  -- (type)* &  sizeof |
| 13          | Multiplicativo | *  /  %                              |
| 12          | Adición        | +   -                                |
| 11          | Desplazamiento | <<  >>                               |
| 10          | Relacional     | <  <=  >  >=                         |
| 9           | Igualdad       | ==  !=                               |
| 8           | AND nivel bits | &                                    |
| 7           | XOR nivel bits | ^                                    |
| 6           | OR nivel bits  | \|                                   |
| 5           | AND Lógico     | &&                                   |
| 4           | OR Lógico      | \|\|                                 |
| 3           | Condicional    | ? :                                  |
| 2           | Asiganación    | =  +=  -=  *=   /=  ...              |
| 1           | Coma           | ,                                    |

 

### Operadores aritméticos

Estos operadores se aplican a los a valores numericos y producen un resultado del mismo tipo veamos esto operadores 

| Operadores | Nombre operador      | Donde se puede aplicar                  |
| ---------- | -------------------- | --------------------------------------- |
| +          | Suma                 | Enteros,floats,complex, values, cadenas |
| -          | Resta                | Enteros,floats,complex, values          |
| *          | Multiplicación       | Enteros,floats,complex, values          |
| /          | División             | Enteros,floats,complex, values          |
| %          | Resto                |                                         |
|            |                      |                                         |
| &          | bit (y)              | Enteros                                 |
| \|         | bit (o)              | Enteros                                 |
| ^          | bit a bit (o)        | Enteros                                 |
| &^         | poco claro (and not) | Enteros                                 |
| <<         | shift izquierdo      | Entero << entero sin signo              |
| >>         | shift derecho        | Entero << entero sin signo              |

Aquí vamos a explicar mas a detalle sobre los operadores de de bit,  estos operadores es mas para trabajar con bits, pero también podemos utilizarlo cuando estamos realizando nuestros programas, veamos algunos ejemplos de como utilizar estos operadores.

## Estructuras de control 

### Condicionales

las condicionales nos permiten evaluar por que cual ruta queremos llevar nuestros programas, las condicionales solo evalúan booleanos

#### if

La condicional `if `, si tal expresión se cumple entonces pasa hacer algo, eso es todo lo que hace veamos como es la sintaxis

```go
if true {
		fmt.Println("Hello world")
	}
// respuesta: Hello world

if 5 > 7 {
		fmt.Println("Imprime mayor")
}
//respuesta: 
```

En el segundo ejemplo de la condicional no imprime nada por que simplemente la expresión no da verdadero, si vienes de otros lenguajes ya sabes esto y go tiene esta diferencia que no es obligatorio los paréntesis en algunos casos, solo estamos viendo en el caso de que si la expresión solo da verdadero, pero que pasa si da falso y queremos  algo cuando la expresión no se cumple, aquí es donde entra el `else` 

#### Else

Cuando evaluamos expresiones y esta no es verdadera, entonces podemos hacer algo al respecto veamos nuestro ejercicio anterior

```go
if 5 > 7 {
		fmt.Println("Imprime texto")
	} else {
		fmt.Println("El numero es menor")
	}
//respuesta "El numero es menor"
```

y así hacemos alguna instrucción cuando la condicional no se cumple 

#### Switch

`Switch` nos permite evaluar muchas expresiones, veamos estos ejemplos 

```go
dia := 7
	switch dia {
	case 1:
		fmt.Println("lunes")
	case 2:
		fmt.Println("Martes")
	case 3:
		fmt.Println("Miercoles")
	case 4:
		fmt.Println("Jueves")
	case 5:
		fmt.Println("viernes")
	case 6:
		fmt.Println("Sabado")
	case 7:
		fmt.Println("Domingo")
	default:
		fmt.Println("No es un dia de la semana")
	}

//respuesta: Domingo
```

Así es como evaluamos, también go tiene otra peculiaridad de utilizar el switch, y es que podemos hacer evaluaciones en su opciones de case 

```go
switch edad := 15; {
	case edad >= 12 && edad <= 17:
		fmt.Println("eres un adolecente")
	case edad >= 18:
		fmt.Println("Eres mayor de edad")
	default:
		fmt.Println("todavia eres un niño")
	}
```



Aquí es cuando ya empezamos a entrar mas en la programación, cuando tenemos la necesidad de hacer muchas veces algo "repetir" y allí entra las estructuras de control 



### Ciclos

#### for

La instrucción `for` nos permite repetir una lista de declaraciones varias veces. la sintaxis es, go tienen muchas variantes del ciclos

```go
// for básico

for i := 0; i < 10; i++ {
		fmt.Println(i)
}

//respuesta: 
1
2
3
4
5
6
7
8
9


```

```go
for i:=0; i< 10; i +=2 {
	fmt.Println(i)
	}
//Respuesta
0
2
4
6
8
```

**For de Rango**: También tenemos el bucle de rango que sirve para recorrer  datos de estructuras, lo que hace es que primero evalúa el tamaño del rango para recorrer esa cantidad de veces dentro del rango puede evaluar una matriz, un puntero a una matriz, un segmento, una cadena, un mapa, o un canal que permita operaciones de recepción 

```go
	frutas := []string{"Naranja", "Manzana", "Uva"}
	for _, item := range frutas {
		fmt.Println(item)
	}
//Respuesta: 
Naranja
Manzana
Uva
```

**Sentencia Break**: Esta sentencia nos permite romper un bucle

```go
	for i := 0; i < 10; i++ {
		if i == 5 {
			fmt.Println("si el Numero llega a 5 romper el bucle")
			break
		} else {
			fmt.Println(i)
		}
	}

// Respuesta 
0
1
2
3
4
si el Numero llega a 5 romper el bucle
```

Como ven, el bucle se rompe cuando llega a 5 

**Sentencia continue**: Esta sentencia hace que ignore el código o se pase de largo en la validación correspondiente y siga continuando la iteración

```go
	for i := 0; i < 10; i++ {
		if i == 5 {
			continue
		} else {
			fmt.Println(i)
		}
	}

//respuesta
0
1
2
3
4
6
7
8
9
```

Si observamos detalladamente el código veremos que el número 5 falta, como dijimos la sentencia `continue` ignora el dato en la y siga continuando con su iteración

**for con condicionales únicas**:  Estas condicionales se utilizan cuando solo va tener una condición veamos un ejemplo

```go
for a < b {
	a *= 2
}
```

## Estructuras de datos 

Si recuerdan al principio vimos los tipos de datos  las estructuras de control también son un tipo de dato dentro de esto tenemos muchos otro tipos de datos mas

### **Arreglos(array)**:

Los arreglos en go nos permite almacenar una colección de elementos de un solo tipo de dato, ese decir no podemos almacenar enteros con cadenas, bien solo almacenamos enteros o solo cadenas, pero también en los arreglos es obligatorio indicar el tamaño de longitud del arreglo, es decir cuantos valores solo puede almacenar, veamos un ejemplo.

```go
// ---- declaración base de arreglos -------
var nombres [3]string
// en este variable nombres solo puedo almacenar 3 valores y si queremos almacenar el 4 valor de seguro tendremos error

nombres[1] = "Maria"
nombres[0] = "Juan" 
nombres[2] = "Pedro"

// ---- declaración avanzanda de arreglos ----
 nombres := [3]string{
	"Maria",
	"Juan",
	"Pedro",
}
// también podemos declarar de esta manera que es mas facil
```

### **Slice**

Los slice son igual que los arreglos, con la única diferencia que a este no se le indica el tamaño o el límite de datos que va almacenar, pero al igual que los arreglos solo pueden almacenar un solo tipo de dato

```go
nombres := []string{
		"Juan",
		"Maria",
		"Pedro",
	}
fmt.Println(nombres)
```

También hay otra forma de crear un slice y es con la función `make()` que es la que mas se utiliza en la comunidad de go, esta función tiene 3 parámetros y primero el tipo de dato, segundo la capacidad inicial y el tercero la capacidad final.

```go
nombres := make([]string, 0)
nombres = append(nombres, "Maria")
nombres = append(nombres, "Juan")
nombres = append(nombres, "Pedro")
	
fmt.Println(nombres)
```

### Mapas

Este tipo de datos se les llama arreglos multidimensionales, los que vimos hasta el momento son `array` y `slice` a estos les denominamos arreglos unidimensionales por que solo pueden almacenar datos de forma lineal u horizontal , pero en los mapas podemos almacenar datos de forma lineal y vertical veamos ejemplos 

```go
idiomas := map[string]string{
		"es": "Español",
		"en": "Ingles",
		"fr": "Frances",
	}
fmt.Println(idiomas)
```

Este es le la sintaxis  de los mapas

### Estructuras

Este también es una estructura de dato, Es una colección de campos y cada campo con un tipo de dato personalizado, y si vienes de otros lenguajes de programación este puede ser una clase para crear objetos, veamos ejemplos

```go
type Persona struct {
	Nombre string
	Edad   uint8
}

persona1 := Persona{}

persona1.Nombre = "Jerry"
persona1.Edad = 22

fmt.Println(persona1)
```

### Funciones

Las funciones generalmente son bloques de código o colecciones de instrucciones que permiten re utilizar código 

```go
// funciones simples 
 func saludar() {
 	fmt.Println("Hola mundo")
}
```

Función con parámetros 

```go
func saludar1(nombre string) {
 	fmt.Println(nombre)
}
```

Funciones que retornan valor

si vienes de otros lenguajes de programación este casi siempre te parecerá complicado , pero nada mas lejos de ello, solo tenemos que indicar los tipos de datos y entender la sintaxis de cada función como trabajar con ello, ya que sabemos la funcionalidad detrás de las funciones 

```go
func sumar(n1 uint8, n2 uint8) uint8 {
	return n1 + n2
}
```

Funciones que retornan múltiples valores 

En go también tenemos funciones con diferentes peculiaridades, como por ejemplo indicar un return vacío sin ninguna variable ya que las variables lo indicamos  los valores que van a retornar 



## Respuestas a las preguntas

pregunta 1

```go
//variables	
nombre, edad, lugar := "Juan", 20, "Perú"
fmt.Println(nombre, edad, lugar)

//constantes
const nombre, edad, lugar = "Juan", 20, "peru"
fmt.Println(nombre, edad, lugar)
```

