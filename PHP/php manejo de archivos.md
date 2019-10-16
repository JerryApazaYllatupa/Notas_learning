[TOC]

# Como subir un archivos con php

En este contenido iremos explicando como podemos subir archivos con php 

## Configuración de  las opciones del servidor  de php

esta configuración que veremos a continuación son de suma importancia para la subida de archivos correctamente para esto entonces tenemos que abrir el archivo del servidor que en este caso es ` php.init`

Si no estas seguro de donde se encuentra el archivo `php.init ` crea un archivo de php y ejecuta este código `<?php echo php_ini_loaded_file(); ?>` este te dará la ubicación del archivo

Al abrir el archivo tenemos que modificar algunos valores

```tcl
; Whether to allow HTTP file uploads.
file_uploads = On
 
; Temporary directory for HTTP uploaded files.
; Will use system default if not set.
;upload_tmp_dir = 
 
; Maximum allowed size for uploaded files.
upload_max_filesize = 16M
 
; Maximum number of files that can be uploaded via a single request
max_file_uploads = 20
 
; Maximum size of POST data that PHP will accept.
post_max_size = 20M
 
max_input_time = 60
memory_limit = 128M
max_execution_time = 30
```

### Descripciones de cada código

* `file_uploads`: El valor de la directiva `file_uploads` Se debe establecer en `on` Para permitir la carga de archivos y el valor por defecto esta en `false`
* `upload_max_filesize`: Te permite configurar le tamaño máximo del archivo cargado. De forma predeterminada se establecen en `2em` (2 megabytes), y puede anular esta configuración utilizando el archivo `.htaccess`. Dos megabytes no son muchos para los estándares de hoy, por lo que es necesario aumentar esto. si recibes un error de cuando el ` archivo excede upload_max_filesize ` cuando intenta cargar un archivo, debes aumentar el valor  de este, pero si cambiamos este valor también es necesario cambiar el valor de `post_max_size`(que esta mas abajo)
* `upload_tmp_dir`: Establece un directorio temporal que se utiliza para almacenar los archivos cargados. En la mayoría de los casos no necesitas preocuparte por esta configuración. Si no lo configuras, se utilizar el directorio temporal del sistema 
* `post_max_size`: Te permite configurar el tamaño máximo de los datos POST, dado que los archivos se cargan con solicitudes POST, este valor tiene que ser mayor a lo que estableciste en la directiva ` upload_max_filesize `, Por ejemplo, si tu` upload_max_filesize` es `16M` (16 megabytes), es posible que desee establecer `post_max_size` en `20M` .
* ``max_file_uploads``: Te permite establecer el número máximo de archivos que se pueden cargar a la vez. el valor predeterminado es 20, una cantidad razonable 
* ``max_input_time``: Es el número máximo de segundos que un script pueda analizar los datos de entrada, Debe establecerlo en un valor razonable si está tratando con cargas de archivos grandes `60`(60) segundos es un valor  para la mayoría de las aplicaciones 
* `memory_limit`: Indica la cantidad máxima de memoria que se puede consumir un script, si tienes problemas durante la carga de archivos grandes, debe asegurarse de que el valor de esta directiva sea mayor de lo que estableció para la directiva ` post_max_size `. El valor predeterminado es `128MB`(128Megabytes) así que, a menos que tengan un ` post_max_size ` y ` upload_max_filesize ` muy grande no debe preocuparse por esto.
* `max_execution_time`: Es el segundo máximo que se permite ejecutar un script, si tiene problema durante la carga de archivos grandes, puede considerar aumentar este valor 30 (segundos) deberían funcionar bien para la mayoría de las aplicaciones 



## Vamos al ejemplo de como subir archivos

###  Crear el formulario HTML

Para este ejemplo vamos a crear estos dos archivos en un carpeta `index.php`,`upload.php` y por ultimo una carpeta `uploaded_files` 

En el archivo `index.html` tendremos este código 

```php+HTML
<?php
session_start(); 
?>
<!DOCTYPE html>
<html>
<head>
  <title>PHP File Upload</title>
</head>
<body>
  <?php
    if (isset($_SESSION['message']) && $_SESSION['message'])
    {
      printf('<b>%s</b>', $_SESSION['message']);
      unset($_SESSION['message']);
    }
  ?>
  <form method="POST" action="upload.php" enctype="multipart/form-data">
    <div>
      <span>Upload a File:</span>
      <input type="file" name="uploadedFile" />
    </div>
 
    <input type="submit" name="uploadBtn" value="Upload" />
  </form>
</body>
</html>
```

Enfoquemos no primero en el formulario en este formulario tenemos el atributo `enctype` ,Es importante configurar este atributo cuando deseamos manejar archivos 

El atributa `enctype=""`: especifica el tipo de codificación que se debe de usar cuando se envía el formulario y este toma uno de estos 3 valores 

-  `"application / x-www-form-urlencoded"`: Este es valor predeterminado cuando no se establece el valor del atributo. En este caso, los caracteres se decodifican antes de que se envíe al servidor, esto no afecta en nada al contenido plano pero si tenemos el elemento de archivo en el formulario  hay si tenemos que utilizar este siguiente valor.
- `"multipart / form-data"`:  Este te permite cargar archivos utilizando El método POST, Además se asegura que los caracteres no estén decodificados cuando se envía el formulario 
- `"text / plain"`: Generalmente no se usa. Con este configuración los datos se envían sin decodificar 

A continuación tenemos el elemento 

```html
  <input type="file" name="uploadedFile" />
```

este campo nos permite seleccionar un archivo de su computadora 

