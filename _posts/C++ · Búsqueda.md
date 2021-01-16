# C++ · Búsqueda

Métodos de búsqueda de un vector



### Búsqueda secuencial

Recorre el arreglo de principio a fin buscando una coincidencia.

```c++
#include <iostream>

using namespace std;

int main()
{
	int vector[] = {1, 6, 4, 2, 4, 6, 4, 3, 6, 6}; // 10
	int dato = 3;
	int pos;
	
	while (vector[pos] != busca && pos < 10) pos++;
	
	if (pos)
	{
		cout << "Encontrado en la posicion " << pos;
	}
	else
	{
		cout << "No se ha encontrado dentro del arreglo.";
	}
	
	return 0;
}
```



### Búsqueda binaria

Búsqueda más eficiente y rápida que la búsqueda secuencial. La lista tiene que estar ordenada de forma ascendente.

```c++
#include <iostream>

using namespace std;

int main()
{
	int vector[] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}; // 10
	int dato = 3;
	
	int ini, fin, centro;
	bool control = false;
	
	ini = 0;
	fin = 10;
	
	while (ini <= fin)
	{
		centro = (ini + fin) / 2;
		
		if (vector[centro] == dato)
		{
			control = true;
			break;
		}
		if (vector[centro] > dato)
		{
			fin = centro;
			centro = (ini + fin) / 2;
		}
		if (vector[centro] < dato)
		{
			ini = centro;
			centro = (ini + fin) / 2;
		}
	}
	
	if (control)
	{
		cout << "Encontrado en la posicion " << centro;
	}
	else
	{
		cout << "No se ha encontrado dentro del arreglo.";
	}
	
	return 0;
}
```

