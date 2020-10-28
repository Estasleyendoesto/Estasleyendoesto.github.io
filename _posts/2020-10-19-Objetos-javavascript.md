---
layout: post
title: "Objetos en Javascript"
---

Los objetos en JavaScript son por referencia. A diferencia de una variable, si hacemos una copia como `let nombre2 = nombre` la variable `nombre2` es una copia de `nombre`.
Pero con los objetos es distinto. La copia de un objeto como `let user2 = user` no existe. Si hacemos un cambio en una propiedad de `user2`, `user` también se vería afectado
y viceversa.

# Declaración
```js
let user = {
  name : 'Pepe',
  age  : 89,
  'estado social': 'soltero',
};
```

# Modificación, agregado, borrado y acceso
```js
// Modificación
user.name = 'Julián';
user['age'] = 91;

// Agregado
user.soltero = false;
user['mascota'] = 'Pato';

// Borrado
delete user.soltero;

// Acceso
alert( 'Bienvenido ' + user.name );
```

# Agregación dinámica
```js
let fruta = prompt('Ingresa una fruta');

// Forma 1
let frutas = {
  [fruta] : 4;
};

// Forma 2
frutas[fruta] = 2;
```

# Construcor
```js
function makeUser(name, age, casado) {
  return {
    name,
    age,
    casado : false,
  };
}

makeUser('Rodolfo', 71);
```

# Operador in
```js
 // Comprobar existencia, 2 formas:
 if (user.name) alert( user.name );
 if (name in user) alert( user.name );
 
 // Bucle for para iterar propiedades
 for prop in user:
    console.log( prop );       // claves
    console.log( user[prop] ); // valor
```

# Clonar un objeto
```js
// Podemos clonar un objeto, de forma que sea único y no comparta dirección de memoria.
let clon = Object.assign({}, user);

// También podemos copiar las propiedades de otros objetos y asignarlas a otra
Object.assign(user, obj1, obj2, ... ) // '...' -> n objetos
```

# This
This toma como referencia los parámetros del objeto padre dentro de las funciones. Pero solo en el primer nivel. Del segundo nivel hacia adelante se recomienda el uso del puntero que siempre tomará como referencia los parámetros del padre.
```js
// Forma tradicional del uso de this
let user = {
  name: 'Pepe',
  lastname: 'Romero',
  saludo(){
    console.log(this.name, this.lastname);
  }
};
user.saludo();

// Uso incorrecto de this
let user = {
  name: 'Pepe',
  lastname: 'Romero',
  saludo(){
    let porConsola = function(){
      console.log(this.name, this.lastname); // this no referencia al objeto raíz
    }
    porConsola();
  }
};
user.saludo();

// Alternativa para referenciar a la raíz mediante la flecha =>
let user = {
  name: 'Pepe',
  lastname: 'Romero',
  saludo(){
    let porConsola = () => {
      console.log(this.name, this.lastname); // this siempre referenciará al objeto raíz
    }
    porConsola();
  }
};
user.saludo();
```
