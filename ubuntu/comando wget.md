---

---

# Comandos Wget 

GNU Wget es una utilidad de lineas de comandos para descargar archivos de la web, con wget puedes descargar archivos mediante los protocolos `http`, `https`, `ftp` Wget le ofrece una serie de opciones que le permite descargar varios archivos, reanudar las descargas, limitar el ancho de banda, las descargas recursivas, las descargas en segundo plano, refleje un sitio web y mucho mas.

En este tutorial explicare como utilizar a profundidad la opción de wget con ejemplos prácticos

## Instalar Wget

Actualmente el paquete Wget esta instalado en la mayoria de las distribuciones de linux, para comprobar si el paquete Wget esta instalado en su sistema operativo, abra la consola y escriba Wget y presione enter. Si tiene wget instalado, el sistema imprimira wget: Url faltante de lo contrario imprimirá comando no encontrado.

instala wget 

```bash
sudo apt install wget
```

instala en centos y fedora 

```bash
sudo yum install wget
```

 

## Sintaxis del comando 

Antes de entrar en el comando revisemos la sintaxis del comando wget 

```bash
wget [opitions] [url]
```

- opciones: https://linux.die.net/man/1/wget
- URL: Url del archivo o directorio con la que desea vincular 

## Como Descargar Archivos con Wget

En su forma mas simple cuando se usa sin ninguna opción, wget descargará el recurso especificado en la `[url] ` al directorio actual 

En el siguiente ejemplo descargaremos un archivo de el kernel de linux

```bash
wget https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.17.2.tar.xz
```

Como puede ver Wget comienza resolviendo la dirección ip del dominio luego se conecta al servidor remoto y inicia la transferencia 

Durante la descarga wget muestra la barra de progreso junto con el nombre del archivo el tamaño del archivo, la velocidad de descarga y el tiempo estimado, una vez que se a completado la descarga puede verlo en la ruta donde a ejecutado el comando

## Opciones de Wget

- `-q` : Para desactivar la salida  si un dato existe este añadirá un sucesión de número
- `-o [nombre_nuevo] `: Para guardar el archivo descargado con un nombre diferente
- `-P /var/program ` : Para guardar el archivo en una ruta especifica 
- `--limit-rate=1m`: Para limitar las descargar y así no consumir todo el ancho de banda, y es para limitar bytes por segundo ` k`: para kilobytes , `m`: para megabytes, `gb`: para gigabytes
- `-c`: Para reanudar la descarga : si el servidor remoto no admite la reanudación de descargas; Wget iniciará la descarga desde el principio y sobrescribiera el archivo existente 

## Como descargar en segundo plano 

Para descargar en segundo plano, use la opción `-b` de forma predeterminada, la salida se redirige a un archivo `wget-log` en el directorio actual, para ver el estado de descarga, use el comando `tail`

```bash
tail -f wget-log 
```

## Como cambiar el usuario-agente de Wget de #Wget

A veces, al descargar un archivo, el servidor remoto puede configurarse para bloquear el agente de usuario de Wget. En situaciones como esta, para emular un navegador diferente, pase la opción `-u`

```bash
wget --user-agent="Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0" http://wget-forbidden.com/

```

Esto simulará un navegador web como Mozilla 



## Como descargar varios archivos 

Si deseas descargar varios archivos a la vez, use la opción `-i` seguida de la ruta a un archivo local o externo que contenga una lista de las URL  que se descargaran, cada URL debe estar en un linea separada., 

```txt
http://mirrors.edge.kernel.org/archlinux/iso/2018.06.01/archlinux-2018.06.01-x86_64.iso
https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-9.4.0-amd64-netinst.iso
https://download.fedoraproject.org/pub/fedora/linux/releases/28/Server/x86_64/iso/Fedora-Server-dvd-x86_64-28-1.1.iso

```

## Wget para descargar a travez de FTP

para descargar  un archivo de un servidor FTP protegido con contraseña, especifique el nombre de usuario y la contraseña como se muestra a continuación 

```bash
wget --ftp-user=FTP_USERNAME --ftp-password=FTP_PASSWORD ftp://ftp.example.com/filename.tar.gz

```

## Uso de Wget para crear un mirror  de un sitio web

Para crear un mirror de un sitio web con wget use la  opción  -m. Esto creara una copia local completa del sitio web siguiendo y descargando todos los enlaces, asi como los recursos del sitio web (javascript, css, imagenes)

```bash
wget -m https://example.com

```

Si desea utilizar el sitio web descargado para la navegación local, deberá pasar algunos argumentos adicionales al comando anterior 

```bash
wget -m -k -p https://example.com

```

La opción `k` hará que Wget convierta los enlaces en documentos descargados para que sean adecuados para la visualización local. la opción `-p` le dirá a wget que descargue todos los archivos necesarios para mostrar la pagina HTML 

## Como omitir la verificación del certificado con Wget

Si deseas descargar archivos a través `HTTPS` desde un host que tiene un certificado ssl no valido, use la opcion `--no-check-certificate`

```bash
wget --no-check-certificate https://domain-with-invalid-ss.com
```

## Como descargar la salida estándar  con Wget

En el siguiente ejemplo wget descargará silenciosamente `(flag-q )` y enviara la última versión de wordpress a `stdouf (flag-O-)` y la canalizara a la utilidad `tar` que extraerá el archivo al directorio var/www/  

```bash
wget -q -O - "http://wordpress.org/latest.tar.gz" | tar -xzf - -C /var/www

```

## Conclusión 

Con wget puede descargar varios archivos, reanudar descargas parciales, duplicar sitios web y combinar las opciones de wget según sus necesidades



```bash

```

