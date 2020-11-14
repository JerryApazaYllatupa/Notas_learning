[TOC]

# Python desde cero

## Pequeña Historia de Python

> Python es un lenguaje de programación versátil, fácil de aprender, interesante y bastante útil. Origen se retorna a finales de 1980 cuando ***Guido Van Rossum*** lo ideo. 

*Guido Van Rossum escribió en 1996:*

> "Hace seis Años, en diciembre de 1989, estaba buscando un proyecto de programación como hobby que me mantuviera ocupado durante las semanas de navidad. Mi oficina estaría cerrada y no tendría mas que mi ordenador de casa a mano. Decidí escribir un intérprete para el nuevo lenguaje de scripting que había estado ideando recientemente: un descendiente de ABC que gustaría a los hackers de UNIX. Elegí el nombre de Python para el proyecto, encontrándome en un estado de ánimo ligeramente irreverente(Siendo un gran fan de Monty Python's Flying Circus) "

*En el año 2000 agregó*

> "El predecesor de Python, ABC, estaba inspirado en SELT  Lambert Meertens se paso un año trabajando en el grupo del SELT en la universidad de Nueva York antes de que surgiera el diseño final ABC.6"



## Introducción al documento

En este documento iremos explicando paso a paso sobre Python, iremos viendo desde las variables hasta los mas complejo, para ello esto no es un libro, pero haré lo mejor posible para poder explicarle como funciona Python y como podrá entender y practicarlo cada código  que iremos aplicando a lo largo del documento.

## Introducción a Python 

Python es un lenguaje interpretado de alto nivel por poseer una estructura sintáctica y semántica legible acorde a las capacidades cognitivas humanas. Además este lenguaje no requiere de un compilador para ser ejecutado sino de un interprete, el cual ejecuta un programa directamente, sin necesidad de generar previamente un ejecutable.

Python es dinámicamente tipado, esto es la capacidad que posee python, en no requerir la definición del tipo de datos en las variables, auto asigna el tipo de dato según el valor asignado 

## Puntos importante de Python

- Python no te muestra el error en cuando se digita el código, te muestra cuando se ejecuta Python es interpretado 

## Variables 

- En las variables no se pueden sumar diferentes tipos de datos
- En Python no existe las constantes
- Las variables son flexibles osea que pueden cambiar sus datos 



### Declarar  una variable 

```python
a = "Hola mundo"
print(a)  # "Hola mundo"
```

## Tipos de datos 

### Cadena(Strings)

```python
cadena = "texto"
cadena = 'texto'
cadena = """texto"""
```

### Numeros(Numbers )

```python
#Número entero: 
edad = 35
#Número entero hexadecimal:
edad = 0x23

```

### Flotantes(Foat)

```python
flotante = 12.5045
```

### Boolean(Boolean)

```python
verdadero = True 
falso = False
#Importante: los booleanos empiezan siempre con mayúscula 
```

## Tipos de datos complejos 

### Tuplas 

Una tupla es una variable que permite almacenar varios tipos de datos inmutables, ¿por que se dice inmutable ?  por que no pueden ser modificados una vez creados de tipos diferentes 

```python
#Declaración ()
mi_tupla  = ('cadena de texto', 15, 2.8, 'otro dato', 25,True)

#Mostrar datos de una tupla
print(mi_tupla)       # ('cadena de texto', 15, 2.8, 'otro dato', 25, True)
print(mi_tupla[2])	  # 2.8
print(mi_tupla[1:3])  # (15, 2.8)
print(mi_tupla[:3])   # ('cadena de texto', 15, 2.8) // Los 3 primeros
print(mi_tupla[3:])   # ('otro dato', 25, True) // Los 3 ultimos

```

### Listas

Una lista es parecida a una tupla con la diferencia fundamental de que esta permite modificar los datos una vez creados (Esto seria como un array en otros lenguajes)

```python
#Declaración []
mi_lista  = ['cadena de texto', 15, 2.8, 'otro dato', 25,True]

#Mostrar datos de una lista
print(mi_lista)       # ['cadena de texto', 15, 2.8, 'otro dato', 25, True]
print(mi_lista[2])	  # 2.8
print(mi_lista[2:4])  # [2.8, 'otro dato']


#Modificar un dato 
mi_lista  = ['cadena de texto', 15, 2.8, 'otro dato', 25,True]
print(mi_lista)  # Primer valor:  ['cadena de texto', 15, 2.8, 'otro dato', 25, True]

mi_lista[0] = 22222
print (mi_lista) # Segundo valor: [22222, 15, 2.8, 'otro dato', 25, True]
```

### Diccionarios

Los diccionarios a diferencia que las anteriores este nos permite guardar datos con una clave para declarar y acceder a un valor (esto seria como un objeto en JavaScript y JSON o array asociativo en php )

```python
#Declaración
usuario = {'nombre':'Juan', 
           'edad':20, 
           'email':'juan@gmail.com'
          }


#Mostrar Datos 
usuario['nombre']  # Juan
usuario['email']   # juan@gmail.com

#Modificar Datos
print(usuario['nombre'])  # Juan
usuario['nombre'] = 'Lucas'  
print(usuario['nombre'])  # Lucas

# Ingresar nuevos datos
print(usuario) 	#{'nombre': 'Juan', 'edad': 20, 'email': 'juan@gmail.com'}
usuario['pais'] = 'EE.UU'
print(usuario)	#{'nombre': 'Lucas', 'edad': 20, 'email': 'juan@gmail.com', 'pais': 'EE.UU'}

```

Mas adelante iremos explicando cada una de las funciones que podemos aplicar en los tipos de datos 

## Comentarios

```python
# Comentario de linea
''' 
 Comentario de bloque 
'''
```

## Operadores Aritméticos 

Entre los operadores aritméticos que python utiliza podemos encontrar los siguientes 

```python
+ # mas, suma 
a = 2 + 2  # 4

- # resta, negación 
a = 4 - 2  # 2
-5 

* # multiplicación
a = 4 * 2  # 8

** # exponente
a = 2 ** 3  # 8

/ # divicción
a = 12.5 / 2  # 6.25

// # divición entera
a = 12.5 // 2  # 6

% # modulo 
a = 27 % 4  # 3

```

## Identación 

Para hablar de las estructuras de control de flujo en Python, es imprescindible primero, hablar de la identación 

### ¿Que es la identación  ?

la identación en python es muy importante y obligatoria tenerlo en cuenta ya que de esto dependerá su estructura, esto lo tiene python para la mejor legibilidad de código lo recomendable para indentación es tener 4 espacios veamos como podemos representar la identación 

```python
if validacion :
---- expresiones
for validation :
---- expresión 
```

##  Asignación múltiple 

