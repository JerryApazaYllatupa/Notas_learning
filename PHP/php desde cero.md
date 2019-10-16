[TOC]



# PHP DESCE CERO

### Comentarios en php	

```php
// comentario en linea 
/*
	Comentario en bloque
*/

```

Imprimir cadenas

```php

<?php 
    print "Hola mundo"; //solo imprimi texto
    echo  "Mi primer hola mundo";
    echo  "Mi primer"," hola mundo"; // puede estar separado por comas
	echo "<h1>Hola mundo</h1>"; // también imprime código html

```

Integrar php en HTML 

```php+HTML
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Practicando php</title>
</head>

<body>

  <?php
  // print "Hola mundo";
  // echo  "Mi primer hola mundo";
  echo  "Mi primer"," hola mundo";
  ?>
</body>

</html>
```

## Tipos de datos 

-  Es tipo de dato es un nombre genérico que se le asigna a cualquier dato que comparte un conjunto común de características 

```php
Estos primeros datos son de tipo escalar por que solo representan un solo valor 
//boleanos (Boolean)
//Enteros (Intenger)
//Flotantes (Double)
//Cadenas (string)
Esto tipos de datos estos pueden tener todo tipo de dato
//Arreglos (Array)
//Objetos (objects)
//Recursos (Resources)
//Nulos (NULL)

```

- Cadenas : Secuencia de caracteres que esta delimitada por comillas simples o dobles 
- Booleanos : Permite representar dos valores `TRUE`o `FALSE`;
- Enteros : Representa números de [0...,9], negativos , octal, hexadecimal, y binarios `10, -10, 0`
- Flotantes: Números decimales, especifico números fraccionarios

### Variables 

Es un espacio de memoria que está determinado por un identificador , es decir que le damos un nombre a ese espacio en memoria, también pueden llegar a cambiar el dato y hasta el tipo de dato

```php
$variable = "valor";
//los nombres de las variables tienen que ser representativos 
```

### Convención de nombres

Es un conjunto de normas y reglas para la escritura de nombre, código fuente,Comentarios e identificadores en programación, facilitan y hacen comprensibles su lectura e interpretación 

-  Camel Case: Primer letra en minúscula y la siguiente concatenada en mayúscula `$miNombre`, `$miSegundoNombre`
- small_caps: Letras en minúsculas y la siguiente letra concatenada separada por un guion `$mi_nombre`, `$mi_segundo_nombre`
- pascal_case: Primer letra y la segunda están concatenas en mayúsculas `$MiNombre`, `$MiSegundoNombre`

### Constantes

Es un valor creado en espacio de memoria que no se puede cambiar mediante la interpretación de código 

```php
define('nombreConstante', valor);
define('PI', 3.141612);
define('url', 'https://dominio.con');
echo url;
```

### saber que tipo de datos es mi variables

```php
//tenemos dos funciones 
$nombre = "nombre";
$numero = 123;
gettype($nombre);//nos devolvera (string) por que nuestro tipo de datos es un string 
var_dump($nombre); // esta función nos devuelve el tipo de dato la longitud y el valor
```

### Datos por referencia 

```php
$nueva = &$nombre;
echo $nueva;
```

## Operadores 

### Operadores aritméticos

```php
+ //suma
- //restar
* //multiplicación
/ // divición
% //modulo es el resto de una divición
```

###  

### Operadores de asignación

```php
= // asignación
+= // le asigne y sume 
-= // le asigne y le reste 
/= // le asigne y que lo divida
*= //le asigne y lo multiplique
.= // le asigne y concatene    
```

### Operadores de incremento / decremento

```php
++$variable //son de preincremento
--$variable // son de predecremento
$variable++ //posdincremento
$varaible-- //posdecremento
```

### operadores de comparación

```php
// o
|| 
or
// y
&&
and
// Igual 
==
//igualdad
===
```



## Arreglos

Es una colección finita de datos múltiples ordenados en filas(unidimensional ) o en columnas y filas (Multidimensional) y pueden ser indexados o asociados 

