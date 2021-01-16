# C++ · Cadenas de texto

Existen dos formas para trabajar con cadenas de texto:

- Mediante el uso de la clase string, usa UTF8
- Usando arrays del tipo de dato char, usa ASCII



## Mediante el uso de arrays del tipo de dato char

```c++
#include <iostream>
#include <cstring> 	// Librería para strings usando char
#include <stdlib.h> // Para usar atoi() y atof()

int main()
{
    // Ambas declaraciones son lo mismo
    char texto1[] = "Soy un texto";
    char texto2[] = { 'S', 'o', 'y', ' ', 'u', 'n', ' ', 't', 'e', 'x', 't', 'o' };

    cout << texto1 << " - " << texto2 << endl;
    
    
    // Lectura por consola
    char input[20];
    cin.getline(input, 20, '\n');	// Variable, longitud, detener tras enter
    cout << input << endl;
    
    
    // Algunas funciones de la librería cstring
    char s1[] = "Texto 1";
    char s2[] = "Texto 2";
    
    strcpy(s1, s2)				// Copia el contenido de s2 dentro de s1 (reemplaza)					void
    strcat(s1, s2)				// Concatena s2 dentro de s1											void
    int l = strlen(s1)			// Devuelve longitud de la cadena										int
    int c = strcmp(s1, s2)		// Compara igualdad, develve 0 si son iguales o 1 y -1 si no lo son.	int
    strrev(s1)					// Invierte una cadena													void
    strupr(s1)					// Convierte una cadena a mayúsculas									void
    strlwr(s1)					// Convierte una cadena a minúsculas									void
    int ent = atoi("123")		// Convierte una cadena a número entero									int
    float flo = atof("12.35")	// Convierte una cadena a número flotante								float
       
	return 0;
}
```



## Mediante la clase string

...