Otra de las ventajas que nos trae python es poder asignar en una sola instrucción múltiples variables 

### Asignación a variables

```python
a, b, c = 'string', 15, True
print(a)  # string
print(b)  # 15
print(c)  # true
```

### Extracción de una tupa

```python
mi_tupla = ('Juan',20,'Peru')

nombre,edad,pais = mi_tupla

print(nombre) 	# Juan
print(edad) 	# 20
print(pais)		# Peru

```

### Extracción de una Lista

```python
mi_lista = ['Argentina', 'Buenos Aires']

pais, provincia = mi_lista

print(pais)      # Argentina
print(provincia) # Buenos Aires		
```

La asignación múltiple de variables, también pude darse utilizando como valores en las tuplas listas diccionarios 

## Estructuras de control 

Para entender las estructuras de control, vamos ver los operadores relacionales y operadores lógicos 

### Operadores relaciones  (de comparación)

```python
== 	# Igual que 
5 == 2  # False (falso)

!= 	# Distinto que
rojo != verde  # True (verdadero)

< 	#Menor que 
2 < 4  # True

>	#Mayor que 
8 > 4  # True

<=  #Menor igual que 
4 <= 4  # True

>= #Mayor igual que
4 >= 5  # False

```

Una estructura de control, es un bloque de código que permite agrupar instrucciones de manera controlada 

### Condicionales

Estas estructuras de control condicionales, son aquellas que nos permiten evaluar si una o más condicionales se cumplen, Para decir que acción vamos a ejecutar. La evaluación de condicionales, Solo puede retornar  `True` o `False` 

y para evaluar más de una condición simultáneamente, se utilizan operadores lógicos 

### Operadores lógicos 

```python
and  # (Y) 
2 == 2 and  5 > 2 	# 1(True) y 1(True) = True
5 == 7 and 7 < 12   # 0(False) y 0(False) = False
9 < 12 and 12 > 15  # 1(True) y 0(False) = Falso


or  # (O)
12 == 12 or 15 < 7	# 1(True) o 0(False) =  True
7 > 5 or 9 < 12     # 1(True) o 1(True) = True


```

 

### if  elif  else

las estructuras de control de flujo condicionales, se definen mediante el uso de 3 palabras claves reservadas `if` (Sí), `elif`(Sino, si), `else`(Sino)	

```python
number= int(input("Por favor ingresa un número: "))
Please enter an integer: 42
if number < 0:
    print('Es numero negativo')
elif number == 0:
    print('Es cero')
elif number == 1:
    print('Es 1')
else:
    print('Es mas de 1')
    
#Otra caracteristica de las condicionales en python es que podemos anidar condiciones
a = 2
b = 2
c = 2

if a == b == c:
    print("Son todos iguales")

```

y así puedes validar los diferentes problemas y anidar a tu gusto 

## Estructura de control iterativas

Las  iterativas (También llamadas cíclicas o bucles) , Nos permiten ejecutar un mismo código, de manera repetitiva Mientras se cumpla la condición 

### for

El for en python trabaja muy distinto a otros lenguajes de programación. En lugar de iterar siempre sobre un rango de números aritméticos o darle la capacidad de la incrementación. En python el `for` itera sobre los elementos de cualquier secuencia ya sea una (lista o una cadena)  

```python
#Iteración de nuemeros
for i in range(1,10):
    print(i, end=' ')  # 1 2 3 4 5 6 7 8 9
    
#Iteración de una palabra
palabras = "Juan"
for caracter in  palabras:
    print(caracter)
    # J
    # u   
    # a
    # n  
    
#Romper un for
for i in range(2,20,2):
    print(i, end=' ')
    if(i==10):
        break
       
# 2 4 6 8 10

#Continuar un for
for i in range(2,20,2):
    print(i, end=' ')
    if(i==10):
       continue 
    
 # 2 4 6 8 10 12 14 16 18

for i in range(10):
    print(i)
    if(i == 5):
        continue;
else:
    print('El siclo ya termino')
```

### While

```python
# La sintaxis de while
i =0
while i<=10 :
    print(i)
    i+=1
# 1 2 3 4 5 6 7 8 9
```

## Funciones

Con la palabra clave `def` podemos crear funciones las funciones nos permiten reutilizar código 

### Función simple

```python
def saludo():
    print("HelloW Words")

saludo() #Hello Word
```

### Función con argumentos 

```python
def mostrarNombre(nombre):
    print('Hola mi nombre es: ',nombre)
    
mostrarNombre('Juan') 	# Hola mi nombre es: Juan
```

### Funciones que retornan 

```python
def sumar(a,b):
    return a + b

print(sumar(2,4))	# 6

```

### Funciones con argumentos asignados 

En muchos de los casos utilizaremos esta funciones que permiten asignar valores por defecto a los argumentos y esto al momento de llamar la función podemos omitir estos parámetros .  Algo importante es que cuando tengamos que dar argumentos o parámetros a una función, es recomendable poner primero los argumentos que no tienen datos por defecto, y los argumentos que van a tener datos por defecto ponerlos al final.

```python
def mostrar_datos(nombre,edad=20,pais="Peru"):
    return 'Nombre:{} edad:{} pais:{}'.format(nombre,edad,pais)

print(mostrar_datos('Juan')) 	# Nombre:Juan edad:20 pais:Peru

```

### Llamar a las funciones con las palabras claves

En las llamadas a las funciones podemos utilizar las palabras claves que declaramos como argumentos en una función por ejemplo

```python
def mostrar_datos(nombre,edad=20,pais="Peru"):
    return 'Nombre:{} edad:{} pais:{}'.format(nombre,edad,pais)

print(mostrar_datos('Juan', pais='EE.UU')) 	# Nombre:Juan edad:20 pais:EE.UU 
```

Y en este ejemplo podemos ver que hemos omitido el segundo parámetro y podemos asignar los valores llamando directamente a las palabras claves en cualquier orden. Esto usualmente se utiliza cuando tenemos muchas parámetros y no vamos estar viendo todavía el orden

```python
def mostrar_datos(nombre,edad=20,pais="Peru"):
    return 'Nombre:{} edad:{} pais:{}'.format(nombre,edad,pais)

print(mostrar_datos(edad=50,nombre='Juan', pais='EE.UU')) # Nombre:Juan edad:50 pais:EE.UU
```

Pasar argumentos a  una función con palabras claves que son estas `*nombre_parametro` cuando pasamos con este asterisco y su nombre del argumento,  le estamos diciendo que la función va recibir una tupla como parámetro, Pero no el clásica tupla en `()` sino de diferente forma que un momento lo vemos  y la otra palabra clave es ``**nombre_variable`` si le pasamos otro argumento con dos asteriscos al inicio, le estamos diciendo a la función que en ese parámetro va revibir un diccionario, Pero también esto se les va pasar de diferentes formas , vemos un ejemplo   `*name` debe aparecer antes `**name`). 

