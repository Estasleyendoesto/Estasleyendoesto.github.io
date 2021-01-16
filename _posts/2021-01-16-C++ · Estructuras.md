# C++ · Estructuras

En c++ se pueden almacenar colecciones de datos de distintos tipos de dato, a diferencia de los arreglos.

> Una enseñanza más completa [si sigues este enlace](https://www.geeksforgeeks.org/structures-in-cpp/)

```c++
#include <iostream>
#include <cstring>

using namespace std;

struct PERSONA
{
	char nombre[20];
	int edad;
};

struct CASA
{
	int codigo;
	struct PERSONA propietario;		// Anidación
	struct PERSONA residentes[2];	// Anidación múltiple
};


int main()
{
	// C
	struct PERSONA p1 = {"Benito", 31};	 
	
	// C++
	PERSONA p2;		
	strcpy(p2.nombre, "Fidel");
	p2.edad = 33;
	
	cout << p2.nombre << endl;
	cout << p2.edad << endl << endl;
	
	// Anidación
	struct CASA c1;
	c1.codigo = 123;
	c1.propietario = p1;
	
	cout << c1.codigo << endl;
	cout << c1.propietario.nombre << endl << endl;
	
	// Anidación múltiple
	c1.residentes[0] = p1;
	c1.residentes[1] = p2;
	cout << c1.residentes[1].nombre << endl << endl;
	
	// Array de estructuras
	struct PERSONA personas[2];
	personas[0] = p1;
	personas[1] = p2;
	for (int i=0; i<2; i++)
	{
		cout << personas[i].nombre << endl;
	}
	
	return 0;
}
```

