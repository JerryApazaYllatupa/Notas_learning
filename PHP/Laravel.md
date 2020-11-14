## Composer 

```bash
composer global require laravel/installer
composer install 
composer update

laravel new nameProyect #para crear un nuevo proyecto 


```

Para crear controladores con php artisan 

```bash
php artisan make:controller namConroller 
php artisan make:controller namConroller --source
```

Como implementar un modelo

```bash
$ php artisan make:model 'App\Entitis\Estudiante'
```

Llamar un nombre de la base de datos especifico, esto generalmente se utiliza en los models

```php
<?php

namespace App\Entitis;

use Illuminate\Database\Eloquent\Model;

class Estudiante extends Model
{
    protected $table = "students";
}

```

Conectar un model con un controller

```php
use App\Entitis\Estudiante;
use App\Entitis\{Estudiante,Tarea, Ususario};

```

## Rutas

```php+HTML
Route::get('/', function () {
    return view('welcome');
});

Route::resource('estudiantes','EstudianteController');
// get - post - delete  - put -  show

Route::get('/tareas/buscar','TareasController@buscar')->name('tareas.buscar');

Route::get('tareas/{id}/ver','TareasController@ver')->name('tareas.ver');

<a href="{{route('tareas.ver',['id' => 1])}}">Ver id</a>
<a class="menu-text menu-text--child" href="{{route('admin','list-files')}}">Library</a>

php artisan route:list
```

Es importante el / o ulr() para llamar recursos 

## Migraciones

```php
php artisan migrate 
//crear tablas
php artisan make:migration create_tareas_migrate
    php artisan make:migration create_itinearies_table --create=itinearies // para crear la tabla en la base de datos
        
//Comandos
php artisan migrate:rollback //Deshacer la ultima migracion ejecutada en la base de datos 
php artisan migrate:reset // Deshacer todas las migraciones nos va dejar la base de datos sin nunguna en la tabla 
php artisan migrate:refresh // actualizar las migraciones 
    
    
 //Comando basicos 
    
 php artisan migrate:status
     // tablas 
   $table->bigIncrements('id');
  $table->string('title', 300);
  $table->text('description')->nullable();
  $table->string('img', 200)->default('default-post.jpg');
  $table->boolean('visibility')->default(1);
  $table->boolean('trash')->default(0);
  $table->unsignedBigInteger('category_id');
  $table->foreign('category_id')->references('id')->on('categories');
  $table->json('permalink');
  $table->timestamps();
```

## Seeders

nos ayuda a llenar nuestras tablas para no hacer de manera manual 

adecuado para catalogos 

```php
#crear new seed 
php artisan make:seed CategorySeederTable
    
#Ejecutar los seeders
 php artisan db:seed --class="CategorySeederTable"
```

## Fechas

```php
['fecha'=>\Carbon\Carbon::now()->format('Y-m-d H:i:s')] //obtener hora actual 
```

## LLenado de base de datos

```php
//union de tablas  
$table->unsignedBigInteger('category_id');
  $table->foreign('category_id')->references('id')->on('categories');
```

### Model factory 

Crear registros con información falsa  para ejecutar pruebas automatizadas En el archivo especificamos  

```php
php artisan make:factory nombreFactory
php artisan make:factory nombrefactory --model=Nombre
```

## Eloquent 

ORM

## Conversiones 

-  El nombre de los modelos debe ser singular, en la BD debe ser plural 
- Notación UpperCamelCase
- Hace el mapeo si seguimos las convenciones 
- si usamos underscore entonces 
  - user_profiles => UserProfile
- Protected $table = 'user_profiles'



```php

```

## Consultas

## Relaciones

- validar los campos que el usuario va insertar
- tenemos que conectar con funciones en lo models de cada tabla 

```php

protected $fillable = ['title','description','img','visibility','trash','permalink'];
```

## Repositorios 

los repositorios 

1. crear la carpeta repositories en Http
2. crear el archivo
3. allí creamos todas las consultas que necesitamos y luego reutilizar en cualquier otro lado 

```php
// extender este model 
public function Categories(){
    return $this->belongsTo(Category::class);
  }

//lamar el model desde el otro model 
 public function Posts(){
      // uno a muchos
      return $this->hasMany(Post::class);
    }
```



```php
<?php

namespace App\Repositories;

use App\Entitis\Post;


class PostRepository
{

  public function getByIdCategory($id)
  {
    return Post::where('id', $id)->orderBy('created_at', 'asc')->get();
  }
  public function getLimit($limit)
  {
    return Post::limit($limit)->get();
  }
}
//en este archivo no es necesario ya hacer el innerjoin()

```

para  mover los archivos a  public

```php
$ php artisan storage:link
```

## autentícate 

```
composer require laravel/ui
php artisan ui vue --auth
```

```php
@if(Auth::user()->hasRole('admin'))

  @else

  @endif
```

Nuevos casas

```php
dd($variable) // para mostrar el valor de una variable 
```

