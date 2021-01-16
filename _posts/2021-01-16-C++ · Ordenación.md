---
layout: post
title: "C++ · Ordenación"
---

Métodos de ordenación de elementos de un vector.



### Burbuja

Hace `(n ^ 2) + n` recorridos para ordenar, donde n = longitud del array.

> 0% de eficiencia

```c++
#include <iostream>

using namespace std;

int main()
{
	int numeros[] = {2, 5, 7, 4, 8, 4, 9, 0, 1, 3, 5, 6}; // 12
	int aux = 0;

    // Ordenación por burbuja
    for (int i = 0; i < 12; i++)
    {
        for (int e = 0; e < 12; e++)
        {
            aux = numeros[i];
            numeros[i] = numeros[e];
            numeros[e] = aux;
        }
    }
    
	return 0;
}
```



### Inserción

Hace `(n ^ 2 + n) - x` recorridos para ordenar, donde n = longitud del array, x = recorrido variable.

> Del 50% al 100% de eficiencia (variable)

```c++
#include <iostream>

using namespace std;

int main()
{
    int numeros[] = {2, 5, 7, 4, 8, 4, 9, 0, 1, 3, 5, 6}; // 12
	int pos, aux = 0;
    
    // Ordenación por inserción
    for (int i = 0; i < 12; i++)
	{
		pos = i;
			
		while ( pos >= 1 && numeros[pos] < numeros[pos - 1] )
		{
			aux = numeros[pos];
			numeros[pos] = numeros[pos - 1];
			numeros[pos-1] = aux;
			
			pos--;
		}
	}	
    
    return 0;
}

```



### Selección

Hace `n + (n * 2)` recorridos para ordenar, donde n = longitud del array

> 54% de eficiencia respecto al de burbuja

```c++
#include <iostream>
#include <cstring>

using namespace std;

int main()
{
	int numeros[] = {2, 5, 7, 4, 8, 4, 9, 0, 1, 3, 5, 6}; // 12
	int min, aux = 0;
    
    // Ordenación por selección
	for (int i = 0; i < 12; i++)
	{
		min = i;
		
		for (int e = i + 1; e < 12; e++)
		{
			if (numeros[e] < numeros[min])
			{
				min = e;
			}	
		}
		
		aux = numeros[i];
		numeros[i] = numeros[min];
		numeros[min] = aux;
	}

	return 0;
}
```



### Shell

Divide `e = n / 2` de forma recursiva hasta que `e = 1`, por cada división hace un recorrido de `n - e ` y termina con un recorrido variable por método de inserción.

> 76% de eficiencia respecto al de burbuja

```c++
#include <iostream>
#include <cstring>

using namespace std;

int main()
{
	int numeros[] = {2, 5, 7, 4, 8, 4, 9, 0, 1, 3, 5, 6}; // 12
    
    // Ordenación por Shell
	int lenght = 12;
	int salto = lenght / 2;
	int ini, fin, aux;

	while (salto > 0)
	{
		for (int i = salto; i < lenght; i++)
		{
			ini = i - salto;	
			
			while (ini >= 0)
			{
				fin = ini + salto;
				
				if (numeros[ini] <= numeros[fin])
				{
					ini = -1;
				}
				else
				{
					aux = numeros[ini];
					numeros[ini] = numeros[fin];
					numeros[fin] = aux;
					
					ini -= salto;
				}
			}
		}
		
		salto /= 2;
	}

```



### Quick sort

Divide un vector en dos partes y compara el valor del extremo de cada parte hasta alcanzar el pivote (centro). A cada parte la vuelve a dividir en dos y vuelve a comparar sus valores extremos hasta alcanzar el pivote. Se repite hasta ordenar los ítems.

> Este es el método más eficiente, corto y elegante conocido hasta la fecha.

```c++
#include <iostream>
#include <cstring>

using namespace std;

void quicksort(int array[], int ini, int fin)
{
	int mid = (ini + fin) / 2;
	int pivote = array[mid];
	int i = ini;
	int f = fin;
	int aux;
	
	do
	{
		while (array[i] < pivote) i++;
		while (array[f] > pivote) f--;
		
		if (i <= f)
		{
			aux = array[i];
			array[i] = array[f];
			array[f] = aux;
			
			i++;
			f--;
		}
	}
	while (i <= f);
	
	if (ini < f) quicksort(array, ini, f);
	if (fin > i) quicksort(array, i, fin);
}

int main()
{
	int array[] = {2, 5, 7, 4, 8, 4, 9, 0, 1, 3, 5, 6}; // 12
	
	// Ordenación por Quick sort
	quicksort(array, 0, 12);
	
	
	// Lectura
	for (int i = 0; i < 12; i++)
	{
		cout << array[i] << endl;
	}
	
	return 0;
}
```

