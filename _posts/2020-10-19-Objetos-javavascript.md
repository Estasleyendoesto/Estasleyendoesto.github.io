---
layout: post
title: "Objetos en Javascript"
---

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
