## Base de datos

Es un almacén que nos permite guardar grandes cantidades de datos de una manera organizada y esta organizado por tablas 

### Lenguaje de definición de datos 

```mysql
-- crear una base de datos
CREATE DATABASE IF NOT EXISTS proyecto;

-- usar la base de datos 
USE proyecto

-- crear tablas
CREATE TABLE productos(
	id_producto INT NOT NULL AUTO_INCREMENT,
	nombre VARCHAR(150),
	precio INT,
	PRIMARY KEY (id_producto)
);

-- unión de tablas

CREATE TABLE pedidos(
	id_pedido INT NOT NULL AUTO_INCREMENT,
	fecha DATE,
	cantidad INT,
	PRIMARY KEY (id_pedido),
	id_cliente INT,
	id_producto INT,
	FOREIGN KEY (id_cliente) REFERENCES clientes(id_cliente),
	FOREIGN KEY (id_producto) REFERENCES productos(id_producto)
);

-- borrar la base de datos
DROP DATABASE proyecto;

-- borrar una tabla 
DROP TABLE productos 

-- modificar una tabla o renombrar un tabla 
ALTER TABLE usuarios RENAME pedidos;
-- renombrar propiedades de las tablas 
ALTER TABLE clientes CHANGE telefono celular INT(11);

-- agregar nueva columna 
ALTER TABLE clientes ADD COLUMN (direccion VARCHAR(20)); 	

-- eliminar columnas 
ALTER TABLE clientes DROP COLUMN direccion;
```

### Lenguajes de manipulación de datos 

```mysql

-- INSERTAR 
INSERT INTO clientes (nombre,apellido,edad,telefono) VALUES ('Jerry','Apaza',20,123456789);

-- UPDATE
UPDATE clientes SET apellido='Apaza yllatupa' WHERE id_cliente = 1;
UPDATE clientes SET apellido='Apaza yllatupa' WHERE id_cliente BETWEEN 2 AND 4; # para actualizar muchas columnas con un mismo valor 


-- DELETE 
DELETE FROM clientes WHERE id_cliente BETWEEN 2 AND 4;
DELETE FROM clientes WHERE id_cliente= 1;

-- SELECT 
    # = 
    # AND
    # OR 
    # NOT
    # >
    # <
    # <=
    # =>
    # <> //diferente
    # != //diferente
    # BETWEEN  __AND__
    # LIKE
    # IN 
    # IS NULL
    # IS NOT NULL //nos trae los valores que no son nullos
    # LIMIT 2[DESDE], 4[HASTA]
    

#mostar una tabla
SELECT * FROM clientes;
#mostrar solo un dato
SELECT nombre FROM clientes;
#mostrar con where y de registro
SELECT nombre, apellido FROM clientes WHERE id_cliente = 5;
SELECT nombre, apellido FROM clientes WHERE id_cliente = 5 LIMIT 2, 4;
SELECT nombre, apellido FROM clientes WHERE nombre = "Jerry";
SELECT nombre, apellido FROM clientes WHERE nombre = "Jerry" AND apellido = "apaza";
SELECT nombre, apellido FROM clientes WHERE nombre = "Jerry" OR apellido = "apaza"
SELECT * FROM clientes WHERE id_cliente > 8;
SELECT * FROM clientes WHERE edad <> 20;
SELECT * FROM clientes WHERE edad != 20;
SELECT * FROM clientes WHERE id_cliente BETWEEN 6 AND 8;
SELECT * FROM clientes WHERE nombre LIKE 'J%'; // los que empiezan con
SELECT * FROM clientes WHERE nombre LIKE '%j'; // los que terminan con
SELECT * FROM clientes WHERE nombre LIKE '%j%'; // los que contienen
SELECT * FROM clientes WHERE id_cliente IN (5,6,7); // ids especificos 
# Ordenamiento
	# ODER BY
	SELECT * FROM clientes WHERE id_cliente > 8 ORDER BY nombre ;
	# ASC
	SELECT * FROM clientes WHERE id_cliente > 8 ORDER BY nombre ASC ; // por defecto
	# DESC
	SELECT * FROM clientes WHERE id_cliente > 8 ORDER BY nombre DESC ;

# Agregación 
	# COUNT
     SELECT COUNT(*) AS nombre FROM clientes WHERE nombre = "Jerry"; // que cuente cuantos 
        registros son iguales 
	# SUM 
	SELECT SUM(edad) AS edad FROM clientes WHERE nombre = "Jerry";
	# MAX
	SELECT MAX(edad) AS edad FROM clientes WHERE nombre = "Jerry"; 
	# MIN
	SELECT MIN(edad) AS edad FROM clientes WHERE nombre = "Jerry"; 
	# AVG
	SELECT AVG(edad) AS edad FROM clientes WHERE nombre = "Jerry"; // la edad media o promedio
#Agrupacion
SELECT nombre, COUNT(*) FROM clientes GROUP BY nombre ; // agrupamos los nombres que se repiten 

#Uniones
	#INNER JOIN
	SELECT * FROM clientes INNER JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente;
	SELECT * FROM clientes INNER JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente WHERE clientes.nombre ="Jerry"; // los que tienen el nombre con este valor 
	#LEFT JOIN
	SELECT * FROM clientes LEFT JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente; //muestra la tabla de la isquierda y los que estan unidos 
	#RIGHT JOIN
SELECT * FROM clientes RIGHT JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente; //muestra la tabla de la derecha y los que estan unidos 
	#MULTITABLA
	SELECT * FROM clientes INNER JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente INNER JOIN productos ON clientes.id_producto = productos.id_producto;


```