```python
def mostrar_dato (text_normal,*tupla,**diccionario):
    print("Este es un parámetro normal: ",text_normal)
    print("-"*40)
    for el in tupla:
        print("Este es un elemento del tupla: ",el)
    print("-"*40)

    for el in diccionario:
        print(el," : ", diccionario[el])

mostrar_dato('Casa','naranja','plátano','manzana', nombre="Juan",edad=50, pais="Peru")
#resultado 
'''
Este es un parámetro normal:  Casa
----------------------------------------
Este es un elemento del tupla:  naranja
Este es un elemento del tupla:  plátano
Este es un elemento del tupla:  manzana
----------------------------------------
nombre  :  Juan
edad  :  50
pais  :  Peru
'''
```

### Parámetros especiales 

Lo que vimos asta este momento sobre las funciones es que podemos pasar los parámetros, ya sea por posición, es decir en el orden en que pusimos los argumentos,  y el otro que es explícitamente por palabra clave 

Python tiene este caracteres especiales, Para  poder facilitar la lectura y el rendimiento, y es esto de que podemos restringir la forma en que podemos pasar los argumentos, ¿y cuales formas? que podemos restringir que solo se puedan pasar a los argumentos de la función, por posición o solo por palabras claves o talvez ambos

```python
def fn(pos1, pos2, /, pos_o_pl, *, pl1, pl2):
      -----------    ----------     ----------
        |             |                  |
        |     posicion or palabra_clave  |
        |                                - solo palabra clave
        -- solo posicion
```

Bueno talvez no lo entiendas,  pero vamos explicando mas a detalle y cuando entiendas vuelve a este gráfico 

Estos `,/`y `*,` nuevos símbolos son opcionales en una función, ¿que es lo que cumplen estos símbolos?, bueno vamos a ello, Para pasar los parámetros a una función podemos restringir de 3 formas que son; 1 pasar parámetros por posición y palabra clave, esto es como el por defecto, `parametro`,  2 cuando solo queremos pasar parámetros por posición, `,/` con esto indicamos que ese parámetro  solo se va a pasar por posición, pero esto símbolo se tiene que pasar después de los argumentos, 3 cuando queremos pasar solo por palabras claves `*,` este símbolo se coloca antes de los argumentos que quieres que se pasen por palabra clave. si no se entiende vamos a explicar más a detalle

### Argumentos de posición o palabra clave 

Este seria el por defecto de los argumentos que pasamos a una función, no necesita de ningún símbolo 

```python
def arguemtnos_estadar(arg):
	print(arg)
    
#ejecutar función 
arguemtnos_estadar('hola') #hola 
```

### Parámetros solo posicionales

Este seria la restricción que solo queremos que se pasen por posición y el símbolo es `,/` y como indicamos este se tiene que pasar después de los argumentos 

```python
def solo_posicion(arg1, arg2,/):
    print(arg1, ' ', arg2)
    
#ejecutar función p
solo_posicion(1,2) # 1 2
solo_posicion(arg1=1, arg2=2) #error por que esta restringido solo por posición  
```

###  Argumentos de solo palabras clave 

Este seria la restricción  que solo queremos que se pasen por palabra clave no importa la posición y se coloca este `*,` antes des los argumentos 

```python
def solo_paralabra_clave(*, arg1,arg2):
    print( arg1 , arg2)

solo_paralabra_clave(2,5) #error por que solo permitimos pasar por palabra clave

solo_paralabra_clave(arg2=2, arg1=5) #  5 2
```

Mezclando  todas las restricciones 

```python
def combinacion_restrincion_argumentos(arg1,arg2,/,arg3,*,arg4,arg5):
    print(arg1,arg2,arg3,arg4,arg5)

combinacion_restrincion_argumentos(1,2,3,4,5) # error
combinacion_restrincion_argumentos(arg1= 1, arg2= 2,arg3= 3, 4,5) #error
combinacion_restrincion_argumentos(1,2,3,arg4= 4,arg5=5)  # 1 2 3 4 5 
```

### Resumen

-  Use posicional si solo desea que el nombre de los  parámetros no este disponible para el usuario. Esto es útil cuando el nombre de los parámetros no tiene un significado real, y el objetivo imponer al usuario a ingresar en el orden correcto 
- Use palabras clave cuando los nombres tengan significado y la definición de la función sea mas comprensible y si desea que el usuario confié en los parámetros que esta pasando 
-  Para una API, use solo posicional para evitar que se rompan los cambios de la API si el nombre del parámetro se modifica en el futuro. 

### Lista de argumentos arbitrarios

Finalmente tenemos la opción menos usada, es especificar que se pueden llamar a la función con un sin fin de argumentos, estos argumentos serán envueltos en una tupla y la palabra clave `*arguments`

```python
def concat(*args,sep="/"):
    print(sep.join(args))

concat('29','11','1998')  # 29/11/1998
concat('29','11','1998', sep='-') 	# 29-11-1998
```

### Desempacando lista de argumentos

Esta situación acurre cuando las parámetros ya están en una lista  o tupla pero necesitan ser desempaquetados para una llamada de una función  que requiere argumentos posicionales separados, Veamos un ejemplo de la función `range(inicio,fin) `: esta función necesita por ejemplo estos parámetros `inicio` que no es obligatoria, pero es de ese valor que iniciara y el parámetro `final` donde terminará su recorrido, Pero que podemos hacer si estos parámetros los tenemos definidos en una lista, veamos un ejemplo, Pero para desempaquetar una lista o tupa tenemos el símbolo `*arg`  y para desempaquetar un diccionario tenemos `**dic`

```python
arg = [2,10]
print(list(range(*arg)))   # [2, 3, 4, 5, 6, 7, 8, 9]
```

Y este pequeño devuelve una lista ya que lo estamos creando directamente utilizando la función `range()`. Ahora veamos otro ejemplo si ya tenemos los parámetros en un diccionario

```python
def saludar(nombre,edad=20,pais="peru"):
    print('Hola me llamo: ', nombre, ' y tengo: ',edad, ' años y soy de: ',pais)


usuario = {'nombre':'JUAN','edad':'50','pais':'PERÚ'}

saludar(**usuario)  # Hola me llamo:  JUAN  y tengo:  50  años y soy de:  PERÚ
```

Ya casi terminamos sobre las funciones  ahora  vamos a ver como documentarlos para otros desarrolladores 

### Documentación de una función con comentarios 

Es una convenciones sobre sobre el contenido y la forma correcta de hacer una documentación.

