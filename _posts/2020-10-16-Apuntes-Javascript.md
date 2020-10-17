---
layout: post
title: "Apuntes de Javascript"
---

## Use strict
Para poder usar las versiones modernas de Javascript dentro de las funciones y el documento es Javascript antiguo. Escribir en la primera línea de la función:
```js
'use strict';
```
> En caso que el documento tenga Javascript moderno, no es necesario incluir esta instrucción. En caso de querer incrustarlo, en la primera línea del documento.

## Typeof
Para saber qué tipo de dato contiene una variable, escribir:
```js
// Cualquiera de las dos formas es válida
typeof _variable_
typeof(_variable_)
```
> Devolverá un string indicándonos qué tipo de dato contiene la variable.

## Conversiones de tipos
Para convertir un entero a string y viceversa, escribiremos:
```js
// Convierte un tipo de dato cualquiera a string
value = String(value)

// Convierte un tipo de dato cualquiera a float o integer
num = Number(undefined) // NaN
num = Number(null)      // 0
num = Number('123')     // 123
num = Number(true)      // 1 o 0
num = Number('123b')    // NaN

/* Convierte un tipo de dato cualquiera en booleano
*  Strings vacíos, undefined, NaN o 0 será false
*  Todo lo que tenga algún tipo de contenido será true
*/
boo = Boolean(0)
boo = Boolean('Pepe')
```

## Operadores
> Excelente resumen de los operadores:
  https://es.javascript.info/operators

## Operador ternario ``?``
Es una forma resumida de `if/else` e incluso podemos anidarlo como `elseif` pero no lo recomiendo por ser poco legible. Quedémonos solo en usarlo como reemplazo de `if/else`.
```js
// Forma tradicional
let dato = '';
if (5 > 2){
  dato = 'correcto';
} else {
  dato = 'Incorrecto';
}

// Operador ternario "?"
let dato = 5 > 2 ? 'correcto' : 'incorrecto';

// También podemos usar if con una sola línea, por ejemplo para llamar a una función.
if (5 > 2) myFunction();
```

## Operador `??`
> Su uso solo está disponible para navegadores moderlos. Los antiguos pueden necesitar polyfills.

Este operador es usado para asignar valores por defecto a las variables:
```js
// Asignar height=100, si height es null o undefined
height = height ?? 100;

// Otro ejemplo
let firstName = null;
let lastName = null;
let nickName = "Supercoder";
// Muestra la primera variable que no sea null/undefined
alert(firstName ?? lastName ?? nickName ?? "Anonymous"); // retorna 'Supercoder'

// El operador ?? tiene una precedencia muy baja, un poco más alta que ? y =
// Está prohibido su uso con || y && sin paréntesis explícitos
```

## Switch
Una sentencia switch puede reemplazar múltiples condiciones if. Provee una mejor manera de comparar un valor con múltiples variantes.
```js
// x es una variable
// Puede ser numérico, string o booleano.
// Los case deben tener su mismo tipo de dato.
switch(x){
  case 0:
    console.log();
    break;
  case 1:          // Podemos agrupar varios case que compartan
  case 2:          // el mismo código.
    console.log();
    break;
  default:
    console.log();
    break;
}
```

## Funciones
> https://es.javascript.info/function-basics
> https://es.javascript.info/function-expressions

```js
// Podemos crear una variable con una función en su interior
let saludo = function(){
  return 'Hola';
};    // Recordar el ";" pues estamos declarando una variable.

let saludo2 = saludo // podemos copiar una variable con su función


// Callbacks
function pescar(ask, yes, no) {
  if (confirm(ask)) yes()
  else no();
}

function meGusta() {
    alert('Me gusta pescar');
}

function noMeGusta() {
  alert('No me gusta pescar');
}

// Las funciones son variables que retornan undefined
// Al incluirles los paréntesis los estamos invocando
pescar('¿Te gusta pescar?', meGusta, noMeGusta);
```




