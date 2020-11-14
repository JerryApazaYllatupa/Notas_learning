[TOC]



# Laravel Homestead

Para trabajar los proyectos de laravel se recomienda, trabajar con su entorno de  desarrollo local que es vagrant, y esta nos proporciona una manera elegante y simple de administrar y aprovisionar maquinas virtuales 

Laravel homestead es un  caja vagrant como la documentación lo dice. Es decir que la caja nos proporciona un maravilloso entorno de desarrollo sin la necesidad de instalar PHP, un servidor web, y cualquier otro software de servidor en su maquina local.

Laravel se ejecuta en cualquier otro sistema 

## Instalación

Primero debemos instalar  un sistema de virtualización ya sea  [VirtualBox 6.x](https://www.virtualbox.org/wiki/Downloads), [VMWare](https://www.vmware.com/), [Parallels](https://www.parallels.com/products/desktop/) or [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v)  y después descargar e instalar  [Vagrant](https://www.vagrantup.com/downloads.html)  para ello hay muchos tutoriales  tanto para virtual box y vagrant.

### ¿Que  es vagrant?

Es una herramienta de lineas de comandos para construir y administrar maquinas virtuales 

sirve para configurar entornos de desarrollo que funcione en varios sistemas operativos 

Vagrant es una herramienta que nos ayuda a crear y manejar maquinas virtuales con un mismo entrono de trabajo. 

Después de la instalación de VirtualBox y Vagrant, Para ver si vagrant se instalo correctamente podemos  verificar con el comando `vagrant --version`  y luego de ello tenemos que descargar la caja de homestead 

### instalar y descargar vagrant en ubuntu

### Instalar vagrant desde paquete .deb

El primer y rápido y método para instalar el último vagrant en Ubuntu es debe el paquete .deb consulte la pagina de descarga de vagrant para obtener la ultima versión de vagrant. Aqui instalaremos v2.2.9

Descargaremos la ultima versión 

```bash
VER="2.2.9"
wget https://releases.hashicorp.com/vagrant/${VER}/vagrant_${VER}_x86_64.deb
```

```bash
sudo dpkg -i vagrant_${VER}_x86_64.deb

sudo apt -f install

```

### Instalar el último vagrant desde el repositorio de la apt

Este método para instalar vagrant en debian y sus derivados es desde un repositorio  apt un repositorio que encontré que funciona es el que se proporciona en https://vagrant-deb.linestarve.com esto le permite actualizar a la versión instalada de vagrant usando el administrador aptpackage.

Descarto de responsabilidad: este es un repositorio de debian no oficial para vagrant alojado por wolfgang faus. Agreque el repositorio a su sistema usando el comando

```bash
sudo bash -c 'echo deb https://vagrant-deb.linestarve.com/ any main > /etc/apt/sources.list.d/wolfgang42-vagrant.list'
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key AD319E0F7CFFA38B4D9F6E55CE3F3DE92099F7A4 D2BABDFD63EA9ECAB4E09C7228A873EA3C7C705F
sudo apt-get update
```

```bash
 sudo apt -y install vagrant
```

Después de la instalación, puede verificar la versión

```bash
vagrant --version
2.2.13
```

Usar una Vagrant Box de prueba. En este ejemplo, Descargaré Kali Linux

para ver mas detalle sobre vagrand ai esta la pagina el link

https://computingforgeeks.com/install-latest-vagrant-on-ubuntu-debian-kali-linux/

https://www.vagrantup.com/downloads.html

##  descargar e Instalar de Homestead vagrand box

```bash
vagrant box add laravel/homestead
```

Esta descarga es un sistema virtual que nos trae todo lo necesario y la configuración para trabajar con un proyecto. Vamos con lo siguiente tenemos que descargar el paquete de homestead.

### Instalar Homestead 

En esta parte tenemos que clonar el paquete de homestead y se recomienda que sea en la carpeta o que la carpeta se llame "Homestead" dentro del directorio Escritorio  o Home, esto será para poder administrar nuestros proyectos de cualquier ruta

```bash
git clone https://github.com/laravel/homestead.git ~/Homestead
```

Una vez clonado en el home  debemos ingresar a la versión estable de homestead

```bash
#ingresamos a la ruta 
cd ~/Homestead 

#vamos a la rama estable
git checkout release

```

Después de terminar esto tenemos que ejecutar el  comando `bash init.sh` desde el directorio *Homestead* y esto será para crear el archivo de configuración Homestead.yaml

```bash
#si estas trabajando con la terminar del git 
bash init.sh
#si estas trabajando con la terminal de windows
init.bat
```

Si abres la archivo de configuración `Homestead.yaml ` tendremos la opción del acceso  `ssh` que son la llaves para dar acceso a git de tu maquina 

### Configuración de Homestead