La primera línea siempre debe ser un resumen breve y conciso del propósito de la función, no se debe explicar explícitamente el nombre o tipo de función. Esta línea debe comenzar con la letra mayúscula y terminar con un punto. Si hay mas líneas en la cadena de documentación debe haber un espacio en blanco que separe ala primera línea que el resumen. Las siguiente líneas deben ser uno o más párrafos que pueden describir sus efectos secundarios 

¿Para que nos sirven estas documentaciones?,  generalmente cuando creamos librerías podamos facilitar esta documentación a los desarrolladores.

```python
def my_funcion():
    '''No hacer nada pero documentarlo

    No, en serio, no hacer nada
    '''
    
#Como mostramos ese mensaje  si queremos saber de que trata
print(my_funcion.__doc__)
#respuesta
No hacer nada pero documentarlo

    No, en serio, no hacer nada
```

 De esta forma podemos ver las pequeñas documentaciones de las funciones  y con la propiedad `.__doc__` ahora veamos otro ejemplo de una función clásica de python `range()`

```python
print(range.__doc__)

#respuesta 

range(stop) -> range object
range(start, stop[, step]) -> range object

Return an object that produces a sequence of integers from start (inclusive)
to stop (exclusive) by step.  range(i, j) produces i, i+1, i+2, ..., j-1.
start defaults to 0, and stop is omitted!  range(4) produces 0, 1, 2, 3.
These are exactly the valid indices for a list of 4 elements.
When step is given, it specifies the increment (or decrement).

Process finished with exit code 0
```

### Anotaciones de funciones

Las anotaciones de funciones, son información de metada datos  completamente opcionales  sobre los tipos utilizados.

Las anotaciones se almacenan en el `.__annotations__` atributo de la función como un diccionario y estos no tienen efecto en las funciones. Las anotaciones están definidas por dos puntos `:` después del nombre del argumento, seguido de una expresión que evalúa el valor del parámetro, es decir que podemos indicar que tipos de variable va recibir es parámetro, continuamos, también podemos indicar que tipo de valor va retornar esa función y se definen mediante el símbolo `->` seguido de la expresión entre la lista de los parámetros y entre los dos puntos que indican el final de la declaración de la función, veamos un ejemplo

```python
def mostrar_datos(nombre: str, edad: str, estado: str = "casado") -> str:
    return 'nombre: ' + nombre + ' edad: ' + edad + ' Estado: ' + estado


print(mostrar_datos('Juan','50'))  # nombre: Juan edad: 50 Estado: casado
```

## Estructuras de datos

En esta sección veremos sobre los métodos para los diferentes tipos de datos

### Métodos paras las listas

- `list.append(x)`: Agregar un valor al final de la lista, y este puede ser cualquier tipo de dato

  ```python
  country = ['Peru', 'Bolivia', 'Colombia', 'Brazil']
  country.append('Chile')	
  
  print(country) 	# ['Peru', 'Bolivia', 'Colombia', 'Brazil', 'Chile']
  ```

- `list.extend(iterable)`: Extiende la lista con los datos iterables, estos iterables pueden ser listas o tuplas

  ```python
  country.extend(['Chile', 'Argentina'])
  #forma 2
  country.extend(('Chile', 'Argentina'))
  
  
  ```

- ``list.``insert`(i, x)`:  Inserta un elemento en la posición indicada por el argumento `i` 

  ```python
  country.insert(2,{"name":"Jerry"})
  ```

- `list.remove(x)`: Elimina el primer elemento que concuerde con el argumento pasado, y si no encuentra, este devuelve un error

  ```python
  country.remove('Bolivia')
  ```

- `list.pop([i])`: Elimina en una posición pasada como argumento y este devuelve el valor eliminado, las paréntesis datas en el método, indican que son opcionales, ese argumente, en muchas documentaciones veras esta opción, bueno si no pasa ningún argumento, este eliminara el ultimo elemento de la lista 

  ```python
  country = ['Peru', 'Bolivia', 'Colombia', 'Brazil']
  
  
  print(country.pop(2))	# Colombia
  
  
  #usa pop para devolver el ultimo elemento de la lista
  print(country.pop())	# Brazil
  country[-1] 
  ```

- `list.clear()`: Elimina todos los elementos de una lista

  ```python
  country.clear()
  ```

- `list.index(x[start,[end]])`: Devuelve el índice del primer elemento encontrado, los demás parámetros son opcionales, `start`: para indicarle desde que posición quieres que se haga la búsqueda y `end`: indicarle hasta que posición se hará la búsqueda, y si no encuentra alguna coincidencia este devuelve un error `ValueError`

  ```python
  country = ['Peru', 'Peru','Peru','Peru', 'Bolivia', 'Colombia', 'Brazil']
  
  
  print(country.index('Peru'))		# 0
  print(country.index("Peru",2,3))	# 2
  
  ```

- `list.count(x)`: Devuelve el número de veces encontrado 

  ```python
  country = ['Peru', 'Peru','Peru','Peru', 'Bolivia', 'Colombia', 'Brazil']
  
  
  print(country.count("Peru")) 	# 4
  ```

  

- `list.sort(key=none,reverse=false)`: 

  ```python
  #Ordenar una simple lista
  names = ["Juan", "Pedro","Ana","Maria"]
  names.sort()
  print(names)
  
  # Ordenar una lista desde sus elementos
  users = [
      {"id": 1, "name": "Juan"},
      {"id": 5, "name": "Maria"},
      {"id": 4, "name": "Pedro"}
  ]
  
  def sortByElement(e):
      return e['id']
  
  users.sort(key=sortByElement)
  
  print(users) # [{'id': 1, 'name': 'Juan'}, {'id': 4, 'name': 'Pedro'}, {'id': 5, 'name': 'Maria'}]
  
  
  ```

- `list.reverse()`: Invierte los elementos de la lista

  ```python
  numbers = [1,2,3,4,5]
  numbers.reverse()
  print(numbers) 	# [5, 4, 3, 2, 1]
  
  ```

- `list.copy()`: Devuelve una copia superficial de la lista

  ```python
  names = ["Juan", "Pedro","Ana","Maria"]
  
  copyNames = names.copy()
  print(copyNames) #['Juan', 'Pedro', 'Ana', 'Maria']
  
  ```


### Compresiones de listas

Proporcionan una forma concisa de crear listas, algunos ejemplos de como crear listas, por ejemplo queremos crear listas de cuadrados 

```python
# Forma 1 de crear una lista
peers = list(range(0,10,2))
print(peers) 	# [0, 2, 4, 6, 8]

#form 2 
quares = []
for i in range(1,10):
    squares.append(i*4)

print(squares)	#[4, 8, 12, 16, 20, 24, 28, 32, 36]

#forma 3
squares = [x*4 for x in range(10)]

print(squares) #[0, 4, 8, 12, 16, 20, 24, 28, 32, 36]
```

