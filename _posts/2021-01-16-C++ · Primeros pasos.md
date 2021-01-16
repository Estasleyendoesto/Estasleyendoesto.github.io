---
layout: post
title: "C++ · Primeros pasos"
---

Breves apuntes para recordar el funcionamiento de C.

> C++ es básicamente C pero con librerías y con algunas mínimas diferencias

C++ es un lenguaje de programación multiparadigma de bajo nivel ampliamente utilizado en todos los sectores. Por dar un ejemplo: videojuegos, sistemas operativos como Windows o Linux están creados en C++.



## Librerías

Para poder hacer uso de todas las funciones proporcionadas para C es necesario el uso de librerías.

```c++
#include <iostream>		// input y output por consola
#include <stdio.h>		// mejora rendimiento de in y out por consola
#include <math.h>		// expresiones matemáticas y trigonométricas para c++
#include <cstring>		// uso de string con el tipo de dato char
```

>  `#include` importa la librería `<iostream>` (encargada de la entrada y salida de datos).

> Documentación sobre las librerías: http://www.cplusplus.com



## Función principal

Todos los programadas, en cualquier lenguaje de programación, tienen una función principal que es llamada al comienzo del todo. En el caso de C++ es la siguiente:

```c++
int main()
{
    // Instrucciones...
    return 0;
}
```

> la función de tipo entero main() se escribe tal cual y debe ser así por convención. Debe retornar siempre 0 que indica que todo está ok.



## Estructura de un programa en C

```c++
// Directivas del preprocesador
# include<iostream>				// Librerías
const float PI= 3.141592;		// Constantes
int num;						// Variables globales

// Prototipos de función
void imprimir(int numero);

// Función principal
int main()
{
    return 0;
}

// Definición de funciones
void imprimir(int numero)
{
    cout << numero << endl;
}
```



## Using namespace

Los espacios de nombre son utilizados para ahorrarnos tener que especificar a qué librería pertenece el llamado a sus funciones.

```c++
#include <iostream>

using namespace std;

int main()
{
    // Mediante el uso de namespaces
    cout << "Saludos, terrícolas";
    
    // Sin su uso
    std::cout << "Saludos otra vez, terrícolas";
    
    return 0;
}
```

> En la práctica, está prohibido el uso de los namespaces debajo de las cabeceras de nuestro proyecto (justo debajo de `#include`) por lo que no deberíamos usarlo. Está bien visto su uso si es para documentos específicos que abusen en gran medida de las librerías y no para todos los documentos del proyecto.



## Comentarios

```c++
// Comentario a una línea

/*
	Comentario multilínea
*/
```



## Entrada y salida de datos por consola

```c++
#include <iostream>
#include <conio.h>
using namespace std;

int main()
{
    int numero;
    
    // Salida de datos
    cout << "Ingresa un número: ";
    
    // Entrada de datos
    cin >> numero;
    
    // Salida de datos
    cout.precision(2);	// Opcional. Redondea un numero.
    cout << "El número ingresado es: " << numero << endl; // endl hace salto de línea.
    
    getch();	// De conio.h, impide que se cierre la consola hasta pulsar una tecla.
    return 0;
}
```

> Se escribe por consola con **`cout`** y se recibe con **`cin`**. El uso de **`<<`** es para concatenar la salida de datos y **`>>`** para la entrada.



 ## Tipos de datos

```c++
#include <iostream>
using namespace std;

int main()
{
    int entero = 25;		// Número entero positivo o negativo
    float flotante = 2.56;	// Número decimal
    double doble = 2.56456;	// Número decimal de mayor longitud
    char letra = 'a';		// Una letra del código ASCII y entre comillas simples
    char cadena[10];		// Una cadena de texto de diez dígitos
    
    cadena = 'Hola';
    
    return 0;
}
```



## Operaciones aritméticas

```c++
#include <iostream>
using namespace std;

int main()
{
    int numero1, numero2, operacion = 0;
    
    numero1 = 4;
    numero2 = 2;
    
    operacion = numero1 + numero2;	// Suma
    operacion = numero1 - numero2;	// Resta
    operacion = numero1 * numero2;	// Multiplicación
    operacion = numero1 / numero2;	// División
    
    return 0;
}

```



## Control de flujo