```php
| 3 | 2 | 2 | 9 | // datos unidimensional 
    
| 3 | 2 | 2 | 9 |
| 3 | 2 | 2 | 9 |
| 3 | 2 | 2 | 9 | // datos multidimensional
| 3 | 2 | 2 | 9 |
| 3 | 2 | 2 | 9 |

```

### Arreglos indexados

Utilizan índices [0..,9], empieza siempre en el índice cero y su total empieza de 1

```php
  | 3 | 4 | 5 | 3 | 2 | 4 | -> varlores o datos de arreglo
  _________________________
  	0   1   2   3   4   5 -> indice en donde se encuentra el valor

      
// Declaración hay dos formas 
$numeros = [3,4,5,3,2,4];
$numeros = array();
      
//Mostrar datos de un arreglo
var_dump($numeros);
print_r($numeros)
echo $numeros[1] //estamos mostrando el valor en el indice 1 del arreglo y en la posición 1 tenemos 4
```



### Arreglos múltiples y asociados 

Serie de espacios que almacenan datos, Nosotros indicamos la relación con una llave, clave o nombre 

```php
$lenguajes = |    php    |   javascript   |      java     |    python     |
		   _________________________________________________________
		    "lenguajes1"    "lenguajes2"    "lenguajes3"   "lenguajes4" 
		       
//asi es como se reprensenta los arreglos asociativos y en codigo seria de esta forma 
$lenguajes = ["lenguaje1"=>'php',"lenguaje2"=>'javascript', "lenguaje3"=>'java', "lenguaje4"=>'python'];

$lenguajes = array("lenguaje1"=>'php',"lenguaje2"=>'javascript', "lenguaje3"=>'java', "lenguaje4"=>'python');

//mostrar estos datos

echo $lenguaje["lenguaje1"]; // resultado php

//esto arreglos son muy importantes por que cada indice se reprenta con un nombre 
```

### Arreglos multidimensionales 

Primero se indica la fila después la columna

```php
| 3 | 2 | 2 | 9 |
| 3 | 2 | 2 | 9 |
| 3 | 2 | 2 | 9 | // datos multidimensional
| 3 | 2 | 2 | 9 |
| 3 | 2 | 2 | 9 |
    
$alumnos=[
  ['nombre','20','pais'],
  ['nombre'=>'juan','edad'=>'20','pais'=>'peru']
];
print_r($alumnos[0][2]); // igual a "pais"


```

### Funciones nativas de php para arreglos

```php
//validar si un arreglo esta vacío
$alumnos=[];
var_dump(empty($alumnos));//true por que esta vacio

//validar si existe algo 
var_dump(isset($alumnos));

//contar un arreglo
echo count($alumnos);

//odenar de manera alfabética 
short($alumnos); // esta hace perder el índice en que se creo el arreglo
ashort($alumnos); // esto mantiene el indice de cada elemento
rshort($alumnos); // ordenamiento de manera inversa y este pierde el indice
arshort($alumnos); // ordenamiento de manera inversa pero mantiene el indice


//sumar los valores de un arreglo
array_sum($numeros);

//encontrar la difencia de pero de arreglos indexados
array_diff($array1, $array2); //devuelve los datos que no existen entre el otro arreglo


//dividir un arreglo
$dividir = array_chunk($alumnos, 3); // pasar el arreglo y cada 3 elementos lo divide
print_r($dividir);

//dividir y eliminar el anterior
$dividir = array_slice($alumnos, 3); // pasar el arreglo y cada 3 elementos lo divide
print_r($dividir);

//unir arreglos
$unirArreglos = array_merge($array1, $array2);


//eliminar el ultimo elemento del arreglo
$eliminarElmenento = array_pop($arreglo);


//agregar un elemento al final 
$agregarElementoArray = array_push($arreglo,'ultimovalor');


//buscar un elemento un arreglo
$buscarElementoArreglo = array_search(value,$arreglo); //devuelve la posición del elemento
```



## Errores

```php
//desactivar todo tipos de errores
error_reporting(0)
    
//guarda de errores en un log
    
ini_set('log_error',1);
ini_set('error_log',"/tmp/php-error.log");
error_log('errores de section tal');
```