- Crear una lista filtrada

  ```python
  # lista de datos desordenada
  numbers = list(range(15))
print(numbers) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]
  
  #Lista filtrada de datos externos
  pairNumbers = [x for x in numbers if x % 3 == 0]
  print(pairNumbers) # [0, 3, 6, 9, 12]
  ```
  
- Aplicar una función a todos los elementos de una lista

  ```python
  def duplicate(x):
      return  x * 2
  
  list = list(range(5))
  newList = [duplicate(x) for x in list]
  
  print(list)		#[0, 1, 2, 3, 4]
  print(newList) 	# [0, 2, 4, 6, 8]
  
  
  ```

- Llamar a un método para cada elemento 

  ```python
  countries = [" Peru"," Bolivia ", "Chile  "]
  print(countries) # [' Peru', ' Bolivia ', 'Chile  ']
  
  new_list_country = [country.strip() for country in countries]
  print(new_list_country) # ['Peru', 'Bolivia', 'Chile']
  ```

- Crear una lista con tuplas de números cuadrados 

  ```python
  list = [(x, x**2) for x in range(6)]
  print(list) # [(0, 0), (1, 1), (2, 4), (3, 9), (4, 16), (5, 25)]
  ```

- Sacar datos de listas hijas  y convertirlas en una

  ```python
  list = [ [1,2,3], [4,5,6],[7,8,9] ]
  new_list = [x for element in list for x in element ]
  print(new_list) # [1, 2, 3, 4, 5, 6, 7, 8, 9]
  
  ```

- Sacar los valores de una matrix 

  ```python
  matrix = [
       [1, 2, 3, 4],
       [5, 6, 7, 8],
       [9, 10, 11, 12],
   ]
  new_list = list(zip(*matrix))
  print(new_list)
  ```



### Declaración `del`

Con esta declaración también podemos eliminar datos de una lista, este se difiere de del método `pop(x)`, generalmente es usada para eliminar datos de de una lista, sea de cualquier forma, por índice, por rango, limpiar la lista, etc, con del podemos hacer todo los que hacen muchos métodos sobre eleminar

```python
# Eliminar un elemento del indice
names = ["Juan", "Pedro","Ana","Maria"]
del names[1]
print(names)	# ['Juan', 'Ana', 'Maria']


# Elimina un rango
names = ["Juan", "Pedro","Ana","Maria"]
del names[1:3]
print(names)	#['Juan', 'Maria']

#Eliminar todo 
names = ["Juan", "Pedro","Ana","Maria"]
del names[:]
print(names)	#[]
```

### Tuplas y secuencias 

Una tupla consta de una serie de valores separadas por comas, estas tupas no son necesarias las paréntesis al momento de asignación de datos  veamos algunos ejemplos,

Algunos casos que surgen a partir de la nueva información sobre las tuplas, son: que pasaría si deseo declara una tupa vacía o si que si tenga una dato, buenos vamos a ello como podemos resolver estos casos 

```python
# declaración de una tupla sin parentesis
t = 12344, 54321, 'hello!'
print(t[0])  # 12344	

# declaración de una tupla vacía 
tupla_vacia = ()

# Declaración de una tupla con un solo dato 
tupla = 1,
print(tupla)  # (1,)


#Desempaquetación de tuplas
t = 12345, 54321, 'hello!'
n1, n2, text = t

print(n1) #12345

```



### Conjuntos

Python también incluye un tipo de dato para conjuntos, un conjunto es una colección desordenada sin elementos duplicados, los usos básicos incluyen pruebas de membresía y eliminación de entradas duplicadas, los objetos de conjunto también admiten operaciones de matemáticas como unión, intersección, diferencia y diferencia simétrica.

Veamos con ejemplos

```python
basket = {'apple', 'orange', 'apple', 'orange', 'banana'}
print(basket)  # {'banana', 'apple', 'orange'}
```

Como podemos apreciar nos devolvió un conjunto de datos sin duplicaciones y que pasa si queremos crear un conjunto vacío , pues tenemos la función `set()`, y no `{}`, este ultimo nos crea un tipo de dato diccionario, veamos otros ejemplos

```python
a = set('abracadabra')
print(a)  # {'a', 'b', 'c', 'd', 'r'}
# Lo que hizo esta función fue crear un conjunto sin elementos repetidos

```

Algunas operación que se puede hacer con los conjuntos son:

```python
#  unir dos conjuntos y hacer la diferencia en este caso devuelve el valor del primer conjunto
a = set('abracadabra')
b = set('alacazam')
print(a - b)	# {'d', 'b', 'r'}

# unir a y b
a = set('abracadabra')
b = set('alacazam')

print(a | b)	#{'d', 'c', 'l', 'r', 'a', 'b', 'z', 'm'}

# devuelve las datos similares en ambos datos
a = set('abracadabra')
b = set('alacazam')

print(a & b) # {'c', 'a'}

# este Devuelve la comparación de ambos conjuntos pero solo los datos que no sean similares en ninguno de los conjuntos,
a = set('abracadabra')
b = set('alacazam')
print(a ^ b)	# {'b', 'd', 'r', 'm', 'l', 'z'}


```

Estos son temas muy complejos, pero con práctica les puede quedar y ser útil en algunas ocasiones, buenos sigamos al igual que las listas también podemos crear con los operadores de compresión, veamos un ejemplo

```python
sets = {x for x in 'abracadabra' if x not in 'abc'}
print(sets)  # {'r', 'd'}
```

Bueno hasta aquí sobre las listas ahora vayamos con los diccionarios

## Diccionarios

Los diccionarios es uno de los tipos de datos de python, los diccionarios en otros lenguajes serian como objetos o arreglos asociativos o matrices asociativas, una diferencia con las listas, las listas están indexadas por un rango de números es decir solo se pueden llamar por esos indices que son ese rango de números, en cambio un diccionario esta indexada por `clave` y `valor` .

Algo que nos dice la documentación de python es que las claves de un diccionario, pueden ser datos inmutables, es decir una cadena, un numero o las tuplas si solo contienen datos inmutables,como cadena o numero.

Como ya mencionamos anteriormente en este documento los diccionarios se crean con llaves `{}` y sus datos son clave y valor, véanlo siempre de esta forma `{"clave":"valor"}` y para tener mas elementos pues debemos separar con comas `{"clave":"valor", "clave2": "valor2"}`, los valores pueden contener cualquier tipo de dato

Explicando mas a detalle, las operaciones principales que se hacen con un diccionario son almacenar datos con `clave y valor` , para extraer datos tenemos que indicar la clave 

veamos algunos ejemplos 

