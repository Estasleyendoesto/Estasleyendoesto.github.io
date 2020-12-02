---
layout: post
title: "Virtualenv y pip"
---

# Virtualenv y pip

> Este tutorial ha sido extraído de: https://j2logo.com/virtualenv-pip-librerias-python/

Si estás familiarizad@ con Python o estás iniciándote, es posible que en algún tutorial hayas visto que hagan uso de `virtualenv`. **Virtualenv es una herramienta que nos permite tener entornos Python totalmente separados y aislados**, de manera que el intérprete y las librerías de proyectos diferentes no entren en conflicto.



## Instalación de virtualenv

Para instalar virtualenv nos ayudaremos de otra herramienta que viene instalada junto con el intérprete de Python: `pip`. Pip es una utilidad de línea de comandos que nos permite instalar y administrar librerías y paquetes Python. Muchos de estos paquetes y librerías se encuentran alojados en el [Python Package Index](https://pypi.org/) o [PyPI](https://pypi.org/), el repositorio oficial de Python para paquetes de terceros.

El comando para instalar virtualenv con pip es el siguiente:

```
pip install virtualenv
```



## Creando un entorno virtual con virtualenv

Para crear un entorno virtual con virtualenv nos situaremos en el directorio raíz de nuestro proyecto y ejecutaremos el siguiente comando:

```
python -m venv c:\path\to\myenv
```

> `c:\path\to\myenv` como la ruta o bien ser solo el nombre del virtualenv

Esto creará el directorio `env`, el cuál contiene el entorno virtual:

```
/tutorial-virtualenv
|__/myenv
   |__/bin
   |__/include
   |__/lib
```

El directorio `bin` (se llama `Scripts` en Windows) contiene los ejecutables: como el intérprete de Python o pip. Por su parte, los directorios `include` y `lib` contienen las librerías necesarias para correr nuestro código. Las librerías de terceros se instalarán en `env/lib/pythonX.X/site-packages/`.

En mi caso, yo tengo dos versiones de Python instaladas: Python 2.7 (venía instalada con el sistema) y Python 3.6.

Python 2.7 es la versión por defecto y está instalada en `/usr/bin`, mientras que Python 3.6 lo está en `/usr/local/bin`. ¿Cómo indico a virtualenv qué versión de Python usar? Si no indicamos nada, virtualenv tendrá en cuenta la versión por defecto de Python. En el ejemplo, la versión de Python del entorno virtual es la 2.7. Si queremos usar la versión 3.6, debemos indicarle la ruta en la que se encuentra el intérprete de Python a utilizar, por ejemplo:

```
virtualenv -p /usr/local/bin/python3.6 env
```



## Usar el entorno virtual

En el paso anterior creamos nuestro entorno virtual, sin embargo, si instalamos cualquier paquete no lo haremos en dicho entorno. Para ello, primero debemos activarlo ejecutando el siguiente comando:

```
source env/bin/activate
```

> `source` es la ruta absoluta, pero podemos abrir la consola de comandos en la carpeta raíz y omitir `source`

En el caso de Windows ejecutaremos:

```
env\Scripts\activate.bat
```

Sabremos que estamos dentro del entorno virtual porque el prompt del terminal comienza con (myenv)

Cualquier librería que instalemos ahora será dentro del entorno virtual.

Para salir del entorno virtual, lo haremos ejecutando el siguiente comando:

```
deactivate
```



## requirements.txt

Por regla general, los proyectos Python suelen distribuirse con un fichero llamado `requirements.txt`. Este fichero contiene un listado con todas las librerías de las que depende el proyecto, junto con sus números de versión.

Los pasos para migrar un proyecto de una máquina a otra o desde un repositorio de código suelen ser:

- Crear el entorno virtual con virtualenv
- Activar el entorno
- Instalar las dependencias indicadas en el fichero `requirements.txt`

El contenido del fichero `requirements.txt` debe verse así:

```
# Para instalar una versión específica
package==version

# Para instalar una versión igual o superior
package>=version

# Para instalar la versión más reciente
package
```

Por ejemplo, si se quiere instalar la versión 1.7.1 de *Pygame*, se anota lo siguiente:

```txt
Pygame==1.7.1
```

Si se desea instalar una versión mayor que o igual a la 1.7.1, se anota lo siguiente:

```txt
Pygame>=1.7.1
```

Para instalar las librerías listadas en el fichero `requirements.txt`, basta con ejecutar el siguiente comando:

```
pip install -r requirements.txt
```



## Consideraciones a tener en cuenta

Cuando se trabaja con `virtualenv`, debes tener en cuenta las siguientes cosas:

- El entorno virtual hace uso de rutas absolutas. Si copias y pegas para duplicar, te llevas el entorno a otra máquina o cambias el nombre de algún directorio que esté incluido en la ruta de tu proyecto, no funcionará.
- Es una buena práctica añadir tus propias variables de entorno al final del fichero `activate`.
- Tu entorno virtual puede estar ubicado en cualquier parte del sistema de ficheros. Yo suelo tenerlo dentro de la carpeta del proyecto, junto con el código.
- En el ejemplo, el entorno virtual lo he llamado `env` pero puedes darle el nombre que tú quieras. Por convención se suelen usar `env` o `venv`.

Ejemplo de configuración de un proyecto con `virtualenv` y `requirements.txt`:

```
/mi_proyecto
|_/env
|_program.py
|_requirements.txt
|_...py
```



## Guía rápida (cheat sheet) de virtualenv y pip

🎯 Instalar virtualenv:

```
pip install virtualenv
```

🎯 Crear entorno virtual:

```
virtualenv env
```

🎯 Crear entorno virtual especificando el intérprete:

```
virtualenv -p ruta/interprete/python env
```

🎯 Crear entorno virtual heredando las librerías del sistema (no recomendado):

```
virtualenv --system-site-packages env
```

🎯 Activar el entorno virtual en Linux/Mac:

```
source env/bin/activate
```

🎯 Activar el entorno virtual en Windows:

```
env\Scripts\activate.bat
```

🎯 Salir del entorno virtual:

```
deactivate
```

🎯 Instalar un paquete/librería (por ejemplo, flask):

```
pip install flask
```

🎯 Instalar una versión concreta de un paquete/librería:

```
pip install flask==1.0.1
```

🎯 Actualizar la versión de un paquete/librería:

```
pip install flask -U
```

🎯 Desinstalar una librería:

```
pip uninstall flask
```

🎯 Listar todas las librerías:

```
pip list
```

🎯 Listar todos los paquetes/librerías en formato `requirements.txt`:

```
pip freeze
```

🎯 Crear/Actualizar el fichero `requirements.txt`:

```
pip freeze > requirements.txt
```

🎯 Mostrar la información de un paquete/librería:

```
pip show flask
```



