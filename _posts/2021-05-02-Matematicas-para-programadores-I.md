---
layout: post
title: "Matemáticas para programadores I"
---

## Introducción
El objetivo de esta serie de artículos es la de dotar de los conocimientos necesarios para subir de nivel en las habilidades de uno en las simulaciones.


## Conocimientos esenciales en las matemáticas
Estos son los conocimientos básicos esenciales que necesitas conocer:
- Números
- Aritmética
- Álgebra
- Geometría y Trigonometría
- Vectores
- Cálculo




## Números
Las matemáticas dividen el mundo de los números en subconjuntos. 

### Enteros, racionales e irracionales
Los números reconocidos como los números para contar o números naturales son representados con el símbolo *N*... `N = {1,2,3,4,5,6,...}` en adición con el número 0 que también cuenta (aunque el 0 representa el vacío o inexistencia).

Al conjunto de números naturales positivos y negativos se los denomina con el símbolo *Z* y se los conoce como los números enteros.

Al conjunto de fracciones como 5⁄4 simbolizados con *Q* se los conoce como los números racionales que incluye todas las fracciones positivas y negativas, además de los números enteros porque son vistos como una forma especial de fracción con el denominador de 1, `3 = 3⁄1`. 

### Irracionales y números reales
Los números irracionales son números que no pueden ser representados por el cociente de dos enteros. Hace mucho tiempo se pensaba que estos números no existían, pero Pitágoras hizo prueba de uno de estos números con la raíz cuadrada de 2 que es irracional. En estos días, estos números conocidos han aumentado. Los matemáticos son más consientes que los irracionales son más fundamentales que los racionales.

Los números irracionales y racionales en conjunto forman los números reales que son representados con el símbolo *R*. En adición, también hay otro tipo de números como los números complejos. Estos números incluyen un múltiplo del número imaginario i que representa la raíz cuadrada de -1. Estos números no son necesarios a no ser que veamos los cuaterniones.

> La raíz cuadrada de un número n en las matemáticas son representadas mediante `√n`. En un lenguaje de programación es usando con una función `sqrt(n)` previamente importando la librería `math`.

### Decimales, binarios y hexadecimales
Los números decimales o conocidos en la programación como base 10 son los números que nosotros conocemos normalmente. Es base 10 porque los dedos en nuestras manos cuentan 10 y porque 10 es múltiplo de 2 y 5. Así que es fácilmente determinar cuando un número escrito es una notación decimal es divisible entre estos dos números.

Pero si consideramos el uso de otra base cualquiera podríamos tener problemas aunque para el ordenador no lo fuera.

Base 2 o binario es la representación para los switches de los ordenadores y se lo representa con dos símbolos a menudo conocidos como 0 y 1.

Pero ante una gran cantidad de información que un ordenador debe procesar la longitud de estos números sería inmensa, para acortarlo el ordenador usa la base 16 o conocido como hexadecimal por los 16 símbolos que hace uso de los números del 0 al 9 y las letras del abecedario de la A a la F.




## Cómo los ordenadores representan los números
Los números binarios pueden ser convenientemente representados mediante 1 y 0 o Encendido y Apagado. Un ideal sistema para las computadoras que solo piensan en números y esos números son representados mediante un conjunto de interruptores. Cada interruptor representa un bit de información y cada bit puede estar entre encendido o apagado. 

Con ocho bits puedes representar números entre el 0 al 255.
Con 32 bits puedes representar cualquier número hasta el 4294967295
Con 64 bits puedes representar cualquier número hasta el 18,446,744,073,709,551,615. Este es también conocido como trabajo cuádruple.

Un sistema de desarrollo nativo de una computadora está diseñada para realizar cálculos muy rápido con cualquier número usando base 2, y esto es relativo al número de bits del procesador. Un ordenador de 64-bits puede ofrecer mayores cálculos que uno de 32-bits. No todos los bits son usados. Un bit también representa si el número es positivo o negativo.

Como resultado, un ordenador de 32-bits procesa entre −2147483647 a 2147483647 en lugar de un sólo rango de números positivos que sería hasta 4294967295.



### Representando los números enteros

Los números enteros en un lenguaje de programación son representados con los decimales...



### Representando los números racionales e irracionales

Los números racionales e irracionales son representados mediante una división. Así que realmente nos quedaríamos con su parte decimal al dividir el numerador entre el denominador.



## Funciones conocidas

Todos los lenguajes de programación incluyen su librería `math` que integra operaciones matemáticas más complejas.

### Valores absolutos

Representado con la función `abs()` retorna el valor absoluto de un número que **siempre será positivo**, puede ser un número flotante o un entero. El pseudocódigo sería el siguiente.

```pseudocode
function abs(n)
	if n>=0 then return n
	otherwise return -n
end function
```

### Flotantes a enteros

Comúnmente usados para convertir números flotantes a enteros, aunque tiene otros propósitos como los siguientes:

- Para un número n, la función `floor()` redondea el número decimal al entero más alto
- Para un número n, la función `ceil()` redondea el número decimal al entero más bajo
- Para un número m, la función `round()` redondea el número decimal al entero más alto o bajo si es inferior o superior a 0.5