- Declaración de  un dicionario

  ```python
  # Declaración normal
  usuario = {'nombre':'Juan','edad':20,'email':'juan@gmail.com'}
  
  # Declaración con las diferentes tipos de datos inmutables en las claves
  dictionary = { 1 : "numero", ('name','nombre'): "Juan", "name":"Maria"}
  
  print(dictionary[1])	# numero
  print(dictionary[(('name','nombre'))])	# Juan
  print(dictionary['name']) 	# Maria
  
  
  ```

- Modificar datos 

  ```python
  user = {'name':"Juan", 'age':20, "country":"Peru"}
  user['name'] = 'Pedro'
  
  print(user)	 # {'name': 'Pedro', 'age': 20, 'country': 'Peru'}
  ```

- Eliminar un valor 

  ```python
  user = {'name':"Juan", 'age':20, "country":"Peru"}
  del user['name']
  print(user)	#{'age': 20, 'country': 'Peru'}
  ```

- Obtener las claves 

  ```python
  user = {'name':"Juan", 'age':20, "country":"Peru"}
  print(list(user))
  
  ```

- Preguntar si un valor existe en el diccionario

  ```python
  user = {'name':"Juan", 'age':20, "country":"Peru"}
  print('name'in user)	# True
  print('married' not in user)	#True
  
  ```

El constructor `dict()` a  partir de una secuencia de datos `clave y valor`

```python
datas = [('Juan',20),('Pedro',30),('Maria',23) ]
users = dict(datas)
print(users)	#{'Juan': 20, 'Pedro': 30, 'Maria': 23}
```

También podemos crear diccionarios a partir de expresiones

```python
dictionary = {x: x**2 for x in (2, 4, 6)}
print(dictionary)

```

También cuando las claves son cadenas simples podemos utilizar el constructor  `dict()`

```python
users= dict(Juan=20,Pedro=30,Maria=40)

print(users) #{'Juan': 20, 'Pedro': 30, 'Maria': 40}

```

## Bucles 

Para obtener los datos de un diccionario también podemos utilizar el método `dict.items()`, este devuelve una lista con los valores en una tupla

```python
#Obtener datos
user = {'name':"Juan", 'age':20, "country":"Peru"}
print(user.items())	# dict_items([('name', 'Juan'), ('age', 20), ('country', 'Peru')])

#obtener y recorrer 
user = {'name':"Juan", 'age':20, "country":"Peru"}
for key, value in user.items():
    print(key ,": ", value)

# Respuesta
name :  Juan
age :  20
country :  Peru
```

Al recorrer un secuencia de datos el indice y valor se pueden recuperar al mismo tiempo utilizando el función `enumerate()` 

```python
user = {'name':"Juan", 'age':20, "country":"Peru"}

for key, value in enumerate(user):
    print(key ,": ", value)
    
 '''
0 :  name
1 :  age
2 :  country
 
 '''
```

Para recorrer dos o mas secuencias al mismo tiempo, las entradas se puede emparejar con la función `zip()`

```python
list1 =['name','age', 'country']
list2 =['Juan', 20, 'Peru']
for l1, l2, in zip(list1,list2):
    print(l1," : ",l2)
    
'''
name  :  Juan
age  :  20
country  :  Peru
'''

```

 Para recorrer una secuencia en reversa, Primero tenemos que especificar en rango y luego la función `reversed()`

```python
for x in reversed(range(5)):
    print(x)
'''
4
3
2
1
0

'''

# tambien tenemos de esta forma
for x in range(5,0,-1):
    print(x)
    
'''
5
4
3
2
1

'''

```

Para recorrer una secuencia en orden, podemos usar la función `shorted()`, que devuelve una lista ordenada, sin modificar los datos originales

```python
numbers = [1,5,2,6,3,8]
for i in sorted(numbers, reverse=True):
    print(i)
    
'''
8
6
5
3
2
1
'''
```

Aveces es tentador modificar datos de una lista mientras recorres, sin embargo  tenemos una forma simple de  y seguro creando una nueva lista, veamos como se hace

```python
names = ['maria', '', 'Juan', "","Pedro"]
name_options =['Lucas','Susana','Armando','Marcos']

print(name_options[0])
for row, item in enumerate(names):
    if item == "":
        item = name_options[row]
    print(item)
    
 '''
Lucas
maria
Susana
Juan
Marcos
Pedro
 '''
```

### Más sobre las condicionales 

Los operadores de comparación `in`  y `not in`, estos operadores comparan si un valor existe en un secuencia, también tenemos los operadores de `is` y `not is`, estos operadores comparan si dos objetos son realmente iguales, esto solo trabaja con objetos mutables como las listas. 

Las comparaciones se pueden anidar utilizando los operadores boleanos como `and` y `or`, también tenemos el operador `not` , este operador es de negación y tienen una prioridad muy baja ante los demás operadores 

Algo muy importante que dice la documentación es , que pasa si deseamos compara muchos valores con `and` , antes de entrar en ejemplos, estos operadores son de corto circuito, entonces que pasa cuando hacemos esta comparación ` true and true and true` , si todos son verdaderas el resultado es verdadero, pero vasta que uno sea falso, esta comparación devuelve falso.

```python
# un ejemplo con or 
name1, name2, name3 = "", "Maria", "Pedro"

print( name1 or name2 or name3)	# Maria
```

### Comparaciones de secuencias y otros tipos

Los objetos de secuencia generalmente se pueden comparar con otros objetos, con el mismo tipo de secuencia, como la documentación comenta que la comparación utiliza *lexicografiaordenamiento* los dos primeros elementos, y si son diferentes, esto determina el resultado de la comparación; si son iguales, se comparan los dos siguientes elementos y así sucesivamente, hasta que se agote cualquiera de las siguientes secuencias 

```python
(1, 2, 3)< (1, 2, 4)	#true
[1, 2, 3]< [1, 2, 4]	#true
print('C' < 'Pascal') 	#true
print((1, 2, 3, 4,5) < (1, 2, 4))	#true
print((1, 2) < (1, 2, -1))	#true
print((1, 2, 3) == (1.0, 2.0, 3.0))	#true
print((1, 2, ('b', 'b'),3) < (1, 2, ('a', 'b'), 4))	#false
```

## Módulos

En python, cada uno de nuestros archivos `.py` se denominan módulos. Estos módulos a la vez pueden formar parte de un paquete, un paquete es una carpeta que contiene archivos `.py`. Pero para que cada carpeta pueda considerarse un paquete, debe contener un archivo llamado `__init__.py`, este archivo no necesita contener ninguna instrucción.

Cuando deseamos escribir un programa mas largo o cuando nuestro programa esta creciendo, podemos dividir nuestro código en muchos archivos, uno para facilitar el mantenimiento del código, otro para reutilizar código con paradigmas de programación, solo preparamos un archivo para que el interprete de python pueda leer,  y a este se le llama como `script`.