## Código final 

```mysql
# crear una tabla
CREATE DATABASE IF NOT EXISTS proyecto;
USE proyecto;

CREATE TABLE productos(
	id_producto INT NOT NULL AUTO_INCREMENT,
	nombre VARCHAR(150),
	precio INT,
	PRIMARY KEY (id_producto)
);

CREATE TABLE clientes(
	id_cliente INT NOT NULL AUTO_INCREMENT,
	nombre VARCHAR(100),
	apellido VARCHAR(100),
	edad INT,
	telefono INT,
	PRIMARY KEY (id_cliente)
);

CREATE TABLE pedidos(
	id_pedido INT NOT NULL AUTO_INCREMENT,
	fecha DATE,
	cantidad INT,
	PRIMARY KEY (id_pedido),
	id_cliente INT,
	id_producto INT,
	FOREIGN KEY (id_cliente) REFERENCES clientes(id_cliente),
	FOREIGN KEY (id_producto) REFERENCES productos(id_producto)
);

INSERT INTO clientes (nombre,apellido,edad,telefono) VALUES ('Jerry','Apaza',20,123456789);

UPDATE clientes SET apellido='Apaza yllatupa' WHERE id_cliente = 1;
UPDATE clientes SET apellido='Apaza yllatupa' WHERE id_cliente BETWEEN 2 AND 4;

DELETE FROM clientes WHERE id_cliente BETWEEN 2 AND 4;
DELETE FROM clientes WHERE id_cliente= 1;

SELECT nombre, apellido FROM clientes WHERE id_cliente = 5;
SELECT nombre, apellido FROM clientes WHERE nombre = "Jerry";
SELECT * FROM clientes WHERE edad <> 20;

SELECT * FROM clientes WHERE edad != 20;
SELECT * FROM clientes WHERE id_cliente BETWEEN 6 AND 8;
SELECT * FROM clientes WHERE nombre LIKE 'J%';
SELECT * FROM clientes WHERE id_cliente IN (5,6,7);

-- ORDENAMIENTO
SELECT * FROM clientes WHERE id_cliente > 8 ORDER BY nombre ;
SELECT COUNT(*) AS nombre FROM clientes WHERE nombre = "Jerry";

SELECT SUM(edad) AS edad FROM clientes WHERE nombre = "Jerry";

SELECT MAX(edad) AS edad FROM clientes WHERE nombre = "Jerry"; 
SELECT AVG(edad) AS edad FROM clientes WHERE nombre = "Jerry";

SELECT nombre, COUNT(*) FROM clientes GROUP BY nombre ;

SELECT * FROM clientes INNER JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente INNER JOIN productos ON clientes.id_producto = productos.id_producto;
SELECT * FROM clientes LEFT JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente 
-- DROP DATABASE proyecto;
-- DROP TABLE pedidos 
--ALTER TABLE usuarios RENAME pedidos;
-- ALTER TABLE clientes CHANGE telefono celular INT(11);
-- ALTER TABLE clientes ADD COLUMN (dirección VARCHAR(20)); 
-- ALTER TABLE clientes DROP COLUMN dirección;
```

