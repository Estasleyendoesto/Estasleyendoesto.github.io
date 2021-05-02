---
layout: post
title: "Matemáticas para programadores II"

---

## Introducción

Continuando el primer artículo, en este repasaremos la aritmética.



## Aritmética

Un repaso general, no mencionando las sumas, restas, multiplicaciones y divisiones tradicionales que todos deberíamos tener dominado.

### Calculando fracciones

Una fracción `2⁄5` es exactamente igual a decir `2 ÷ 5` y en un lenguaje de programación `2 / 5`. Los dos puntos utilizados en el tan conocido símbolo **÷** representan al numerador entre el divisor de la fracción. 

### Multiplicando dos fracciones

Para multiplicar dos fracciones simplemente multiplicas los numeradores por un lado y luego los denominadores por otro lado. Cuando multiplicas una fracción con un número entero, recuerda que al número entero debes añadirle el denominador 1.

![multiplierfracc](/assets/res/multiplierfracc.png)

### Dividir fracciones

Para dividir `2⁄5` entre `3⁄7` simplemente invierte `3⁄7` a `7⁄3` y multiplica normalmente.

![fraccfdivir](/assets/res/fraccfdivir.png)

### Adición y sustracción de fracciones

También conocido como sumas y restas, son un poco más complicadas que los anteriores. Si las fracciones tienen el mismo denominador, tan solo debes operar normalmente ignorando los denominadores.

<img src="/assets/res/ari06.png" alt="ari06" style="zoom: 150%;" />

Pero qué ocurre si queremos operar con fracciones que tengan un denominador distinto. Afortunadamente, el método más rápido es hacer una multiplicación en cruz. Tenga en cuenta que solo puede hacerse entre dos fracciones, si hay tres primero debemos operar con las dos primeras y al resultado con la tercera y así sucesivamente.

![cruzmulti](/assets/res/cruzmulti.png)

Sea suma o resta solo debemos cambiarle de signo. Para conseguir que tengan el mismo denominador, las multiplicamos. Para el primer numerador extraemos el numerador de la primera fracción y la multiplicamos por el denominador de la segunda. Para el segundo numerador extraemos el numerador de la segunda fracción y la multiplicamos por el denominador de la primera.

### Factores y factorización

Un factor es reducir una fracción. Un factor o división de un entero es un entero que puede ser exactamente dividido por otro entero. Como 1, 2, 3 son factores de 6.

Por ejemplo si queremos factorizar o reducir la fracción `6⁄8` podemos ver que ambos pueden ser divididos por 2 y es llamado el máximo factor común, o comúnmente conocido como el máximo común divisor o GCD. Para reducir una fracción se divide el numerador y el denominador por el GCD.

En estudios tempranos de la aritmética, se hallaría el GCD de dos números encontrando el factor primo que tengan en común estos dos números. Los factores primos pertenecen a los números primos y los números primos son números que solo pueden ser divisibles entre ellos mismos o entre 1. El número 1 se lo considera primo, pero por un caso especial se lo excluye de la lista, por lo que partiríamos del 2, 3, 5, 7, 11...

#### Algoritmo Euclidiano para hallar el GCD

Un algoritmo extremadamente rápido, corto y considerado hermoso entre la comunidad de los programadores es el algoritmo Euclidiano para hallar el GCD. Seudocódigo:

```pseudocode
function gcd(n, m)
	set r to the remainder of n/m
	if r = 0 then return m
	else return gcd(m, r)
end function
```



### El módulo Aritmético

El módulo es el residuo de una división y es ampliamente utilizado en la programación. Por ejemplo, el algoritmo Euclidiano necesita asignar a la variable `r` el residuo de `n / m`. Por suerte las librerías nos dan la función `mod()` para hallar el módulo, aunque lenguajes modernos como Python el operador `%` también permite hallar el módulo.



### Proporciones, ratios y porcentajes

Volviendo a las fracciones, una de las más poderosas interpretaciones de una fracción es el ratio entre el numerador y el denominador. A veces es como un porcentaje. Continuaremos estos dos conceptos en detalle.

#### Mapeo entre rangos y valores

"Ratio" o proporción se oye mucho mejor que la misma cosa como "fracción", pero son usadas en diferentes circunstancias, particularmente cuando se relacionan dos objetos similares (precisos). Los ratios son usualmente escritos usando los dos puntos. 

El ratio 4:3, por ejemplo, es el equivalente a la fracción 4⁄3. Dos objetos están en el tamaño del ratio 4:3 si uno es 4⁄3 veces el tamaño de el otro.

Frecuentemente, las proporciones son usados para describir como se divide algo. Podemos optar por dividir un pastel en una proporción 1:2 haciendo que una pieza sea dos veces más grande que la otra, de tal forma que:

![factpast](/assets/res/factpast.png)

En otras palabras, puedes dividir el pastel en dos piezas. Uno a 1⁄3 del tamaño original, otro a 2⁄3 del tamaño original.