Como ya mencionamos python tiene una forma de poner definición a un archivo que son **Módulos**. Los módulos contienen definiciones y declaraciones de python. El nombre del archivo es el nombre del módulo.

### Crear un modulo

para esto creamos un archivo `fibo.py` y llenamos con las siguientes instrucciones 

```python
def fib1(n):  # Escribir la serie de fibonachi hasta n
    a, b = 0, 1
    while a < n:
        print(a, end=" ")
        a, b = b, a+b
    print()


def fib2(n):
    array = []
    a, b = 0, 1
    while a < n:
        array.append(a)
        a, b = b, a+b
    return array

```

para utilizar este módulo podemos crear  otro archivo, o en la misma ruta abrir en la terminal el interprete de python e importar el módulo 

```python
import fibo
```

Al hacer esta importación solo estamos importando el modulo osea el archivo `fibo.py`, y ¿como utilizamos las funciones que tenemos dentro del módulo?, pues el nombre del módulo + `.` y la función. Dentro del módulo su nombre  esta disponible como variable global.`__name__`.

```python
import fibo

f = fibo
f.fib1(15)	# 0 1 1 2 3 5 8 13 
f.fib2(15)	# [0 1 1 2 3 5 8 13] 
f.__name__	# 'fibo' 

```

### Mas sobre módulos

Un modulo puede contener sentencias ejecutables, así como definiciones de funciones, Estas declaraciones están destinadas a inicializar el módulo, también pueden ejecutarse si solo llamamos el modulo

Los módulos pueden importar otros módulos, también existe una variante del `import`, por ejemplo podemos importar directamente del módulo las declaraciones

```python
from fibo import fib1, fib2

fib1(15)	# 0 1 1 2 3 5 8 13 
```

Otra variante del `import *` 

```python
from fibo import * 
fib1(15)	# 0 1 1 2 3 5 8 13 
```

Esto importa  todos los nombres, excepto los que comienzan con `_nombre`, en la mayoría de los casos los programadores no introducen este tipo de funciones. Tenga en cuenta la practica del `import *` desde un modulo o paquete esta mal vista, ya que a menudo causa un código poco legible. Sin embargo esta bien usarla cuando guardar las sesiones interactivas

Si deseamos cambiar el nombre del un modulo al llamar en otro, tenemos `as `  seguido del nuevo nombre

```python
import fibo as f

f.fib1(15)		# 0 1 1 2 3 5 8 13 

#también del modo diferente 
from fibo import fib1 as fibonacci
fibonacci(15) 	# 0 1 1 2 3 5 8 13 
```

### Ejecutando módulos como scripts

cuando ejecuta  un modulo con Python con:

> `python fibo.py <arguments>`

Cuando ejecutemos un modulo como script, el código del modulo se ejecutará, como si lo hubieran importado, lo que significa si queremos que nuestro módulo sea un script, tenemos que agregar el siguiente código al final

```python
if __name__ == "__main__":
    import sys
    fib(int(sys.argv[1]))
```

y en interprete podemos ejecutar nuestro script

```bash
 python fibo.py 15
 # 0 1 1 2 3 5 8 13 
```

La ruta de búsqueda del modulo

```python

for element in usuario:
    print(usuario[element])
print(usuario.values())
#Obtener los claves o llaves
print(usuario.keys())
#Limpiar el diccinario
usuario.clear()
#Copiar diccionarios
nuevoDiccionario = usuario.copy()
#Actualizar 
usuario.update({'nombre':'nuevo valor',etc tododos lo que quieras actualizar})
#Agregar datos 
usuario = {'nombre':'Juan','edad':20,'email':'juan@gmail.com'}
usuario['cargo'] = "Estudiante"
print(usuario)
```



## Paquetes

Los paquetes son una forma de estructurar los módulos, es decir que tenemos una carpeta de módulos y para que la carpeta sea un paquete tiene que tener el `__init__.py`, con esto ya le indicamos a python que este es un paquete 

```python
matematica/
    |-- __init__.py
    |-- aritmetica.py
    |-- geometria.py
```

para llamar a los módulos del un paquete, 

```python
from matematica.aritmetica
print(matematica.aritmetica.sumar(7, 5))
```

o de otra manera 

```python
from matematica import aritmetica
print(aritmetica.sumar(7, 5))


from matematica.aritmetica import sumar
print(sumar(7, 5))

```

## Entrada y salida

Hay diferente métodos para representar la salida de un programa o tener más control sobre impresiones de con `print` como pasar valores a un `string` para esto tenemos dos formas

```python
nombre = "Juan"
edad = 20
print(f'Hola me llamo {nombre} y tengo {edad} años de edad')
# Hola me llamo Juan y tengo 20 años de edad
```

otra forma es utilizando el método `str.format()` pro ejemplo

```python
nombre = "Juan"
edad = 20
print('Hola me llamo {} y tengo {} años de edad'.format(nombre, edad))
# Hola me llamo Juan y tengo 20 años de edad

# ========== otra manera de format es pasar con palabra clave, que no seria importante el orden ======
nombre = "Juan"
edad = 20
print('Hola me llamo {name} y tengo {age} años de edad'.format(age=nombre, name=edad))
```

### formatear cadenas literales

Pasar un entero después de `:`  hará que ese campo se el numero de espacios, esto es útil para alinear columnas 

```python
table = {'Juan': 23, 'Jack': 26, 'Maria': 24}

for nombre, edad in table.items():
    print(f'{nombre:10} ===> {edad:10} hola')
    
    
""" 
    Juan       ===>         23 hola
    Jack       ===>         26 hola
    Maria      ===>         24 hola

"""
```

## Leyendo y escribiendo archivos

La función `open(file, mode)` retorna un `file object`  y se usa normalmente con dos argumentos el nombre del archivo y el modo en que vamos abrir el archivo

```python
with open('text.md') as f:
    read_data = f.read()
    print(read_data)
    f.closed
```

### Métodos de los objetos de archivo

- `f.read()`: lee el archivo en modo texto
- `f.readline()`:  Lee una sola linea del archivo generalmente la primera linea 
- `list(f)` o `f.readlines()`: Nos permite leer el archivo en una sola linea
- `f.write(cadena)`: Para insertar texto

```python
#  w : solo para escritura
# a : abre en modo escritura y el dato agregado se va al final 
# r : solo para lectura
# r+ : para lectura y escritura
# b : abrir el archivo en modo binario
with open('text.md', 'r+') as f:
    print(f.write('este es una nueva linea agregada por f.write'))

    for line in f:
        print(line, end=" ")

f.close()
```

por leer mas profundo

```python
with open('text.md', 'rb+') as f:
    f.write(b'0123456789abcdef')
    print(f.seek(-2, 1))
    print(f.read(4))
f.close()

```

