# Git desde cero



[TOC]



## Fundamentos de git 

https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Fundamentos-de-Git



## ¿Que es Git?

Es un sistema de control de versiones que originalmente fue diseñado para operar en un entorno Linux. Actualmente git es multiplataforma, es decir que ahora ya no solamente es compatible con Linux sino también MacOS Windows.

## Beneficios

> * Trabajo colaborativo
> * Ayuda en conflictos 
> * puedes llevar todo los registros de todo los cambios y avances de tu proyecto
> * Funciona como una máquina del tiempo puedes ir al pasado de tu código o volver al presente
> * Git trabaja con ramas ayuda a que varias personas en un mismo proyecto y puedan hacer modificaciones sin afectar a los demás 

## Instalación de git 

> https://git-scm.com/downloads
>
> descargar e instalar  y todo siguiente 

## Git status

> - `Working directory`: el área de trabajo, en este estado están esos archivos se modificaron 
> - `staging area`: Se les prepara los archivos para ser incluidos en el repositorio.  
> - `repository`:   Los archivos son incluidos al repositorio con el uso de commints.
>
> Mas información https://git-scm.com/book/en/v1/Getting-Started-Git-Basics

## Flujo de trabajo de git 

> 1. Modificas una serie de archivos en tu directorio de trabajo 
> 2. Preparas los archivos, añadiéndolos a tu área de preparación 
> 3. Confirmas los cambios, lo que toma los archivos tal y como están en el área de preparación y almacena esa copia Instantánea de manera permanente en tu directorio de Git    



## Comando  básicos de la terminal 

> * `cd nombre_carpeta`: para ingresar a una carpeta
>
> * `cd ..`: para salir de una carpeta 
>
> * `mkdir nombre_carpeta`: para crear una carpeta 
>
> * `touch file.txt`: para crear un archivo 
>
> * `vim file.txt`: para editar un archivo, a  guardar el archivo presiona `"Esc"` y digita el comando `":wq"` para guardar y salir y para salir sin guardar digitar el comando `":q!"`
>
> * `clear`: limpiar la consola 
>
> * `rm -fr carpeta`: Forzar par borrar una carpeta 
> * `cat archivo.txt`: para ver la información de un archivo 
>



## Comando para obtener ayuda

> * `git help `: Para obtener ayuda  sobre algunos comandos
> * `git help --all`: Para ver todos los comandos de git 
> *   `git help  <verb>` : Para obtener ayuda o información sobre algún comando de git por ejemplo `git help config`

## Config

> Para registrarte en git 
>
> * `git config`: Para configurar 
>* `git config --system user.name 'nombre_usuario'` : Para configurar todo el sistema con un solo usuario
> * `git config --global user.name 'nombre_usuario'`:  Este es el recomendado para configurar el nombre del usuario 
>* `git config --global user.email correlectronico@gmail.com`:  Para configurar el correo electrónico del usuario 
> * `git config --global core.editor vim`: También podemos asignar el editor para editar  los archivos del proyecto  
>* `git config --list`: Para mostrar toda la información de todo el registro anterior 
> 
>
> 



## Inicializar un proyecto 

> Inicializar un proyecto  para ello tenemos que estar ubicados en los archivos mas altos del proyecto para poder inicializar un proyecto  y allí abrimos nuestra terminal  y digitamos el siguiente comando 
>
>  ```bash
>git init
> ```
> 
> 



##  Trabajando con los Comandos de git 

