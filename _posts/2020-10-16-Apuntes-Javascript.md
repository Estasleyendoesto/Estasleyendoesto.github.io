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