También podemos pasar otro tipos de datos, hasta el momento solo estábamos pasando puro texto, con el método  `dump(object, f)` de `json` podemos pasar diferente tipos de datos

```python
import json

with open('text.md', 'r+') as f:
    json.dump(['juan', {'name': 'Juan'}, 20], f)
    f.read()
f.close()

```

## Errores y excepciones

En la mayoría de errores encontramos dos tipos de errores ***errores de sintaxis y errores de excepciones***  

### Errores de sintaxis

Estos errores son mas conocidos como errores humanos, generalmente nos pasa cuando estamos iniciando en el lenguaje, al no saber la sintaxis del lenguaje

```python
>>> while True print('Hello world')
  File "<stdin>", line 1
    while True print('Hello world')
                   ^
SyntaxError: invalid syntax
```

El interprete indica con una flecha de donde primero se origino el error e indicándonos del tipo  de error 

### Excepciones 

Las excepciones son errores que se producen durante la ejecución y estos errores se llaman excepciones, pero no son incondicionalmente fatales, ya que podemos manejarlos y decidir que hacer cuando ocurra el error por ejemplo un error

```python
>>> 10 * (1/0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
```

nos indica que la linea tal tenemos un tipo de error que es que no se puede dividir por cero, como podemos manejar este tipo de errores 

### Gestionando excepciones

```python
try:
    pass # este seria donde ejecutemos nuestro codigo, si pasa algo entoces este sera capturado y nos pasa ala excepcion
except expression as identifier:
    pass # Aqui decidimos que hacer cuando ocurrio el error
```

Vemos un ejemplo

```python
while True:
    try:
        x = int(input("ingresa un numero: "))
        break
    except ValueError:
        print('ups, por favor vuelve a ingresar')

```

En este ejemplo podemos ver como podemos manejar este excepción

una declaración `try` puede tener mas de una `except`, para gestionar distintos excepciones, por ejemplo un `excep` puede nombrar distintas excepciones 

```python
except (RuntimeError, TypeError, NameError):
	pass
```

**bloque else:** También tenemos es `else` después del `except` que es que el caso cuando no pasa por la excepción, y podamos realizar algo si todo salio correctamente 

```python
while True:
    try:
        x = int(input("ingresa un numero: "))

    except:
        print('ups, por favor vuelve a ingresar')
    else:
        print('Todo a funcionado correctamente')
        break
```

**Bloque finally**: Es posible utilizar este bloque, que se ejecute al final del código, ocurra o no ocurra un error

```python
while True:
    try:
        x = int(input("ingresa un numero: "))

    except:
        print('ups, por favor vuelve a ingresar')
    else:
        print('Todo a funcionado correctamente')
        break

    finally:
        print('Este texto se imprime pase lo que pase')
```

### Lanzando excepciones

La declaración `raise()` nos permite forzar a que ocurra una excepción específica por ejemplo:

```python
try:
    raise NameError('GenerandoError')
except NameError as err:
    print(err)
```

También con `raise` podemos continuar y seguir lanzando la excepción

```python
try:
    raise NameError('GenerandoError')
except NameError as err:
    print(err)
    raise

```

###  Excepciones definidas por el usuario

volver a practicar cuando sepas mas sobre clases

https://docs.python.org/es/3.8/tutorial/errors.html

## Clases

## Programación orientada a objetos

Para Python Todo es un objeto 

### Que es un objeto

Es un conjunto de cosas  que tiene propiedades o atributos y métodos, Algo muy importante que tenemos que tener en claro es. Para  poder crear un objeto tenemos que tener un "clase" y que es una clase las clase es como el molde  que de ese molde vamos a crear un objeto  y como se crean las clases 

```python

class Usuario:
    nombre = ''
    edad = 20
    pais =""

    def saluda(self):
        print('HOLA MUNDO',self.edad)

pepito = Usuario()

print(pepito.saluda())

```

- Propiedades: Las propiedades de un objeto son las propiedades  como nombre, edad, genero
- Métodos : los métodos son las acciones que pueden realizar un objeto, por ejemplo una persona puede saludar,comer, dormir, etc.
- `self`: Tenemos que entender bien que el `self` es una propiedad muy importante en los métodos y tiene que ir siempre. Los que vienen de otros lenguajes de programación el  self es equivalente al this, es para poder acceder  a las propiedades del objeto 
- Constructor: Un constructor es como una condicional  que tenemos, es como un ultimo fase de poder asignar valores   o acceder a las propiedades de la clase antes de que se cree el objeto, es el iniciador del objeto cuando instanciamos un objeto y esto siempre pasa por el iniciador antes que se cree el objeto.

```python
class Persona:
    nombre=""
    edad = 0
    pais = ""

    def __init__(self,nombre,edad,pais):
       self.nombre = nombre
       self.edad = edad
       self.pais = pais

    def saluda(self):
        print('Hola me llamo:',self.nombre)


persona = Persona('Jerry',20,'Peru')
print(persona.nombre)
```

- Herencia : La herencia son heredar propiedades o métodos de otras clases, pero algo importante cuando heredamos de múltiples clases, este toma el `__init__`  o constructor del primer clase que llamaste a heredar 



## Funciones propias Python  

- `input()`: Para ingresar datos por consola

  ```python
  edad = input('Ingresa edad')
  ```

  


## Funciones Generales 

- `print(variable,...)`: Para imprimir el dato de una variable

  ```python
  print(edad) 
  # 20
  ```



## Funciones para string



## Funciones para Números

- `range(inicio,finparada[,paso])`: Se usa comúnmente para recorrer un número especifico de veces en un `for` También se puede utilizar para crear duplas, listas

  ```python
  for i in range(1,10):
      print(i, end=' ')  # 1 2 3 4 5 6 7 8 9
  
  for i in range(10,1,-1):
      print(i, end=' ')  # 10 9 8 7 6 5 4 3 2 1
      
      
  # Crear una tupla o lista a partir de un rango de números 
  numero_pares = tuple(range(2,20,2)) 
  print(numero_pares)	   # (2, 4, 6, 8, 10, 12, 14, 16, 18)
  
  numero_pares = list(range(2,20,2)) 
  print(numero_pares)	   # [2, 4, 6, 8, 10, 12, 14, 16, 18]
  #Tambien podemos utilizar con la función sum()
  
  print(sum(range(4)))  # 0 + 1 + 2 + 3 = 6
  ```

   

- ``len()``: Para obtener la longitud de un string o lista este empieza de 1 para contar tengan cuidado 

  ```python
  saludar = "Hello Word"
  print(len(saludar)) # 10
  
  a = ['Mary', 'had', 'a', 'little', 'lamb']
  print(len(a))  # 5
  ```

  