[TOC]



# Paradigmas de programación 

## ¿Que es un paradigma de programación ?

En programación sería un modelo que nos permite tener una base para poder resolver un problema pueda que sea buena para algunos problemas y pueda  que no se bueno para otros, pero es una base en lo que podemos basarnos para poder resolver problemas .

## Paradigmas más usadas 

- Programación Estructurada / Imperativa 
- Programación Declarativa 
- Programación orientada a objetos
- Programación dirigida por eventos 
- Programación funcional 
- Programación multiparadigma 

### Programación Estructurada / Imperativa

La programación Estructurada o imperativa como su nombre los dice **Emperador**  "le dices el ***qué*** debe hacer el programa y también el ***como*** se va hacer ". Es decir que se debe de hacer y como, es la sugerida para aprender a programar

La gran mayoría de los lenguajes de programación adoptan este paradigma 

### Programación declarativa 

La programación declarativa " Se indica ***qué*** se debe de hacer, pero generalmente no se indica el ***como***". Este paradigma utilizan los lenguajes SQL para los motores de base de datos relacionales 

### Programación Orientada a Objetos 

El paradigma más utilizado en los lenguajes de programación. Abstrae los problemas identificado todos los actores como objetos. Los objetos tienes atributos y acciones o comportamientos, otro de su objetivo principal es el de reutilizar código 

### Programación funcional 

Este paradigma lleva mucho tiempo en el mercado, unos de los problemas para este paradigma  es la falta de recursos tecnológicos, Por que la programación funcional requiere de mucha potencia de computo , como por ejemplo la recursividad es una de las base de la PF. "No hay ciclos", sino que todo se basa en notaciones matemáticas  

### Programación Dirigida por eventos 

La estructura y la ejecución del programa va determinadas por los sucesos que puedan ocurrir en el sistema un ejemplo seria. Al hacer click, al mover el mouse, al mostrar un mensaje, este paradigma se encuentra mas en el lenguaje de JavaScript.   

### Programación Multiparadigma

Muchos lenguajes de programación actuales permiten programar con los diferentes paradigmas mencionados anteriormente 

## Ejercicios

```javascript
// Estructurada

const factorial = (n) => {
	let res = 1;
	for (let i = 1; i <= n; i++) {
		res *= i;
	}
	return res;
};
console.log(factorial(5));

//Recursividad
const factorialConRecursividad = (n) => {
	if (n == 0 || n == 1) {
		return 1;
	}
	return factorialConRecursividad(n - 1) * n;
};
console.log(factorialConRecursividad(5));

```

