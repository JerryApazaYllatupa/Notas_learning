

## Funciones de strings

## ``explode()``

- `expode( string $delimiter , string $string [, int $limit = PHP_INT_MAX ] ) : array`: Divide un string en varios strings, y este devuelve un array de string, siendo cada uno un substring del parámetro `string` Formado por la división realizado por los delimitadores indicados en el parámetro `delimiter` 

```php
delimiter // se pasa un delimitador como " ", "-" que caracter tiene el string con lo que pueda separa ese estring 
string // En este parmetro se pasa el estring 
    
limit // Si el parámetro limit es positivo El array devuelto contendra de limit elementos y el ultimo elemento contendra el resto del string 
    //si el parámetro limit es negativo, Se devolvera todos los componentes a excepcion del ultimo  -limit 
    //si el parámetro es cero, se tratará como un 1 
    
```

### Valores devueltos 

devuelve un array de string creado por la división del parámetro 

 Si `delimiter` es un [string](https://www.php.net/manual/es/language.types.string.php) vacío (""), **explode()** devolverá **`FALSE`**. Si `delimiter` contiene un valor que no forma parte del parámetro `string` y se utiliza un `limit` negativo, entonces devolverá un [array](https://www.php.net/manual/es/language.types.array.php) vacío, en caso contrario se devolverá un [array](https://www.php.net/manual/es/language.types.array.php) que contiene el valor de `string`. 

Ejemplos

```php
//Ejemplo 1
$pizza  = "porción1 porción2 porción3 porción4 porción5 porción6";
$porciones = explode(" ", $pizza);
echo $porciones[0]; // porción1
echo $porciones[1]; // porción2

// Ejemplo 2
$datos = "foo:*:1023:1000::/home/foo:/bin/sh";
list($user, $pass, $uid, $gid, $gecos, $home, $shell) = explode(":", $datos);
echo $user; // foo
echo $pass; // *
```

```php
/* 
   Un string que no contiene el delimitador simplemente 
   devolverá un array de longitud uno con el string original. 
*/
$entrada1 = "hola";
$entrada2 = "hola,qué tal";
var_dump( explode( ',', $entrada1 ) );
var_dump( explode( ',', $entrada2 ) );
//Resultado
array(1)
(
    [0] => string(4) "hola"
)
array(2)
(
    [0] => string(4) "hola"
    [1] => string(8) "qué tal"
)

```

 **Ejemplo #3 Ejemplos del parámetro `limit`** 

```php

$str = 'uno|dos|tres|cuatro';

// límite positivo
print_r(explode('|', $str, 2));

// líimte negativo (desde PHP 5.1)
print_r(explode('|', $str, -1));

// Array
(
    [0] => uno
    [1] => dos|tres|cuatro
)
Array
(
    [0] => uno
    [1] => dos
    [2] => tres
)
```



### Reestructurar un arreglo en php

```php
$dates = ['nombre', 'edad', 'email', 'email', 'email', 'email', 'email', 'email'];
list($user, $pass, $uid, $gid, $gecos, $home, $shell) = $dates;
echo $user;
echo "<br>";
echo $pass;
echo "<br>";
echo $uid;
echo "<br>";
echo $gid;
echo "<br>";
echo $gecos;
echo "<br>";
echo $home;
echo "<br>";
echo $shell;
//Respuesta 
nombre
edad
email
email
email
email
email
```

