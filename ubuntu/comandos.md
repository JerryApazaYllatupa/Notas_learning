[TOC]



# Comandos para la terminal linux

## Navegando por los directorios

- `pwd`: "Print Working Directory",  muestra el directorio actual,muy importante cuando navegamos sobre muchos directorios

- `ls`: 

  ```bash
  # listar los ficheros de la carpeta actual
  ls
  # listar fichero de otras rutas
  ls /usr/
  # listar ficheros con información extra
  ls -l
  # listar ficheros o carpetas ocultas
  ls -a
  #listar todos lo ficheros con permiso y todo los que contienen con una cierta palabra
ll palaba_a_buscar*
  ```

  `cd`:  
  
  ```bash
  # cd solo nos lleva al directorio actual 
  cd  	
  
  # Entrar en un directorio
  cd  /directorio/ 
  
  # salir un directorio atras
  cd ..
  
  ```

## Manipular archivos

- `cp`: Copiar un fichero o directorio

  ```bash
  # Copiar 
  cp nombreFichero directorioACopiar
  
  #copiar el directorio y su contenido
  cp -r nombreFichero directorioACopiar
  
  # copiar solo el contenido del directorio
  cp -r nombreFichero/*  directorioACopiar
  
  #copiar un fichero o directorio y preguntar antes de sobre escribir 
  cp -i nombreFichero directorioACopiar
  ```

- `mv`: Mueve o renombre un fichero o directorio 

  ```bash
  #mover
  mv FicheroODirectorio  directorioAMover/
  
  #mover y renombrar
  mv document.txt  document/nombreNuevo.txt
  
  ```

- `mkdir`: Crea un directorio

  ```bash
  #crear
  mkdir nuevoDirectorio
  
  #crear un directorio con el nombre espaciado
  mkdir "nueva carpeta"
  mkdir nueva\ \carpeta
  #crear carpetas con subcarpetas 
  mkdir  -p name/{name, name/{name,name}}
  
  ```

- `rmdir`: Elimina directorios vacíos  

  ```bash
  rmdir "carpetaVacia"
  ```

- `rm`: Eliminar ficheros o directorios

  ```bash
  # eliminar un fichero
  rm archivo.txt
  
  #eliminar un directorio y todo su contenido
  rm -r documents
  
  #preguntar antes de eliminar 
  rm -i documents
  
  #Eliminar todas las carpetas
  rm -r documents/*
  
  
  ```

## Comprimir descomprimir archivos

- Descomprimir Archivos

  ```bash
  sudo apt-get install unrar
  unrar x nombre_del_rar.rar
  ```

  



## Atajos de teclado

- `Tab`: Nos auto completara lo que tratamos de escribir
- `ctrl + r`: Buscará en el historial a medida que concuerde con lo que vayamos escribiendo
- `ctrl + c`: Para romper cualquier proceso que este en ejecución
- `ctrl + d`: Cierra la terminal o eliminar a la derecha
- `ctrl + w`: Elimina la palabra anterior en la pasión del cursor 
- `ctrl + k`: corta el comando del cursor actual, hacia la derecha
- `ctrl + u`: corta el comando del cursor actual, hacia la izquierda
- `ctrl + y`: Copia el comando cortado con `k` y `u` 
- `ctrl + l`: Limpiar la consola
- `ctrl + e`: ir al final de la linea del comando
- `ctrl + a`: ir al inicio de la linea del comando
- `ctrl + f`: Mover el cursor hacia la derecha
- `ctrl + b`: Mover el cursor hacia la izquierda
- `ctrl + j `y `ctrl + m`: Estos dos comandos aceptar linea seria como dar enter en el comando
- `ctrl + n `: Siguiente historial
- `ctrl + t `: mover caracteres 
- `ctrl + p`: Historial previo
- `atl + b`: mueve el cursor una palabra atrás
- `atl + c`: Convertir a  mayúscula la primer letra de la palabra 
- `!!`: Repetirá el ultimo comando
- `ctrl + shift + v`: Pegar
- `ctrl + shift + c`: Copiar
- 

## Comandos de información del sistema

- `date`: Muestra la fecha y hora 
- `cal`: Muestra el calendario del mes actual en curso
- `whoami`: Muestra el nombre del usuario con el que estamos trabajando
- `uptime`: Muestra el tiempo en que esta encendido el sistema

## Comandos de procesos

- `top`: Muestra todos los procesos que se encuentran activos en el sistema
- `kill pid`: Detiene el proceso del pid, y el pid es como el id obtenido con el comando `top`

## Comandos de actualización 

- `apt-get update`: Actualizará los repositorios de los programas con las versiones mas recientes
- `apt-get upgrade`: Aplicara las actualizaciones que hayamos obtenido con el comando anterior en caso de existir actualizaciones

## Comandos de instalación

- `apt-get install libreoffice` : Comando para instalar cualquier otra aplicación que este la software ubuntu 

- `dpkg -i xxx.deb`:  Es el instalador de paquetería .deb

- `yum install xxxxxx`: Instalador de paquetería para gestores rpm