## Estructura de control 

### condicionales 

```php
  $edad = 20;
//condicional normal
  if ($edad> 18) {
    echo "eres mayor de esdad";
  } else {
    echo "eres menor de edad";
  }

//condicional ternario
$edad > 18 ? print "eres mayor de esdad" :  print "eres menor de edad";

//switch
switch($dia){
   case 1: // identificar el valor
       echo 'lunes'; //hacer algo
       break;//  para salir de la condicional
   case 2: 
       echo 'martes';
       break;
   default: // ni no cumple ninguna ejecutar este código
     echo " no es un dia de la semana";
     break;
}
```

### Ciclos

```php
//====while (Mientras)========

while(condicion){
    //bloque de código
    //acción para detenerse
}

//======= do-while (Mientas que)======

declarar incremento
do{
   //bloque de codigo a repetir
   //acción para detenerse
}while(condition);


//======== for (para) =======

for ($i=0; $i < ; $i++) { 
  # code...
}

//======== foreach (para cada) ========
foreach ($arreglo as $row => $item) {
  # code...
}


```

## Funciones 

fragmentos de códigos bien definiditos con nombres para reutilizar código 

```php
// sintaxis
function FunctionName($argumentos, $active=false) //funciones con argumentos  y argumentos por defecto
{
      // # code...
      $process = 1 + 1; //hacer procesos
      return $process; //retorna un valor
}
FunctionName($parametros) // llamanar la funcción
    
    
//función anonima 
$despedida = function(){
    echo "hata pronto";
  };
$despedida();

//Closures

function closhures(Closure $funcion, $values){
    return $function($values);
}
```



## POO

Es un paradigma de programación, 

### Objeto

los objetos tienen datos y funcionalidad, los datos en programación orientada a objetos se llaman atributos y la funcionalidad se llaman métodos

### atributo

los atributos son las propiedades de un objeto

### métodos

los métodos son la funcionalidades de los objetos

### clases 

Es una plantilla o un molde que tiene una estructura básica para crear un objeto 

### Instanciar

Es el proceso de crear objetos a partir de la case se llama  instanciar

### Abstracción

pensar que atributos y métodos van a tener para crear las clases

### Encapsulamiento

para proteger la información de manipulación no autorizada, hay datos públicos, datos privados, datos protegidos métodos para acceder a cierta información 

### Polimorfismo

poder darle la misma orden a diferentes objetos y que cada uno de ellos responda de su propia manera 

### herencia

heredar los atributos de la clase padre y le se le agregan nuevos atributos a los hijos	



```php
//creación de una clase

class usuario // creamos nuestra clase
  {
    public $nombre; // sus atributos
    public $apellido;
    public $edad;
    public $estado;
    
     public function saludar(){ //creación de un método
      echo "hola mi nombre es: ".$this->nombre;
    }
  }

  $usuario1 = new usuario(); //instanciamos un nuevo usuario
  $usuario1->nombre = "juan"; //asignamos valor  alos atributos
  var_dump($usuario1); // mostramos el nuevo objeto
      
  //llamar una método
  
  $usuario1 -> saludar();	
  
```



### Accesos a  los métodos 

```php
class usuario{
    public $nombre = "Nombre"; // ES libre para todos
    private $DNI="1234"; // es restrigido solo puede ser accedido por los mienbros de la clase y clase
    protected $contraseña = "1245"; // solo los mienbros de las clases y las clases heredadas
    
    function obtenerMensajePivado(){
        echo "DNI: ".$this->DNI;
    }
}
```

### Constructor

la finalidad del constructor es poder agregarle obligatoriamente los parámetros, cumple con 3 funciones asignación de datos privados al momento de instanciar, definir las propiedades obligatorias, poder ingresar los datos en el momento de instanciar un objeto

