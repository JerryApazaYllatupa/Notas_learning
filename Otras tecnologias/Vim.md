# Vim

Vim es un editor de código para editar archivos 



## Comandos para navegar

* `k`: Para arriba
* `j`: Para abajo
* `l`: Para la izquierda
* `h`: Para arriba 



Para entrar al estado de edición 

* `i`
* `:q!` : Para salirse sin guardar 
* `:wq`: Para guardar y salir 

## Moverse en Vim

* `w`: Para saltar en la siguiente palabra 
* `e`: Para ir al final de un palabra
* `b`: Para regresar atrás una palabra 

Combinación de teclas con números 

* `5 + k` : Para subir 5 lineas 
* `f + o`: Para buscar la siguiente letra 

Para el inicio o al final de una linea 

* `0`: Para ir al final de la linea
* `shif + $`: Para ir al final de la linea 
* `gg`: Para irse al inicio del documento 
* `GG`: Para irse al final de una linea 
* `15 G` Para irse a una linea especifico 
* `*`: Para encontrar la siguiente palabra igual 
* `%` Para ver el cierre de un paréntesis y regresar en el paréntesis 

## Editar documentos

* `o`: Para insertar una nueva linea abajo
* `O`: Para insertar una nueva linea arriba
* `x` : Para borrar un carácter donde esta posicionado el puntero 
* `r + letra`: Reemplazar caracteres 
* `d + w`: Para cortar una letra a la derecha
* `d + b`: Para cortar una letra a la izquierda 
* `dd`: Para cortar una linea 
* `p`: Para pegar 
* `y + w`: Para copiar una letra
* `yy`: Para copiar una linea
* `.` Repetir la ultima acción 
* `v` Modo visual para seleccionar 
* `u`: Para deshacer  
* `ctrl + r`: Para rehacer  el cambio 
* `A`: Para mover el cursor al final de la linea 



## Buscar y reemplazar 

* `/palabra`: Para buscar una palabra y enter al final y con la letra `n` para buscar la siguiente palabra 
* `/o$`: Para buscar todos los que terminan en o   al final de una linea el signo de pesos es para eso son las expresiones regulares 
* `:%s/palabra/palabraareemplazar` : Para reemplazar una palabra 