- `rpm -i xxxx.rpm`: Instalador de paquetería para gestores rpm

- ```bash
  sudo apt -f install
  ```

## Comandos de Inicio y Apagado

- `halt`: Detiene todos los procesos y apaga el equipo
- `shutdown`: Programa el apagado del equipo en un minuto
- `shutdown -r xx `: Programa el reinicio del sistema, en el minuto que se paso como parámetro 
- `shutdown -h now ` : Apaga el equipo saltándose el minuto programado 
- `shutdown -r now`: Reinicia el equipo salándose el minuto programado
- `reboot`: Reinicia el sistema 



## Comandos de red

- `ifconfig`: Lista las direcciones IP del equipo

- `ping xxxx`: Manda una señal hacia la dirección y comprobar si esta en la linea

- `whois xxxx`: Obtiene información acerca de un dominio 

- `wget xxxx`: Descargará el archivo xxx, debemos proporcionar una dirección completa https://mott.pe/noticias/wp-content/uploads/2019/03/los-50-paisajes-maravillosos-del-mundo-para-tomar-fotos.jpg

  ```bash
  wget https://mott.pe/noticias/wp-content/uploads/2019/03/los-50-paisajes-maravillosos-del-mundo-para-tomar-fotos.jpg  && mv los-50-paisajes-maravillosos-del-mundo-para-tomar-fotos.jpg Descargas/
  
  ```



## Comandos de comandos

- `man xxxx`: Muestra el manual o configuración de uso del programa

  ```bash
  man vim
  ```

- `sudo chown  -R user:user name_folder`: Para cambiar a un usuario especifico

  ```bash
  sudo chown -R jerry:jerry go
  ```

  

- 

## Eliminar programas de ubuntu

```bash
# Modo 1
sudo apt-get --purge remove my_program
# Modo 2
sudo ppa-purge ppa:myprogram

# Modo 3
sudo apt-get remove mypacket
```

## Comandos para crear editar eliminar archivos 

### Crear archivos

```bash
# touch: nos permite, solo crear archivos, puede ser cualquier extensión y podemos crear en una linea cuantos quereamos, si el archivo existe este no crea otro archivo ni reemplaza 

touch notes.txt 
touch notes1.txt notes.js notes.css

# gedit: este tambien al igual de touch puede crear archivos de cuaquier extension y abrir el archivo al instante, esto es lo genial de gedit y puede validar validar el contenido de acuerdo al tipo de archivo

gedit style.css
getit app.js
 

```

### imprimir el contenido de un archivo

En esta parte tenemos tres modos de visualizar ojo solo visualizar, es decir solo podemos ver el archivo desde la terminal.

Los tres modos son ***cat***, ***more***  y ***less***, cada uno con sus particularidades.

#### cat 

Este comando es uno de los más utilizados cuando se trata de archivos, entre sus múltiples opciones esta poder ver el contenido del archivo,crear archivos, etc.  

```bash
# Este comando te permite crear un archivo sin extensión dandote al mismo tiempo de llenarla con contenido y porderla guardar al instante con el comando ctrl + d, tener cuydado con este comando, si aplicas este en un archivo existente, lo más probable es que se te borre el contenido
cat > nombrearchivo
 content 1
 content 2
CTRL + D

#visualizar contenido: recomendado 
cat style.css

# visualizar multiples contenidos: este comando visualizara el contenido de forma conjunta
cat style.css app.js

# Visualizar contenido numerado
cat -n style.css

# visualizar contenido numerado pero solo las líneas con contenido y omitir las basias
cat -b style.css

# saber mas sobre los camandos 
cat --help

```

#### more

Este comando al igual que **cat** visualiza contenido, pero con la diferencia de que este es muy útil  para contenidos muy largos, ya que este te muestra el contenido pagina y no necesitamos del ratón, solo la tecla de espacio para poder viendo el contenido 

```bash
more style.css
```

#### less

Less al igual que los anteriores puedes visualizar contenido, con la diferencia de que este te abre un editor y tenemos que aprendernos mas comandos tan solo para hacer lo mismo, en lo personal no lo recomiendo, ya que podemos hacer todo esto y mejor en **vim**, de todas maneras pueden investigar y saber más sobre este

### Leer y editar archivos 

Finalmente tenemos dos editores de texto muy potentes para la consola, que son **Nano** y **Vim** que estos muy complejos  y explicarlos seria mas largo del documento, por lo cual pueden investigar sobre estos temas, pero si queremos poder leer y editar archivos tenemos **gedit** en la mayoría de las distros de linux lo tienen como editor de texto.

```bash
gedit style.css
#este te abrirá el programa para editar el archivo y cualquier tipo de archivo el de las mayorias 
```

## Solución de Errores 

- Tenemos estos errores  al realizar una instalación fallida o actualizaciones 

  ```bash
   sudo rm /etc/apt/sources.list.d/* -vf 
   sudo rm /etc/apt/sources.list.d/bjfs-ppa-maverick.list
  ```

  https://cyberlider.blogspot.com/2016/10/solucion-eno-se-pudieron-leer-las.html






Formatear datos json en la terminal

```bash

```

