## vagrant

1. Descargar vargrant y virtualbox

## Instalación de  Homestead

1. Descargar la maquina virtual y homestead 

   ```bash
   vagrant box add laravel/homestead
   ```

2. clonar el paquete de homestead 

   ```bash
   git clone https://github.com/laravel/homestead.git ~/Homestead
   ```

   

3. ingresamos en la ruta 

   ```bash
   cd ~/Homestead
   git checkout release
   ```



Algo importante es que cuando agregamos nuevos sitios a nuestra configuración de homestead tenemos que refrescar y para ello utilizamos este comando 

```bash
vagrant reload --provision
```

Comando para ejecutar nuestro servidor de homestead 

```bash
#ejecutar el servidor
vagrant up
#despues ejecutar el comando para acceder a la maquina 
vagrant ssh

#apagar el servidor
vagrant destroy
```

## Controladores y modelos

```bash
php artisan make:controller PhotoController --resource --model=Photo

```

### Como ejecutar comandos de artisan desde la web 

```php
Route::get('/createController', function () {
  Artisan::queue('make:controller MyController');
});

```



## Rutas 

#### Métodos de enrutador disponibles

```php
Route::get($uri, $callback);
Route::post($uri, $callback);
Route::put($uri, $callback);
Route::patch($uri, $callback);
Route::delete($uri, $callback);
Route::options($uri, $callback);
```



## Blade 

```php+HTML
//llenar el yield
<h1>@yield('title') </h1>

//la manera de llenar  la sección sin tener que cerrar la sección 
 @section('title','Este es el titulo de la categoria')
```

## Cache

```php
// ============ Comands =========
Route::get('/configCache', function () {
  Artisan::queue('config:cache');
});

```

```php
Route::get('/activeRute', function () {
  Artisan::queue('storage:link');
});

Route::get('/configCache', function () {
  Artisan::queue('config:cache');
});

```