```php
 <?php
  class usuario
  {
    private $nombre;
    private $apellido;
    private $edad;
    private $estado;

    public function __construct($nombre,$apellido,$edad,$estado) //constructor 
    {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->edad = $edad;
      $this->estado = $estado;
    }

    public function saludar(){
      echo "hola mi nombre es: ".$this->nombre;
    }
    function mostrarDni(){
      echo "DNI: ".$this->dni;
    }

  }

  $usuario1 = new usuario("Jerry","Apaza",30,false);
  print_r( $usuario1);

```

### Encapsulamiento

Para el encapsulamiento tenemos los getter(Para obtener datos) y setters(para asignar datos) 

```php
class usuario
  {
    private $nombre;
    private $apellido;
    private $edad;
    private $estado;

    public function __construct($nombre, $apellido, $edad, $estado)
    {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->edad = $edad;
      $this->estado = $estado;
    }
    #getter
    public function obtenerNombre()
    {
      echo $this->nombre;
    }
    #setter
    public function asignarNombre($nombre)
    {
      $this->nombre = $nombre;
    }
  }

  $usuario1 = new usuario("Jerry", "Apaza", 30, false);
  $usuario1-> obtenerNombre();

  // $usuario1->nombre="juan";
  $usuario1->asignarNombre('Juan');
  $usuario1-> obtenerNombre();

  ?>
  //se podria decir que esto es la forma correcta de programar
```

### Interfaces

Nos permite agrupar un conjunto de declaraciones sin especificar el nombre el tipo de retorno y los argumentos todo esto se define en una sola clase y es posible utilizar interfaces múltiples y las interfaces son como lo requerimientos para instanciar un objeto, las interfaces tienen una serie de características: no pueden definir atributos solamente nos van a definir una función, tampoco pueden tener métodos definidos con su algoritmo correspondiente, las interfaces tampoco se pueden instanciar, todas los métodos en un interface siempre tienen que ser públicos, no se pueden llamar igual que una clase, básicamente con la interfaz vamos a poder definir cuales son lo métodos necesarios para que se pueda definir después en un clase 

```php
 interface Conocimiento{
    public function asignarConocimiento($lisdato);
    public function optenerConocimiento();
  }

  class usuario implements Conocimiento
  {
    private $nombre;
    private $apellido;
    private $edad;
    private $estado;
    private $lisdato;

    public function __construct($nombre, $apellido, $edad, $estado)
    {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->edad = $edad;
      $this->estado = $estado;
    }
    #getter
    public function obtenerNombre()
    {
      echo $this->nombre;
    }
    #setter
    public function asignarNombre($nombre)
    {
      $this->nombre = $nombre;
    }
      
    #implementar las funciones de interfaces 
    public function asignarConocimiento($lisdato)
    {
      $this->lisdato = $lisdato;
    }
    public function optenerConocimiento()
    {
      if(!empty($this->lisdato)){
        foreach ($this->lisdato as $row) {
          echo '<p>'.$row.'</p>';  
        }
      }
    }


  }

  $usuario1 = new usuario("Jerry", "Apaza", 30, false);

  $usuario1-> asignarConocimiento(['va a aprender el programación','poo','php desde cero']);
  $usuario1-> optenerConocimiento();
	
  ?>
```

  

### Destructor

Destruye, esto nos sirve especialmente cuando tenemos muchos usuarios en memoria y los procesos están lentos 

```php
#destructor

    public function __destruct()
    {
      echo "destruyendo".$this->nombre;
    }
```

### Propiedades estáticas

 y estas se utilizan para declarar atributos y métodos a los que se puede acceder sin crear una instancia de clase  

