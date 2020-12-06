---
layout: post
title: "Aritmética"
---

Todo buen programador competente debe conocer las reglas de la aritmética. Después de todo, ¿cómo podría usar lo básico de la librería math?



- [Números naturales y negativos](#Números_naturales_y_negativos)
- [Sumar, restar números enteros](#Sumar_y_restar_números_enteros)
- [Multiplicar y dividir números enteros](#Multiplicar_y_dividir_números_enteros)
- [Valor absoluto](#Valor_absoluto)
- [Fracciones](#Fracciones)
- [Decimales](#Decimales)
- [Reescribir decimales como fracciones y viceversa](#Reescribir_decimales_como_fracciones_y_viceversa)



## Números naturales y negativos

En matemáticas, los números naturales son los que utilizamos en la vida cotidiana para contar u ordenar y pertenecen al conjunto de **números enteros positivos**.

El conjunto de los números naturales se representa por **ℕ** y está formado por: **ℕ** =  {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, ...}

Los números naturales no tienen decimal, unidad imaginaria, o bien no son fracciones.

Si les añadimos un signo *menos* «−» delante, obtenemos los números enteros negativos

Un **número entero negativo** es un número natural como 1, 2, 3, etc. precedido de un signo *menos* «**−**». Por ejemplo −1, −2, −3, etcétera. Se leen "menos 1", "menos 2", "menos 3",...

Puesto que los números naturales se utilizan para contar elementos, el **cero** puede considerarse el número que corresponde a la ausencia de los mismos



![Los números naturales en una recta](https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Integers-line.svg/706px-Integers-line.svg.png)

> En la programación, el cero puede ser un valor nulo `null`, un booleano falso `False` o bien una posición en un índice [0]



#### Demostración en C

```c++
#include <iostream>

using namespace std;

int main()
{
    // Valores positivos, negativos y nulos
    int positivo = 5;
	int negativo = -2;
	int nulo = 0;
    cout << positivo << endl;
	cout << negativo << endl;
	cout << nulo << endl;
    
    // Booleano en false usando 0
    bool booleano = 0;
    cout << booleanos << endl;
    
    // Índice de un arreglo, array o vector (posición inicial)
    int array[] = {1, 2 ,3 ,4};
    cout << array[0] << endl;
    
   	return 0;
} 
```

**Output:**

```
5
-2
0

0

1
```

> Todos los ejemplos mostrados en C son válidos para cualquier lenguaje de alto nivel





## Sumar y restar números enteros

Si un número **no tiene signo** normalmente significa que es un número **positivo**.

> **5** es en realidad **+5**



Todos sabemos sumar y restar por lo que omitiremos esa obviedad. En su lugar, veremos cómo operar el signo negativo, sumaremos y restaremos signos opuestos.



**Sumar números negativos**, el resultado es una suma normal pero de negativos.

> `-5 + -2 = -7` realmente quiere decir "negativo 5 más negativo 2 es igual a negativo 7"
>
> *Podrías escribirlo así:* **`(-5) + (-2) = (-7)`**



**Restar números negativos** es lo inverso a la suma.

> `-5 - -2 = -3` realmente quiere decir "negativo 5 menos megativo 2 es igual a negativo 3"
>
> *Podrías escribirlo así:* **`(-5) - (-2) = (-3)`**



**Sumar un número positivo con un número negativo o viceversa equivale a una resta**.

> `5 + -2 = 3` y podría escribirse así **`(+5) + (-2) = (+3)`**
>
> `-5 + 2 = -3` y podría escribirse así **`(-5) + (+2) = (-3)`**



**Restar un número positivo con un número negativo o viceversa equivale a una suma**.

> `5 - -2 = 7` y podría escribirse así **`(+5) - (-2) = 7`**
>
> `-5 - 2 = -7` y podría escribirse así **`(-5) - (+2) = -7`**





## Multiplicar y dividir números enteros

Cuando se multiplican dos números positivos se obtiene un positivo

> `3 × 2 = 6`



Cuando se multiplica un positivo y un negativo y viceversa se obtiene un negativo

> `(−3) × 2 = −6`
>
> `3 × (−2) = −6`



Cuanto se multiplican dos números negativos se obtiene un positivo

> `(−3) × (−2) = 6`



**Y para las divisiones es exactamente igual!**

> `3 / 2 = 1.5`
>
> `3 / -2 = -1.5`
>
> `-3 / 2 = -1.5`
>
> `-3 / -2 = 1.5`





## Valor absoluto

El valor absoluto de un número entero coincide con su valor numérico sin tener en cuenta el signo. Se representa con unas barras verticales alrededor del número, así: `|x|`

Por ejemplo,`|2|` representa el valor absoluto de 2.



### cómo calcular el valor absoluto de un número

- Cuando es **positivo** da como resultado el mismo número. Por ejemplo, `|5| = 5`
- Cuando es **negativo** da como resultado el número opuesto. Por ejemplo, `|-3| = 3`
- Cuando es **cero**, `|0| = 0`

Como puedes observar, toma siempre un valor mayor o igual que cero.



Además, representa la **distancia del número al 0**. Esto es muy fácil de observar en la recta numérica:


<img src="https://www.smartick.es/blog/wp-content/uploads/ValorAbsoluto_9.png" style="zoom:80%;" />




## Fracciones

En [matemáticas](https://es.wikipedia.org/wiki/Matemáticas), una **fracción** es la expresión de una cantidad [dividida](https://es.wikipedia.org/wiki/División_(matemáticas)) entre otra cantidad; es decir que representa un cociente no efectuado de números. Por razones históricas también se les llama *fracción común*, *fracción mixta* o *fracción decimal*. 

![Fracciones](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4f/PieChartFraction_threeFourths_oneFourth-colored_differently.svg/220px-PieChartFraction_threeFourths_oneFourth-colored_differently.svg.png)

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7ffd1bec9bda32c3e4d2cf1dd06d55aee63ee9b)



### Suma y resta de fracciones con el mismo denominador

Se suman o se restan los numeradores y se mantiene el denominador.


<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-dc831d4c013187206230bf8143c67076_l3.png" alt="" />
</p>


<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-8c2242780c2a5a0c89f987b39005b344_l3.png" alt="" />
</p>



### Suma y resta de fracciones con distinto denominador

Esta sería la forma tradicional de operar con fracciones de distinto denominador.


<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-fa34943bf99aea5694fc785018347ca2_l3.png" alt="" />
</p>


<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-aa1dbc22e0bb1871aa6e01e2bcab0988_l3.png" alt="" />
</p>



Es bastante intuitivo, pero si queremos operar de forma a lápiz y papel podemos hacerlo mediante:

- El mínimo común múltiplo de los denominadores

- Fracciones equivalentes



#### Cálculo del mínimo común múltiplo (m.c.m)

Buscamos el mcm de dos o más números, en nuestro caso los denominadores 180 y 324. Entonces a cada denominador lo dividimos entre algún [número primo](https://es.wikipedia.org/wiki/Número_primo#:~:text=En%20matemáticas%2C%20un%20número%20primo,por%20lo%20tanto%2C%20pueden%20factorizarse.) hasta que el residuo sea 1.

<p align="center">
<img src="https://cuadernos.rubio.net/media/magpleasure/mpblog/upload/e/a/ea61a4ce0fd7fb36b5c2631028c3e38c.png" style="zoom: 50%;" alt="" />
</p>




Agrupamos los números primos repetidos en exponen y obtenemos que:
<p align="center">
<img src="https://estasleyendoesto.github.io/assets/res/ari01.png" alt="" />
</p>

<p align="center">
<img src="https://estasleyendoesto.github.io/assets/res/ari02.png" alt="" />
</p>



Nos quedamos con los máximos exponentes e ignoramos el resto aunque se repitan y luego los multiplicamos, en este caso:
<p align="center">
<img src="https://estasleyendoesto.github.io/assets/res/ari03.png" alt="" />
</p>
Entonces el **m.c.m** de 180 y 324 es 1620



#### Hallar una fracción equivalente

Tenemos la fracción:

<p align="center">
<img src="https://cuadernos.rubio.net/media/magpleasure/mpblog/upload/e/a/ea61a4ce0fd7fb36b5c2631028c3e38c.png" alt="" />
</p>

y queremos conseguir que su denominador sea el número 6, es decir:

<p align="center">
<img src="https://www.smartick.es/blog/wp-content/uploads/CodeCogsEqn-6.png" alt="" />
</p>

Tienes que pensar por qué número se ha multiplicado el 3 (el denominador) para obtener el número 6… ¡Eso es! Se ha multiplicado por 2.

Por tanto, el numerador también habrá que multiplicarlos por 2 .

<p align="center">
<img src="https://www.smartick.es/blog/wp-content/uploads/CodeCogsEqn-6-1.png" style="zoom:80%;" alt="" />
</p>

si multiplicamos el número 2 por 2 obtenemos 4.

<p align="center">
<img src="https://www.smartick.es/blog/wp-content/uploads/CodeCogsEqn-7.png" style="zoom:80%;" alt="" />
</p>

Acabamos de hallar la fracción equivalente.



#### Sumar y restar fracciones con distinto denominador hallando las fracciones equivalentes

La técnica consiste en multiplicar los denominadores por un número que los convierta en un mismo denominador, y a los numeradores multiplicarlos por ese mismo número, por ejemplo:
<p align="center">
<img src="https://estasleyendoesto.github.io/assets/res/ari04.png" alt="" />
</p>
Qué número en común podrían tener 10 y 8. En este caso sería 40, porque 40 es divisible entre 10 y 8. Entonces, 10 por 4 es 40 y también debemos multiplicar por 4 al numerador, es decir 7 por 4. Con el denominador 8 si lo multiplicamos por 5 da 40, repetimos el proceso con el numerador.
<p align="center">
<img src="https://estasleyendoesto.github.io/assets/res/ari05.png" alt="" />
</p>


Ahora que tenemos los denominadores igualados podemos restar normalmente y si es posible despejar la fracción.
<p align="center">
<img src="https://estasleyendoesto.github.io/assets/res/ari06.png" alt="" />
</p>


> Mira el [video de la explicación](https://youtu.be/BuGyx2VrGRE)



### Multiplicación y división de fracciones con distinto denominador

Para multiplicar dos fracciones, basta multiplicar los numeradores por una parte y los denominadores por otra. Como ejemplo,

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/de1400726b954005ce94c4f6d0cfea87b471d8cf)



Podemos despejar una fracción antes de realizar la operación. Este atajo se conoce como "cancelación" y consiste en dividir de forma cruzada mediante un factor común. Ejemplo,


<p align="center">
<img src="https://estasleyendoesto.github.io/assets/res/ari07.png" alt="" />
</p>


El factor común de 21 y 7 es 7, por lo que podemos despejar y el factor común de 18 y 2 es 2 así que también podemos despejar.



En el caso de dividir fracciones, saltándome el porqué se hace así, el método consiste con que la división de dos fracciones es igual a la multiplicación de la primera fracción por el inverso de la segunda

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/a5c07b36ebe908618efda3a45a927ad643cdfed3)



Ejemplo para quien no entendió la imagen:
<p align="center">
<img src="https://estasleyendoesto.github.io/assets/res/ari08.png" alt="" />
</p>




## Decimales

Los **números decimales** se utilizan para representar números más pequeños que la unidad. Se escriben a la derecha de las Unidades separados por una coma. Es decir:

**Centenas,  Decenas,  Unidades , Décimas,  Centésimas,  Milésimas**

Las operaciones matemáticas con decimales es exactamente igual que con números enteros, salvo la diferencia del punto. Lejos de eso, no hay ninguna complejidad.

> Sigue [este enlace](https://es.khanacademy.org/math/eb-6-primaria-nme/x137d84de64ca8f83:operaciones-con-decimales) y aprenderás a operar con decimales!



### Redondeo de decimales

Para redondear números decimales tenemos que fijarnos en la unidad decimal posterior a la que queremos redondear.

Si la unidad decimal es mayor o igual que ![5](https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-b35a08a3a770db22b654b89e2ebf58e1_l3.png), aumentamos en una unidad la unidad decimal anterior; en caso contrario, la dejamos como está.

<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-a936d14a2d8155c3f94e51573473fd74_l3.png" alt="" />
</p>

<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-c799ec5a5451174da864eacc1eef5866_l3.png" alt="" />
</p>

<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-ddf514a83f14c34837a3ab7c67a8174c_l3.png" alt="" />
</p>

<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-b17b31bbb2aec044c69115412cf89953_l3.png" alt="" />
</p>


### Truncar decimales

Para truncar un número decimal hasta un orden determinado se colocan las cifras anteriores a ese orden inclusive, eliminando las demás.

<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-4c3d2540f959f4c95f7b8d43e2f85590_l3.png" alt="" />
</p>

<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-4853c86de3c81e5ef88de38e5703dee8_l3.png" alt="" />
</p>

<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-6c737b5aec7d7392157322cc03bd62ac_l3.png" alt="" />
</p>

<p align="center">
<img src="https://www.superprof.es/apuntes/wp-content/ql-cache/quicklatex.com-f247c0dd885a74dd5f229b7d822a46d7_l3.png" alt="" />
</p>





## Reescribir decimales como fracciones y viceversa

Imagina que tienes que realizar la siguiente suma de números decimales y fracciones:

![](https://www.smartick.es/blog/wp-content/uploads/9a.png)

No es fácil sumar una fracción con un número decimal, ¿verdad? Es mucho más fácil sumar fracciones con fracciones o sumar números decimales con números decimales. Por tanto tenemos dos posibilidades:

- Pasar el número decimal a fracción
- Pasar una fracción a número decimal



### Pasar un número decimal a fracción

Ahora, tenemos el número

![](https://www.smartick.es/blog/wp-content/uploads/2-22.png)

¿Cómo podemos pasarlo a número decimal? Vamos a seguir la misma estrategia, pero primero tenemos que pensar qué denominador tiene… ¿qué número pueden llevar todos los números como denominador sin que varíen?… ¡Eso es! El número 1

![](https://www.smartick.es/blog/wp-content/uploads/3-10.png)

Ahora tenemos que pensar qué número ponemos en el denominador de la fracción equivalente… El truco es usar el 1 seguido de ceros. Así que lo primero que vamos a probar es con un cero, el 10

![](https://www.smartick.es/blog/wp-content/uploads/4-13.png)

Como para pasar del 1 al 10 (el denominador) hay que multiplicar por 10, multiplicamos también 0,25 (el numerador) por 10

![](https://www.smartick.es/blog/wp-content/uploads/5-9.png)

Y nos queda…

![](https://www.smartick.es/blog/wp-content/uploads/6-8.png)

No hemos quitado todos los decimales aún, ¿verdad? ¡Pues seguimos añadiendo ceros!

![](https://www.smartick.es/blog/wp-content/uploads/7-8.png)

Si multiplicamos por 100 nos queda

![](https://www.smartick.es/blog/wp-content/uploads/CodeCogsEqn-1-1.gif)

Por último, recuerda que las fracciones se pueden simplificar. Si simplificamos esta fracción nos queda

![](https://www.smartick.es/blog/wp-content/uploads/9-4.png)

Entonces,

![](https://www.smartick.es/blog/wp-content/uploads/9-4.png)

Así que, **resumiendo los pasos**, cuando queramos pasar un número decimal a fracción tenemos que:

- Poner el número decimal en una fracción encima de un 1. Es decir, el número decimal es el numerador, el 1 el denominador
- Buscar una fracción equivalente. Esa fracción llevará en el denominador un 1, y tantos ceros como decimales tenga nuestro número
- Multiplicar el número de arriba por ese número
- Simplificar la fracción



### Pasar una fracción a número decimal

La técnica es tan sencilla como dividir el numerador entre el denominador. Así es, una simple división de dos números enteros.

![](https://www.smartick.es/blog/wp-content/uploads/2-23.png)