Los siguientes operadores lógicos para el control de flujo que devuelven true o false.

```c++
1 == 2		// Igualdad
1 != 2		// Desigualdad
1 > 2		// Mayor
1 < 2		// Menor
1 >= 2		// Mayor o igual
1 <= 2		// Menor o igual
&&			// And
||			// Or
```



### If ... else

```c++
if (5 == 5)
{
    // do stuff..
}
else if (2 == 2)
{
    // do stuff..
}
else
{
    // do else..
}
```



### Switch

```c++
switch (numero)
	{
		case 1:
			cout << "Es el número 1";
			break;
		case 2:
			cout << "Es el número 2";
			break;
		case 3:
			cout << "Es el número 3";
			break;
		default:
			cout << "Es un número desconocido";
	}
```



### While

```c++
int i = 0;
while (i < 10)
{
    cout << i << endl;
    i++;
}
```



### Do ... while

```c++
int i = 0;
do
{
    cout << i << endl;
    i++;
}
while (i < 10);
```



### For

```c++
for (int i = 0; i < 10; i++)
{
    cout << i << endl;
}
```



## Vectores, arrays o arreglos

Es una colección de datos del mismo tipo, de una dimensión y de una longitud predefinida.

```c++
// Se define la longitud del vector para introducir datos más adelante
// Todos sus elementos deben ser del mismo tipo de dato
int 	entero[10];
float 	flotante[5];
double 	doble[7];
char 	letra[21];

// Al introducir los datos en la misma declaración no se define la longitud.
char letras[] = {'a', 'b', 'c', 'd', 'e'};
int numeros[] = {1, 2, 3, 4, 5};

// Se asigna un número entero en la posición 3 del vector
entero[2] = 25;

// Iteración de un vector
for (int i = 0; i < 10; i++)
{
    numeros[i] = i; // Asignación de datos automático
}
```



## Matrices

Una matriz es un vector de dos dimensiones y de una longitud predefinida.

```c++
// Matriz de dos dimensiones
int entero[3][3];

// Asignación directa
int numero[3][3] = { {1, 2, 3}, {4, 5, 6}, {7, 8, 9} };

// Asignación manual
numero[2][1] = 25;

// Interación de una matriz
int n = 1;
for (int fila = 0; fila < 3; fila++)
{
    for (int columna = 0; columna < 3; columna++)
    {
        entero[fila][columna] = n; // Asignación de datos automático
        n++;
    }
}

```



## Punteros

Los punteros se declaran de la misma forma que una variable con la principal característica de estar precedido con ``*`` asterisco. Un puntero no es una variable, es una dirección que apunta a un espacio en la memoria de otra variable. En otras palabras, es como su representación.

Para apuntar a otra variable, el puntero debe ser declarado con el mismo tipo de dato que la variable a apuntar y asignar que es la dirección de memoria de la otra variable con ``&``.

Pero como el puntero tiene almacenado la dirección en memoria, para poder visualizar y modificar el contenido de esta dirección en memoria tenemos que usar asterisco ``*`` que hace referencia al valor.

> **`&`**   obtiene la dirección en memoria de cualquier tipo de dato, objeto, estructura o array/vector.
>
> **`*`**   reserva un espacio en memoria para almacenar una dirección de memoria obtenida con `&`.

```c++
#include <iostream>

using namespace std;

int main()
{
    int numero, *dir_numero; // Creación de un puntero de tipo entero
    numero = 14;
    dir_numero = &numero;	 // Definimos que el puntero apunte a la dirección en memoria de la variable numero
    
    cout << "Dirección en memoria: " << dir_numero << endl;	// El puntero almacena la dirección en memoria
    cout << "Valor: " << *dir_numero << endl;				// Con * accedemos al valor en memoria
    
    // Cambiamos el valor de la variable numero a través del puntero
    *dir_numero += 21;	
    cout << "Numero: " << numero << endl;
    cout << "Puntero: " << *dir_numero << endl;
    
    return 0;
}

```

> Un puntero almacena la dirección en memoria, ejemplo: `0xbfebd5c0`. Mientras que un puntero precedido por el símbolo asterisco `*` muestra el contenido de la dirección en memoria, ejemplo: `25`. Por supuesto, podemos modificar esta variable desde el puntero y cambiar el valor de `25` a `31`.


