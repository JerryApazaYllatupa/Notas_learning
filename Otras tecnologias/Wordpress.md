[TOC]



## Wordpress desde cero

Trabajando WordPress como desarrollador 

## Conceptos

### Themes

Los temas en WordPress son las plantillas webs personalizados en lo general WordPress también tiene temas gratuitos, y en estas notas iremos configurando un tema que ya hemos diseñado previamente, para ello pido que tengan un tema o también pueden descargarse una de https://w3layouts.com/ que varios temas gratuitos 

### Licencias de WordPress y la GPL

Las licencias de WordPress  son muy importantes si la pagina va ser publicada en la internet, si paginas que solo van a funcionar en el local, entonces estas licencias no son tan importantes 

### Entorno de desarrollo 

Para desarrollar un tema hay dos formas uno que puede ser local y otro en el servidor Para estos ejemplos que iremos aplicando en este trabajo iremos aplicando en un servidor local para ello tenemos que tener instalado un servidor como `xampp wampp` y se tiene que descargar los archivos generales de WordPress de su pagina oficial, y también necesitaremos un editor de código para la modificación de archivos  y los códigos que iremos trabajando no se preocupe si hasta este no entiende nada, mas adelante iremos explicando paso a paso  

## Instalación de WordPress

requisitos para la instalación de WordPress: tener instalado un servidor local como ``xampp ``u otras, tener los archivos de WordPress

si eres principiante sique estos pasos 

* descargar el archivos WordPress en esta dirección https://wordpress.org/download/ descomprima el archivo
* y xampp en esta dirección https://www.apachefriends.org/es/download.html instálelo 

1. Ejecutar ``xampp``  

1. Descomprimir el archivo de WordPress en la carpeta `C:\xampp\htdocs` es opcional si quieres guardar todos los proyectos en sola carpeta y la carpeta se llamaría `www`, luego de ello tenemos que cambiar el nombre del carpeta que descomprimimos al nombre de nuestro proyecto, por defecto esta carpeta que  se descomprime esta con el nombre de `wordpress` 

   

2. También tenemos que crear una base de datos : Para esto nos vamos al navegador ingresamos `localhost` esto es para abrir el servidor local, luego de ello tendremos una interfaz  tenemos que ingresar a la ventana de `phpMyAdmin` y allí tenemos que crear una base de datos 

   y es importante tener en cuenta el tipo de base de dato y allí seleccione el tipo de base de datos que este ese`utf8mb4_unicode_ci` es para que nos reconozca caracteres especiales  

3. cargar la ubicación de nuestro proyecto, el ruta de mi ubicación por ejemplo es esta `http://localhost/www/peruhoneymontours.com` 

4. Allí nos cargará una interfaz que es para instalación y configuración del proyecto y lo primero que nos pide es que selecciones nuestro idioma 

5. Luego no aparece otra interfaz donde nos pide los requisitos que tenemos que tener para la configuración leemos y siguiente no aparece otra interfaz para llenar el nombre de nuestro proyecto luego esta la opción para ingresar el nombre de usuario, esto datos para los permisos de los servidores en esa opción poner ``root``  que este usuario nos da el servidor local que es xampp, luego de eso también esta la opción de la contraseña esta casilla lo dejamos vacío  y siguiente 

6. En esta sección tenemos que crearnos un usuario y una contraseña para gestionar nuestro contenido 

   

   

Una vez instalado todo el WordPress  tenemos que configurar el archivo *``wp_config.php``* 

## WP_DEBUG

Configurar la depuración es una parte esencial del desarrollo del tema de WordPress. WordPress proporciona una serie de constantes para respaldar sus esfuerzos de depuración. Estos incluyen:

```php
define( 'WP_DEBUG', true );
define( 'WP_DEBUG_LOG', true );
define( 'WP_DEBUG_DISPLAY', true );
```

Estos archivos los que nos ayudan con la creación de nuestro temas para ello tenemos que agregar estos archivos en `wp-config.php`



### Archivos de plantilla 

Es la estructura que tenemos que llevar para el desarrollo de nuestra plantilla 





## Subir nuestra plantilla a WordPress

los archivos importantes para que WordPress nos reconozca como plantilla tiene que haber un `index.html` y un archivo css `style.css` . Estos archivos tienen que estar en la raíz principal del tema 

### Configurar el css 

para que WordPress nos reconozca nuestra plantilla en la sección de `themes` tenemos que configurar nuestro agregar unos comentarios en  la parte principal del nuestra hoja de estilos 

```css
/*
Nombre del tema: Theme Honeymoon
Autor: view-peru.com
Autor URI: https://view-peru.com/
Descripción: Es la plantilla de honeymoon .
Versión: 1.0
Licencia: GNU General Public License v2 o posterior
Licencia URI: http://www.gnu.org/licenses/gpl-2.0.html
Dominio de texto: veintisiete
Etiquetas: una columna, dos columnas, barra lateral derecha, encabezado flexible, listo para accesibilidad, colores personalizados, encabezado personalizado, menú personalizado, logotipo personalizado, estilo editor, imágenes destacadas, widgets de pie de página, post-formatos, rtl-language-support, sticky-post, theme-options, threadded-comments, ready-translation
Este tema, como WordPress, tiene licencia bajo la GPL.
Úselo para hacer algo genial, divertirse y compartir lo que ha aprendido con los demás.
*/
```

si quieres mas detalles de este código aquí explica todo https://developer.wordpress.org/themes/basics/main-stylesheet-style-css/