> * `git status`: Para ver el estado de nuestros archivos  y en que área de estado están si están en el área de   working o staging o en el directorio 
>
>   > ```bash
>   > git status 
>   > git status -s // para ver en que area o estado se encuentras nuestros archivos 
>   > ```
>
> * `git diff name_archive`: Permite mostrar la diferencia de los cambios de archivos antes que se agreguen al estado de staging  o al estado de preparación  
>
>   > ```bash
>   > // este git dif solo funciona  en los archivos que no los as agregado aun al área de staging 
>   > git diff index.html | f8df4c0
>   > git diff --staged // y si quieres ver la direferncia de los archivos que estan el area de staging con archivos del repositorio usa este comando 
>   > git diff --cached 
>   > ```
>   >
>   > 
>
> * `git log`: Nos muestra el historial de todos los commit que se hizo en el  proyecto
>
>   >  Este  comando tiene sub comando para trabajar
>   >
>   >  ```bash
>   >  git log -p -2 // Este comando nos muestra las direfencias de cambios de cada commit y le estamos indicando que nos muestre los 2 ultimos registros 
>   >  git log --stat // Nos muestra estadisticas sobre los archivos modifcados en cada información .
>   >  git log --shortstat // Muestra solamente la linea de resumen de la opción  --stat
>   >  git log --name-only // Muestra la lista de archivos afectados
>   >  git log --name-status // solo me muestra que paso en cada archivo por ejemplo algunos se an modificado y otros se an eliminado
>   >  git log --abbrev-commit //Muestra solamente los primeros carcateres de la suma SHA-1 en vez de los 40 caracteres de que compone 
>   >  --graph //Muestra un Gráfico ASCII con la historia  de ramificacion y uniones 
>   >  --pretty= //Muestra las configuraciones usando un formato alternativo. Posibles opciones son oneline, short, full, fuller y format (mediante el cual puedes especificar tu propio formato)
>   >  
>   >  //Comandos que utilizaremos mas sobre git log 
>   >  
>   >  git log --oneline -2 // que nos muestre los commit de forma resumida
>   >  git log --oneline --graph // para mostrar los graficos de las ramificaciones 
>   >  git log --pretty=format:"%h - %an: %s" 
>   >  git log --since (desde)
>   >  git log --since=2.hour | minutes | day |weeks | years | "2008-01-15" 
>   >  git log --after (despues de)
>   >  git log --until, --before (hasta) antes de tal fecha
>   >  git log --since=2018-09-00 --until 2018-11-00
>   >  git log --after='2019-06-10' | git log --after '2019-06-10'
>   >  
>   >  git log --author 'correo@gmail.com' // para filtrar solo los commit de alguien
>   >  git log --grep 'palabra clave' // para buscar dentro de los commit una palabra clave
>   >  git log -S' .dev .ed-grid ' | -Sfunctiona_name // para decirle quienes modificaron estas lineas de códigos 
>   >  
>   >  los formatos que puedas pasar para pretty estan aqui 
>   >  
>   >  %H = Hash de la confirmación
>   >  %h = Hash de la confirmación abreviado
>   >  %T = Hash del árbol
>   >  %t = Hash del árbol abreviado
>   >  %P = Hashes de las confirmaciones padre
>   >  %p = Hashes de las confirmaciones padre abreviados
>   >  %an = Nombre del autor
>   >  %ae = Dirección de correo del autor
>   >  %ad = Fecha de autoría (el formato respeta la opción -–date)
>   >  %ar = Fecha de autoría, relativa
>   >  %cn = Nombre del confirmador
>   >  %ce = Dirección de correo del confirmador
>   >  %cd = Fecha de confirmación
>   >  %cr = Fecha de confirmación, relativa
>   >  %s = Asunto 
>   >  
>   >  // y para utilizarlo ya sabemos 
>   >  git log --pretty=format:"%h - %an: %s"
>   >  //combinacion de comandos
>   >  git log --pretty="%h - %s" --since="2018-10-01"    --before="20178-11-01"
>   >  ```
>
> * `git commit --amend` : Para deshacer  cambios que hayas echo por, ejemplo que te equivocaste al momento de ingresar el asunto del commit 
>
>   > ```bash
>   >  git commit --amend //Con esto podras editar ese ultimo commit pero esto te abrira el editor vim y si quieres omitir esto digite el siguiente comando. 
>   >  
>   > // y si no sabes como funciona vim esto lo encontraras en las primeras líneas de comando básicos de la terminal 
>   >  
>   >  git commit --amend -m "El nuevo mensaje que tendra"
>   >  
>   > ```
>
> * `git reset <file>`: Para deshacer cosas 
>
>   > ```bash
>   > git reset index.html //Para sacar un archivo específico del area staging 
>   > git reset --soft cb61e7c // Para resetear un proyecto de un commit especifico Nota: estos archivos seran trasladados al staging area 
>   > git reset --mixed cb61e7c // Estos archivos incluidos en el commit serán trasladados al working directory en español al area de trabajo 
>   > git reset --hard cb61e7c //Estos archivos incluidos en el commit serán eleminados permanentemente 
>   > ```
>   >
>   > 
>
> * `git rm --cached <file>` : para cancelar todo los archivos del área staging
>
>   > ```bash
>   > git rm --cached index.html // tenemos que ingresar que archivo queremos cancelar del estado de staging
>   > git rm -f index.html //Para eleminar un archivo permanente del proyecto
>   > ```
>   >
>   > 
>
> * `git add -A o .` : Para agregar los archivos al área de staging 
>
>   > ```bash
>   > git add name.txt // para agregar algo específico al area staging
>   > git add -A  // para agregar todo los archivos  que estan en el área de trabajo
>   > git add . // tambien es igual agrega todo
>   > ```
>
> * `git commit `: para pasar los archivos del estado de staging al repositorio principal o ala rama principal  registrando con puntos en el siclo de vida de nuestro proyecto, e indicándolo que cambios se esta realizando 
>
>   > ```bash
>   > git commit  // Por defecto esto nos abrira un editor como vim
>   > git commit -v // Este es parecido al primero pero este te muestra  los cambios mas detallado dentro del editor 
>   > git commit -m "mensaje de commit" // Esta es la forma clásica de hacer commits
>   > git commit -a // si quieres saltarte el paso de git add
>   > git commit -a -m "mensaje de commit "// Nos permite saltarnos el git add y de ingresar el registro en el editor
>   > ```
>   >
>   > 
>
> * `git checkout`: Para moverse en el tiempo de línea del proyecto 
>
>   > ```bash
>   > git checkout a28245f // nos podemos mover mediante los commic  ingresando codigos de los commic, y regresamos en el tiempo como estabamos y cambia todo los commic el contenido del archivo 
>   > 
>   > git checkout v1.0 // para moverse mediante tags
>   > 
>   > ```
>
> * `git clone`:  nos permite  clonar un proyecto de GitHub parar poder contribuir 
>
>   > ```bash
>   > git clone https://github.com/escueladigital/EDgrid.git
>   > ```
>
> * `git remote` : ramas la remotas nos muestra desde donde se esta utilizando ese proyecto 
>
>   > ```bash
>   > git remote --v
>   > 
>   > // y la respuesta seria esta 
>   > 
>   > origin  https://github.com/escueladigital/EDgrid.git (fetch)
>   > origin  https://github.com/escueladigital/EDgrid.git (push)
>   > 
>   > ```
>   >
>
>   
>
> * `git fetch`: nos permite actualizar los cambios nuevos del proyecto que se esta utilizando en el repositorio pero eso solo nos trae la rama del  proyecto si queremos con todos los cambios actualizados necesitamos el siguiente comando 
>
> * `git pull origin master`: para traernos todos los cambios del proyecto  y que todo esta al día 
>
>   >```bash
>   >    git pull origin master 
>   >```
>
> * `git checkout -b nombre_rama`: lo que nos permite hacer esto es  crear una rama  de un punto y poder corregir algún error anterior 
>
>   > ```bash
>   > git checkout -b desarrollo  // para crear y moverse a esa rama
>   > ```
>
> * `git checkout master`: para moverse entre ramas 
>
>   > ```bash
>   > git checkout master // para moverse entre ramas tenermos que ingresar el nombre de la rama 
>   > 
>   > git branch // para mostrar las ramas que existen 
>   > git checkout -- <file.text>
>   > ```
>
> * `git merge nombre_rama`: esto es muy importante a la hora de mezclar ramas, es que tenemos que estar posicionados en la rama principal donde queremos jalar la rama 
>
>   > ```bash
>   > // por ejemplo esta mi rama que cree a partir de la rama master 
>   > HP@DESKTOP-K8FBM90 MINGW64 /c/xampp/htdocs/gitDesdeCero (desarrollo) // esta rama se llama desarrollo y aqui hice mis cambios y agrege nuevos archivos  y si quiero mezclar todo estos cambios a la rama principal tenemos que posiconarnos en la rama principal que es master y nos movemos con git checkout master 
>   > y desde alli podemos ejecutar este comando 
>   > git merge desarrollo
>   > 
>   > ```
>   > 
>   
>   * `git branch`: Para mostrar las ramas 
>
> *  `git branch -D nombre_rama`: esto es para eliminar una rama principal 
>
>   > ```bash
>   > git branch -D desarrollo
>   > ```
>
> * `git mv old_name new_name`: Para renombrar un archivo 
>
>   >
>   >
>   >```bash
>   >git mv main.css main3.css // pero para hecer esto el archivo tiene que estar sin modificaciones es decir no tiene que estar en el área de working 
>   >
>   >```
>   >
>   >





