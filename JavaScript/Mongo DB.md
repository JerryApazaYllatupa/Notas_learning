# Mongo DB

## Instalación 

> 1. Tenemos que descargar e instar todo siguiente https://www.mongodb.com/download-center/community
> 2. Y luego instalar el  robo 3T https://robomongo.org/download
>



## Comandos

> * `db.help()`: Para obtener ayuda
>
> * `show dbs`: nos muestra las base de datos 
>
> * `db.createCollection('Alumnos')`: Para crear colecciones son como tablas
>
> * `show collections`: Para mostrar las colecciones 
>
> * `db.Alumnos.insert({name:'Jerry'})`: Para insertar contenido en una collections
>
> * `db.Alumnos.find()`:  Para mostrar los datos de las colecciones 
>
> * `db.Alumnos.find({name:'Jerry'})` Y  también de esta forma podemos buscar elementos 
>
> * `db.Alumnos.drop()`: Para eliminar esa colección 
>
> * `db.Alumnos.remove({name:'Jerry'})`: Eliminar desde un dato del documento
>
> * `db.users.insertMany(
>         [{}])` : Para insertar varios archivos
>
>   >```mariadb
>   >db.users.insertMany(
>   >      [
>   >        {
>   >        user:'@test1',
>   >        user_date:ISODate(),
>   >        email:'test1@gmail.com',
>   >        password:'mys password'
>   >        },
>   >        {
>   >        user:'@test2',
>   >        user_date:ISODate(),
>   >        email:'test2@gmail.com',
>   >        password:'mys password'
>   >        },
>   >        {
>   >        user:'@test3',
>   >        user_date:ISODate(),
>   >        email:'test3@gmail.com',
>   >        password:'mys password'
>   >        }
>   >     ]
>   >    )
>   >```
>
> * `db.users.update({},{$set:{}})`: Para solo actualizar un dato del documento 
>
>   > ```mariadb
>   > db.users.update(
>   > {user:'@test1'},
>   > { 
>   >     $set:{
>   >         email:'test1@test1.com'
>   >      }
>   > }
>   > 
>   > )
>   > // tambien podemos agregar un nuevo campo a un documento 
>   > db.users.update(
>   > {user:'@test1'},
>   > { 
>   >     $set:{
>   >         web:'www.test1.com'
>   >      }
>   > }
>   > 
>   > )
>   > 
>   > // $unset lo que haces es quitar un atributo al documento 
>   > db.users.update(
>   > {user:'@test1'},
>   > { 
>   >     $unset:{
>   >         web:'www.test1.com'
>   >      }
>   > }
>   > 
>   > )
>   > //push  nos crea un arreglo si esque el atributo no lo es y si es entoces lo que hace es que agrega un nuevo valor 
>   > db.users.update(
>   > {user:'@test1'},
>   > { 
>   >     $push:{
>   >         web:'www.test1.com'
>   >      }
>   > }
>   > )
>   > // pull para quitar un dato de ese arreglo que ingresamos y le 
>   > db.users.update(
>   > {user:'@test1'},
>   > { 
>   >     $pull:{
>   >         web:'www.test1.com'
>   >      }
>   > }
>   > 
>   > )
>   > 
>   > //inc nos actuliza atributos númericos 
>   > db.users.update(
>   > {user:'@test1'},
>   > { 
>   >     $inc:{
>   >         saldo:100
>   >      }
>   > }
>   > 
>   > )
>   > // con este renombramos un atributo del las documento 
>   > db.users.update(
>   > {user:'@test1'},
>   > { 
>   >     $rename: {
>   >         user_mane: 'user_name'
>   >      }
>   > }
>   > 
>   > )
>   > // udateMany y {} para actualizar a todos los archivos
>   > db.users.updateMany(
>   > {},
>   > { 
>   >     $set: {
>   >         bio: 'Biografia del Usuario'
>   >      }
>   > }
>   > 
>   > )
>   > ```
>
> * `db.users.find().short({})`: Para ordenar 
>
>   > ```mariadb
>   > //positivo de forma acendenter
>   > //negativo de forma desendente
>   > db.users.find().sort({user:-1})
>   > db.users.find().sort({_id:-1},
>   >                     {user:1})
>   > ```
>
> * `db.users.find(user:'@user').count()`: para contar un registro 
>
>   > ```mariadb
>   > db.users.find().count()
>   > 
>   > ```
>
> * `db.users.find({email:/@gmail/})`: Para filtrar documentos
>
>   > ```bash
>   > db.users.find({email:/@gmail/})
>   > db.users.find({email:/.com$/}) //cuando termina
>   > db.users.find({email:/^Jerry/}) // para indicarle que inicia con
>   > 
>   > //Para buscar por atributo de un arreglo
>   > db.users.find({'user_name.first':'Jerry'})
>   > // para tre 3 hijos adentros mas 
>   > db.users.find({'user_name.action.caminar.trotar': /30/ })
>   > ```
>   >
>   > 