```php
  interface Conocimiento{
    public function asignarConocimiento($lisdato);
    public function optenerConocimiento();
  }

  class usuario implements Conocimiento
  {
    private $nombre;
    private $apellido;
    private $edad;
    private $estado;
    private $lisdato;
    
    #atributo estático 
    public static $moneda = 'USD';

    public function __construct($nombre, $apellido, $edad, $estado)
    {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->edad = $edad;
      $this->estado = $estado;
    }
    #destructor

    // public function __destruct()
    // {
    //   echo "destruyendo".$this->nombre;
    // }
    #getter
    public function obtenerNombre()
    {
      echo $this->nombre;
    }
    #setter
    public function asignarNombre($nombre)
    {
      $this->nombre = $nombre;
    }
    #implementar las funciones de interfaces 
    public function asignarConocimiento($lisdato)
    {
      $this->lisdato = $lisdato;
    }

    public function optenerConocimiento()
    {
      if(!empty($this->lisdato)){
        foreach ($this->lisdato as $row) {
          echo '<p>'.$row.'</p>';  
        }
      }
    }

    #mostrar el dato de la propiedad estatica
    static function optenerMoneda(){
      return self::$moneda; // de esta forma podemos ingresar a los datos estáticos 
    }

  }

  $usuario1 = new usuario("Jerry", "Apaza", 30, false);

  echo $usuario1-> optenerMoneda();
  echo $usuario1::$moneda; // de esta forma podemos ingresar a los datos estaticos 
```



### Herencia

heredan propiedades y métodos de las clases heredadas

```php
//clase principal o clase padre
class Persona
  {
    private $nombre;
    private $apellido;
    private $email;

    public function __construct($nombre, $apellido, $email)
    {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->email = $email;
    }

    public function bienvenida()
    {
      return "Bienvenida " .$this->nombre;
    }
    public function despedida(){
      return "Hasta pronto ".$this->nombre;
    }
  }
	//clses hijo como estudiante
  class Estudiante extends Persona{

    private $pais;

    public function __construct($nombre, $apellido, $email,$pais)
    {
      parent::__construct($nombre,$apellido, $email); // asignar constructor 
      $this->pais = $pais;
    }
  }
//clase hijo como profesor
  class Profesor extends Persona{
    //===== no se puede hacer esto con los constructores======
    // private $cargoCurso;
    // public function __construct($cargoCurso){
    //   $this->cargoCurso = $cargoCurso;
    // }
     
  }

  $usuario1 = new Estudiante("Jerry","apaza","jerryapaza@gmail.com",'peru');
  echo"<br>";
  print_r($usuario1);
  echo"<br>";
  echo $usuario1->bienvenida();
  
  $profesor = new Profesor('Juan',"gomez",'juangomez@gmail.com');
  echo"<br>";
  print_r($profesor);
  echo"<br>";

  echo $profesor->bienvenida();
```



### Polimorfismo

mas de una forma que pueda funcionar o sobre escribir un método 

```php
 class Persona
  {
    public $nombre;
    public $apellido;
    public $email;

    public function __construct($nombre, $apellido, $email)
    {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->email = $email;
    }

    public function bienvenida()
    {
      return "Bienvenida " . $this->nombre;
    }
    public function despedida()
    {
      return "Hasta pronto " . $this->nombre;
    }
  }

//estudiante
  class Estudiante extends Persona
  {

    private $pais;

    public function __construct($nombre, $apellido, $email, $pais)
    {
      parent::__construct($nombre, $apellido, $email);
      $this->pais = $pais;
    }
	//sobre escribir el método
    public function bienvenida()
    {
      return "Bienvenido estudiante {$this->nombre}";
    }

  }
  
  //profesor
  class Profesor extends Persona
  {
      //sobre escribir el método
    public function bienvenida()
    {
      return "Bienvenido Profesor {$this->nombre}";
    }
  }

  $usuario1 = new Estudiante("Jerry", "apaza", "jerryapaza@gmail.com", 'peru');
  echo "<br>";
  print_r($usuario1);
  echo "<br>";
  echo $usuario1->bienvenida();

  $profesor = new Profesor('Juan', "gomez", 'juangomez@gmail.com');
  echo "<br>";
  print_r($profesor);
  echo "<br>";
  echo $profesor->bienvenida();
```

### Heredar super clases