## Integrar proyecto local con GitHub

> 1. para esto tenemos que crear un llave publicó 
>
>    ```bash
>    ssh-keygen -t rsa #comando para generar la llave del repositorio
>    
>    ```
>
>    
>
> ```bash
> ssh-keygen -t rsa // comando para generar el la llave del repositorio
> // y seria algo asi 
> 
> Generating public/private rsa key pair.
> Enter file in which to save the key (/c/Users/HP/.ssh/id_rsa):
> /c/Users/HP/.ssh/id_rsa already exists.
> Overwrite (y/n)? y
> Enter passphrase (empty for no passphrase):
> Enter same passphrase again:
> Your identification has been saved in /c/Users/HP/.ssh/id_rsa.
> Your public key has been saved in /c/Users/HP/.ssh/id_rsa.pub.
> The key fingerprint is:
> SHA256:7gkKfP6Mpc+IJ2dSp4NNJ6s9DLSLR5ncREXm+URnI34 HP@DESKTOP-K8FBM90
> The key's randomart image is:
> +---[RSA 2048]----+
> |     o+ o +      |
> |    .o + + .     |
> |   .  o o E      |
> |  . .  o .       |
> | o *    S        |
> | .B = o.         |
> | ooO.*o .        |
> |. **@O o .       |
> | .oBB== o        |
> +----[SHA256]-----+
> 
> ```
>
> 2. agregar la llave publica ala cuenta de git  
>
> 3. conectar con el proyecto local 
>
>    > ```bash
>    > 
>    > 
>    > ```
>
> * `git pull origin master`: para traernos todo el contenido del repositorio 
>
>   > ```bash
>   > git pull origin master
>   > ```
>   
> * `git push origin master`: para agregar todo los nuevos archivos al repositorio 



## Trabajar con remotos 

> -  `git remote -v` : Te muestra los repositorios a los que puedes trabajar remotamente
>
> - `git remote add [nombre][url]`: Para añadir repositorios remotos 
>
>   > ```bash
>   > git remote add origin https://github.com/JerryApazaYllatupa/claseFinalGit
>   > // y de esta forma podemos añadir un repositorio remoto a  nuestro local 
>   > ```
>   >
>   > 

## GitIgnore

esto es el nuevo contenido 
este es el cambio desde la web
