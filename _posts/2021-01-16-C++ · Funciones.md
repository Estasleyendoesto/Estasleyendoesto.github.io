---
layout: post
title: "C++ · Funciones"
---

Quién no sabe lo que es una función... El secreto del código limpio, legible, reutilizable y eficiente.

> Una función debe ser de algún tipo de dato y retornar dicho tipo de dato, un **`void`** es una excepción y no retorna nada.
>
> Tipos de dato como: `int`, `float`, `string`, `char`, `bool`, `void ` y unos cuantos más...

```c++
#include <iostream>

using namespace std;

// Función vacía que no retorna nada
void sinretorno()
{
    cout << "Soy una variable void" << endl;
}

// Función principal
int main()
{
    sinretorno();
    return 0;
}
```



### Prototipo de función

Como el compilador trabaja sólo con la información contenida en un único fichero, a menudo es preciso “informar” al compilador de que en otro fichero existe una función. Esto se consigue insertando, en lugar de la definición de la función (que ya está presente en otro fichero), su prototipo. Toda función que se invoca debe ir precedida o de su definición o de su prototipo.

```c++
// Prototipo de función
int sumar(int, int);

// Función principal
int main()
{
    int i, j;

    i = 10;
    j = 20;
    
    // Invocación de la función
    i += sumar(i, j);
    
    return 0;
}

// Definición de la función
int sumar(int a, int b) 
{
    return (a + b);
}
```



### Plantillas de función

Esenciales cuando queremos trabajar con más de un tipo de dato.

> Puedes profundizar mucho [siguiendo este enlace](https://codingornot.com/cc-plantillas-templates-en-c) y [este otro enlace](https://www.geeksforgeeks.org/templates-cpp/)

```c++
#include <iostream>

// Prototipo de función
template <typename TIPODATO>
void mostrarAbs(TIPODATO numero);

int main()
{
    int numero = -5;
    mostrarAbs(numero);
    
    // En caso de retornar un valor, aunque el compilador aplica el tipo de dato, podemos hacerlo manualmente con <tipo_dato>
    // mostrarAbs<int>(numero);
    
    return 0;
}

template <typename TIPODATO>
void mostrarAbs(TIPODATO numero)
{
    if (numero < 0) numero *= -1;
    
    cout << "Valor absoluto: " << numero << endl;
}
```



### Paso de parámetros por referencia

> Puedes profundizar mucho [siguiendo este enlace](http://conclase.net/c/curso/cap15)

Lo tradicional siempre has ido pasarle parámetros a una función para poder trabajar con estas. Pero lo que estamos pasando son parámetros por valor, es decir que estamos trabajando con una copia exacta. En este caso, vamos a pasarle la dirección en memoria para modificar estas variables directamente en lugar de trabajar con su copia.

```c++
#include <iostream>

using namespace std;

int doblarvalor(int &num);

int main()
{
    int numero = 5;
    
    cout << "Número: " << doblarvalor(numero) << endl;
    
    // Segunda forma especificando el tipo de dato de la función
    cout << "Número: " << doblarvalor<int>(numero) << endl;
    
    return 0;
}

int doblarvalor(int &num)
{
    &num *= 2;
}
```