```php
//Creamos un super clase padre para todos estos funciona tal cual como un clase pero utilizando la palabra reservada  le decimos que es una super clase
trait Compra{
  private $compra;
  function validarCompra(){
    return "Compra exitosa";
  }

}


  class Persona
  {
    public $nombre;
    public $apellido;
    public $email;
	//con esto llamamos a las super clases 
    use Compra; //podemos agregar mas trait separados por comas

    public function __construct($nombre, $apellido, $email)
    {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->email = $email;
    }

    public function bienvenida()
    {
      return "Bienvenida " . $this->nombre;
    }
    final public function despedida()
    {
      return "Hasta pronto " . $this->nombre;
    }
  }

//estudiante
  class Estudiante extends Persona
  {

    private $pais;

    public function __construct($nombre, $apellido, $email, $pais)
    {
      parent::__construct($nombre, $apellido, $email);
      $this->pais = $pais;
    }

    public function bienvenida()
    {
      return "Bienvenido estudiante {$this->nombre}";
    }

  }
  
  //profesor
  class Profesor extends Persona
  {
    public function bienvenida()
    {
      return "Bienvenido Profesor {$this->nombre}";
    }
  }

  $usuario1 = new Estudiante("Jerry", "apaza", "jerryapaza@gmail.com", 'peru');
  echo "<br>";
  print_r($usuario1);
  echo "<br>";
  echo $usuario1->bienvenida();
  echo "<br>";
  echo $usuario1->validarCompra();

  $profesor = new Profesor('Juan', "gomez", 'juangomez@gmail.com');
  echo "<br>";
  print_r($profesor);
  echo "<br>";
  echo $profesor->bienvenida();
```



### Constantes 

```php
const MONEDA ="USD"; // para crear una constante en una clase 
echo $usuario1::MONEDA; // para llamar a una constante
```



## Manejo de excepciones

una excepción Es un objeto que esta  almacenan los errores que podamos tener  te permite agregar dos argumentos uno es el mensaje y el otro que es el error

```php
trait Compra{
    private $compra;
    function validarCompra()
    {
      return "Compra exitosa";
    }
  }

  class Persona{
    const  MONEDA = "USD";
    public $nombre;
    public $apellido;
    public $email;

    use Compra; //podemos agregar mas trait separados por comas

    public function __construct($nombre, $apellido, $email){
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->email = $email;
      $this->correoValido($this->email);

    }

    public function correoValido($email){
      try {
        if (filter_var($email, FILTER_VALIDATE_EMAIL) === false) {
          throw new Exception('Correo no valido');
        }
      } catch (Exception $e) {
        echo $e->getMessage();
      }
    }
    
    public function bienvenida(){
      return "Bienvenida " . $this->nombre;
    }
    final public function despedida()
    {
      return "Hasta pronto " . $this->nombre;
    }
  }

  //estudiante
  class Estudiante extends Persona{

    private $pais;

    public function __construct($nombre, $apellido, $email, $pais)
    {
      parent::__construct($nombre, $apellido, $email);
      $this->pais = $pais;
    }

    public function bienvenida(){
      return "Bienvenido estudiante {$this->nombre}";
    }
  }

  //profesor
  class Profesor extends Persona{
    public function bienvenida(){

      return "Bienvenido Profesor {$this->nombre}";
    }
  }

  $usuario1 = new Estudiante("Jerry", "apaza", "jerryapaza@gmail.com", 'peru');

  echo "<br>";
  print_r($usuario1);
  echo "<br>";
  echo $usuario1->bienvenida();
  echo "<br>";
  echo $usuario1->validarCompra();
  echo "<br>";
  echo $usuario1::MONEDA;

  $profesor = new Profesor('Juan', "gomez", 'juangomez@gmail.com');
  echo "<br>";
  print_r($profesor);
  echo "<br>";
  echo $profesor->bienvenida();
```

 

## Conexión base de datos

```php
function conecta(){
      try {
        $cadena = 'mysql:host=localhost;dbname=proyecto;charset=utf8';
        $conexion = new PDO($cadena,'root','');
        return true;

      } catch (PDOException $e) {
        echo "ERROR: ".$e->getMessage();
      }
}
//conexion con php
```































## Funciones Propias de php 

* `get_called_class()`: Para mostrar el nombre de la clase dentro de un método 
* `__dir__`: lo que nos trae la ruta principal del proyecto
* 

