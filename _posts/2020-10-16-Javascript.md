---
layout: post
title: "Javascript"
---

# Conocimientos esenciales
- [Estructura del código](https://es.javascript.info/javascript-specials#estructura-de-codigo)
- [Modo estricto](https://es.javascript.info/javascript-specials#modo-estricto)
- [Variables](https://es.javascript.info/javascript-specials#variables)
- [Interacción](https://es.javascript.info/javascript-specials#interaccion)
- [operadores](https://es.javascript.info/javascript-specials#operadores)
- [Bucles](https://es.javascript.info/javascript-specials#bucles)
- [Switch](https://es.javascript.info/javascript-specials#el-constructo-switch)
- [Funciones](https://es.javascript.info/javascript-specials#funciones)
- [Debugging](https://es.javascript.info/debugging-chrome)
- [Buenas prácticas en el anidamiento](https://es.javascript.info/coding-style#niveles-anidados)
- [Guías de estilo para un código más legible](https://es.javascript.info/coding-style#niveles-anidados)
- [Comentarios correctos](https://es.javascript.info/comments#comentarios-correctos)
- [Cómo escribir código ninja](https://es.javascript.info/ninja-code)
- [Cómo hacer test con mocha](https://es.javascript.info/testing-mocha)


# Typeof
Para saber qué tipo de dato contiene una variable, escribir:
```js
// Cualquiera de las dos formas es válida
typeof _variable_
typeof(_variable_)
```
> Devolverá un string indicándonos qué tipo de dato contiene la variable.

# Conversiones de tipos
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

# Operador ternario ``?``
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

# Operador `??`
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

# Switch
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

# Functiones Callbacks
> https://es.javascript.info/function-expressions#funciones-callback

```js
function pregunta(ask, yes, no) {
  if (confirm(ask)) yes()   // Según la lógica le incluimos los paréntesis
  else no();                // y es invocada la función.
}

function meGusta() {
    alert('Me gusta pescar');
}

function noMeGusta() {
  alert('No me gusta pescar');
}

// Las funciones son variables que retornan undefined
// Al no incluirle los paréntesis, no las estamos llamando.
pregunta('¿Te gusta pescar?', meGusta, noMeGusta);
```

# Functiones de flecha
> https://es.javascript.info/arrow-functions-basics

```js
// Forma tradicional (this y new no podrán obtener del padre)
let dato = function() {
  alert('Soy un dato');
}

// Función de flecha a una línea
let dato2 = () => alert('Soy un dato2');

// Función de flecha multilínea
let dato3 = (arg1, argEtc) => {
  alert('Soy un dato con argumentos');
  return;
};
```




