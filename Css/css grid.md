# CSS GRID

## Conocimiento para entender css grid

Es importante conocer estos temas

* CSS básico 
* HTML básico 
* Un poco de flexblox 
* y que entiendas de maquetación de un plantilla 

## Conceptos básicos de css grid 

presenta un sistema de cuadrícula bidimensional para CSS. Las 
cuadrículas se pueden utilizar para posicionar áreas principales de la 
página o pequeños elementos de la interfaz de usuario.

ut contiene funciones dirigidas a los desarrolladores de aplicaciones web. El css grid se puede utilizar para lograr muchos diseños diferentes. También se destaca por permitir dividir una pagina web en Áreas  o regiones principales, por definir la relación de tamaño, posición y capas entre partes de un control construido a partir de primitivas HTML

Al igual que las tablas, el grid layout permite a un autor alinear elementos en columnas y filas. Sin embargo, Con css grid son muchos más y forma mas sencilla que con las tablas. Por ejemplo, los elementos secundarios  de un contenedor de cuadricula podrían posicionarse para que se solapen y se superpongan, de forma similar a los elementos posicionados en css

​			

### ¿Qué es una cuadrícula(grid)?

Una cuadrícula es un conjunto de líneas horizontales y verticales que se
interceptan - un grupo define columnas y el otro filas. Los elementos 
se pueden colocar en la cuadrícula respetando estas columnas y filas. El

### diseño de cuadrícula CSS tiene las siguientes características:

### Tamaños fijos y flexibles 

Es tema abarca mas para creaciones de cuadriculas por ejemplo cuando queremos crear cuadriculas con tamaños fijos podemos utilizar `px` y para cuadriculas flexibles utilizas las medidas que son como por ejemplo `%`, `em`, etc. Y la nueva unidad de medida  `fr` que es (fracción) diseñada para el propósito de las cuadriculas flexibles 

### Posicionamiento de elementos

Css grid lo que nos permite es que podemos colocar elementos en cualquier parte de la cuadricula o super poner elementos, y la cosa mas importante de css grid es "*no importa el orden en que están creados los elementos*", y para el poner un elemento donde quieras se utilizar los números de líneas y nombres de secciones 

### Creación de líneas adicionales para alojar contenido 

Cuando definimos cuadriculas desde `css grid`  a esta se le dice cuadricula *explícita*   y cuando nos los definimos como cuadricula, css grid nos lo define por nosotros y a esta cuadricula se le dice cuadricula *implícita* 

### Control de alineación

Grid contiene características de alineación para poder controlar la 
forma cómo se alinean los elementos una vez colocados en un área de 
cuadrícula y cómo está alineada toda la cuadrícula.

### Control de contenido superpuesto

Se pueden colocar más de un elemento en una celda de la cuadrícula o área, las cuales se pueden superponerse total o parcialmente entre sí. Esta estratificación puede ser controlada con propiedad de `z-index`

## Ejemplo básico 

Para la explicación de  ejemplos de css grid estaremos utilizando estos archivos

1. carpeta principal "css grid"

2. Dentro de la carpeta tenemos estos archivos `index.html` una carpeta `css` , dentro de la carpeta vamos a crear dos archivos .css `main.css` y  `grid.css`

   ![1569687534291]($%7BImagenes%7D/1569687534291.png) 

En el archivo `index.html` Tenemos este código 

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>CSS grid </title>
  <link rel="stylesheet" href="css/main.css">
  <link rel="stylesheet" href="css/grid.css">
</head>

<body>
  <div class="header">
    <p>CSS GRID</p>
  </div>
  <!-- Contenido grid -->
  <div class="container">
    <div class="item">Item One</div>
    <div class="item">Item Two</div>
    <div class="item">Item Three</div>
    <div class="item"> Item Four</div>
    <div class="item"> Item Five</div>
    <div class="item">Item Six</div>
  </div>
  <!-- Fin content grid -->
</body>

</html>
```

En la carpeta `main.css` Tenemos estos estilos para formatear el html

```css
* {
  margin: 0;
  padding: 0;
}

body {
  background-color: #eeee;
  color: #000;
  font-family: "roboto", sans-serif;
}

.header p {
  font-size: 50px;
  text-align: center;
  padding: 20px 0;
}

.container {
  background-color: lightblue;
  max-width: 700px;
  margin: auto;
}
.item {
  padding: 1em;
  background-color: blueviolet;
  color: white;
  margin: 5px 0;
}

```



Y en la archivo `grid.css` vamos trabajar la explicación de cada concepto de css grid 

y al final lo que tendríamos en el navegador es este diseño

![1569688026347]($%7BImagenes%7D/1569688026347.png)



## Propiedades de css grid

* `grid-template-columns: none | 100px | 1fr | minmax(100px, 1fr) | fit-content(40%) | repeat(3, 200px)  ` : Para construir columnas

  ```css
  .container {
    display: grid; //con esta propiedad le decimos que el container ya es una cuadricula 
    grid-template-columns: 50% 50%; // estamos creando dos columnas y cada una con el tamaño de 50%
  }
  
  ```

  ![1569688458197]($%7BImagenes%7D/1569688458197.png)

  Como explicamos no solo podemos crear con `%` si no que también podemos utilizar las diferentes unidades de medidas 

  ```css
  .container {
    display: grid;
    grid-template-columns: 500px 1fr;
  }
  ```

  

*  grid-template-rows: Para las filas

* grid-gap: para la separación de las celdas

* repeat(): Repite cuantas veces quieras una medida

* fr: Para completar el espacio disponible 

  > ```css
  > 
  > .container{
  >   display: grid;
  >   grid-template-columns: 10% 80%;
  >   grid-template-rows: 100px;
  >   grid-gap: 10px;
  > }
  > .item{
  >   border: 1px solid black;
  > }
  > .item img{
  >   width:100%;
  >   height: 100%;
  >   object-fit:cover;
  > }
  > ```
  >
  > 

* `grid-column: [start] / [end]`: Para posicionar una celda en cualquier parte del grid   

  > ```css
  > //Para hacer responsive 
  > grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
  > ```
  >
  > 

* `grid-auto-rows: 100px`: Para darle tamaño cuando posicionamos un elemento en un espacio implicito

* `grid-auto-flow:row, column | row, column dense` : Para cambiar el tipo de render y para llenar los huecos