Aparte de eso tenemos este código de php que es para mostrar el mensaje de estado de carga del archivo y el script `upload.php` lo configura en una variable de  `session`. Veremos mas de esto en la siguiente sección 

```php
<?php
    if (isset($_SESSION['message']) && $_SESSION['message']){
      printf('<b>%s</b>', $_SESSION['message']);
      unset($_SESSION['message']);
    }
?>
```

 Así que eso resume el archivo `index.php`. En la siguiente sección, veremos cómo manejar el archivo cargado en el lado del servidor. 

## Crear lógica de la carga

En esta sección veremos como validar la carga del archivo hacia el servidor y en el archivo `upload.php` tenemos este código 

```php
<?php
session_start();
$message = ''; 
if (isset($_POST['uploadBtn']) && $_POST['uploadBtn'] == 'Upload'){
  if (isset($_FILES['uploadedFile']) && $_FILES['uploadedFile']['error'] === UPLOAD_ERR_OK){
    // get details of the uploaded file
    $fileTmpPath = $_FILES['uploadedFile']['tmp_name'];
    $fileName = $_FILES['uploadedFile']['name'];
    $fileSize = $_FILES['uploadedFile']['size'];
    $fileType = $_FILES['uploadedFile']['type'];
    $fileNameCmps = explode(".", $fileName);
    $fileExtension = strtolower(end($fileNameCmps));
    // sanitize file-name
    $newFileName = md5(time() . $fileName) . '.' . $fileExtension;
    // check if file has one of the following extensions
    $allowedfileExtensions = array('jpg', 'gif', 'png', 'zip', 'txt', 'xls', 'doc');
    if (in_array($fileExtension, $allowedfileExtensions)){
      // directory in which the uploaded file will be moved
      $uploadFileDir = './uploaded_files/';
      $dest_path = $uploadFileDir . $newFileName;
      if(move_uploaded_file($fileTmpPath, $dest_path)) 
      {
        $message ='File is successfully uploaded.';
      }else {
        $message = 'There was some error moving the file to upload directory. Please make sure the upload directory is writable by web server.';
      }
    }else{
      $message = 'Upload failed. Allowed file types: ' . implode(',', $allowedfileExtensions);
    }
  }else{
    $message = 'There is some error in the file upload. Please check the following error.<br>';
    $message .= 'Error:' . $_FILES['uploadedFile']['error'];
  }
}
$_SESSION['message'] = $message;
header("Location: index.php");
```

En primer código que tenemos es 

```php
if (isset($_POST['uploadBtn']) && $_POST['uploadBtn'] == 'Upload') {
...
}
```

En este código estamos comprobando si el método POST si se trata de una solicitud válida.

En PHP, Cuando se carga un archivo la variables superglobal `$_FILES[]`  se rellena con toda la información del archivo cargado. Se inicializa como un arreglo y contiene toda la información para la carga exitosa del archivo y este variable global tiene estas propiedades.

-  `tmp_name`: La ruta temporal donde se carga el archivo se almacena en esta variable 
- `name`: El nombre real del archivo se almacena en esta variable
- `size`: Indica el tamaño del archivo cargado.
- `type`: Contiene el tipo de mime del archivo cargado
- `error`: Si hay un error durante la carga del archivo, esta variable se rellena con el mensaje del error , en caso que el archivo se cargue correctamente el archivo devuelve 0 que se puede comparar utilizando la constante `UPLOAD_ERROR_OK` 

Después de verificar la solicitud POST, Verificamos que la carga del archivo se realizo correctamente 

```php
 if (isset($_FILES['uploadedFile']) && $_FILES['uploadedFile']['error'] === UPLOAD_ERR_OK){}
```

Puede ver que la variable global `$_FILES[]`, Es un arreglo multidimensional, El primer elemento es el nombre del campo de archivo y el segundo tiene la información sobre el archivo cargado, como acabamos de comentar sobre las propiedades de la variable global files	

Luego Inicializamos las variables para obtener el archivo 

```php
// get details of the uploaded file
$fileTmpPath = $_FILES['uploadedFile']['tmp_name'];
$fileName = $_FILES['uploadedFile']['name'];
$fileSize = $_FILES['uploadedFile']['size'];
$fileType = $_FILES['uploadedFile']['type'];

$fileNameCmps = explode(".", $fileName);
$fileExtension = strtolower(end($fileNameCmps));
```

Como el archivo cargado puede contener espacios y otros caracteres especiales, es mejor limitar el nombre del archivo,y eso es exactamente lo que hemos echo en este código 

```php
$newFileName = md5(time() . $fileName) . '.' . $fileExtension;
```

Es importante la restricción el tipo de archivo que se pueda mover o guardar al directorio y esta validación lo hemos echo al verificar la extensión del archivo cargado con un conjunto de extensiones que queremos permitir la carga 

```php
$allowedfileExtensions = array('jpg', 'gif', 'png', 'zip', 'txt', 'xls', 'doc');
if (in_array($fileExtension, $allowedfileExtensions)) {
...
}
```

Finalmente, usamos  la función  `move_uploaded_file`  Para mover el archivo cargado a la ubicación específica de nuestra elección 

```php
// directory in which the uploaded file will be moved
$uploadFileDir = './uploaded_files/';
$dest_path = $uploadFileDir . $newFileName;
 
if(move_uploaded_file($fileTmpPath, $dest_path)){
  $message ='File is successfully uploaded.';
}else{
  $message = 'There was some error moving the file to upload directory. Please make sure the upload directory is writable by web server.';
}

```

La función `move_uploaded_file` toma dos argumentos. El primer argumento es el nombre de archivo del archivo cargado, y el segundo argumento es la ruta de destino a la que desea mover el archivo. 