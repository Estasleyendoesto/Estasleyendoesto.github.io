---
layout: post
title: "Gestión de escenas en un videojuego"
---

# Gestión de escenas en un videojuego

> Este contenido ha sido extraído de https://www.genbeta.com/desarrollo/gestionando-escenas-en-un-videojuego

Un videojuego generalmente no se compone de una sola pantalla, sino que hay varias como pueden ser un menú introductorio. el mapa de nuestro juego, un menú de objetos, una pantalla de puntuaciones, etc. Estas diferentes pantallas reciben el nombre de **escenas** cada una de ella representa algo especifico de nuestro juego.

Cambiar la escena del juego puede ser algo complicado, recuerda que siempre se debe mantener el bucle de ejecución de los juegos.

![](https://estasleyendoesto.github.io/assets/res/1366_2000.png)

Se suele utilizar un bucle infinito que vaya manteniendo esto, pero surge el problema de que en una escena determinada de nuestro juego los eventos, la lógica y las cosas a dibujar serán unas y en otras escenas puede ser otra. Por ejemplo, en un menú habrá que gestionar como eventos si se acciona algún botón y habrá que dibujar este menú, en otra escena del juego puedes necesitar dibujar otra cosa.



## El objeto director y la escena maestra

Nuestras escenas a pesar de lo diferente que puedan ser entre ellas siempre van a tener las características del bucle de arriba. Es decir, deben de inicializarse, actualizarse, gestionar eventos y dibujarse. Por tanto podríamos definir una clase maestra abstracta que se encargara de hacer esto con la escena que tengamos activa independiente de cual sea.

### El objeto director

En lugar de gestionar en nuestro archivo **main** el bucle del juego lo que vamos a hacer es crear un **clase director** que será la encargada de gestionar nuestro bucle de juego, este bucle recibirá una escena cualquiera y se encargará de ejecutar sus métodos de actualizar, eventos y dibujar.

```python
import pygame

class Director:
    def __init__(self):
        self.screen = pygame.display.set_mode(self.size, pygame.RESIZABLE)
        pygame.display.set_caption("Mi juego")
        self.scene = None
        self.quit = False
        self.clock = pygame.time.Clock()
        
    def loop(self):
        while not self.quit:
            self.clock.tick(60)
            
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    self.quit()
                if event.type == pygame.KEYDOWN:
                    if event.key == pygame.K_ESCAPE:
                        self.quit()
              
            self.scene.on_event()
            self.scene.on_update()
            self.scene.on_draw(self.screen)
            
            pygame.display.flip()
            
	def new_scene(self, scene):
        self.scene = scene

    def quit(self):
        self.quit = True
```

Este objeto debe crearse dentro de nuestra función principal **`main`** en sustitución del bucle del juego. Vamos a explicarlo:

En el constructor creamos la ventana de Pygame, le damos título e iniciamos el reloj. También definimos varias variables, por un lado tenemos **`self.scene = None`** que será la escena que queremos que represente, de momento ninguna. **`self.quit = False`** Es una “bandera” que nos indica si queremos salir.

Luego viene el método loop que es el que contiene el bucle de nuestro juego, tiene como condición para salir del bucle que la variable **`self.quit`** sea verdadera, cuando lo sea saldrá del bucle. para hacer esta variable verdadera solo hay que llamar desde cualquier lado del bucle al **método `quit`** que como vemos cambia la variable a verdadera.

Ya dentro del bucle lo primero es establecer el framerate, en este caso lo tenemos a 60. Luego ya empezamos con el bucle, comprobamos si se ha producido un evento de salida. En nuestro caso aparte de eso comprobamos también como evento de salida si se ha pulsado la tecla escape (esto a gusto del consumidor y del juego). Si se ha producido un evento de salida como vemos llamamos a **`self.quit()`**.

Luego llama a **`self.scene.on_event()`**, pero, ¿**`self.scene`** no valía **`None`**? Exacto así que hacemos un inciso aquí en la clase director para explicar la clase scene.



### La clase Scene

La clase **Scene** representa a una clase abstracta del juego. Es una clase padre que debe ser heredada por todas las escenas de nuestro juego, veamos.

```python
import pygame
from abc import ABC, abstractmethod

class Scene(ABC):
    def __init__(self, director):
        self.director = director

    @abstractmethod
    def on_update(self):
        raise NotImplemented("Falta el método on_update")

    @abstractmethod
    def on_event(self, event):
        raise NotImplemented("Falta el método on_event")

    @abstractmethod
    def on_draw(self, screen):
        raise NotImplemented("Falta el método on_draw")
```

Como vemos es muy sencilla, el constructor solo recibe como parámetro el objeto director. Luego implementa tres métodos. **`on_update`**, **, **`on_event`** y **`on_draw`**. Cada uno se encarga de hacer las tareas de actualizar, gestionar eventos y dibujar respectivamente. Pero como vemos en el cuerpo de cada uno de los métodos lo que hay es un error de que no de ha implementado ese método, esto es porque Scene es una escena padre que debe ser llamada por las escenas de nuestro juego e implementar estos tres métodos para que hagan las acciones específicas de nuestra escena. Vamos allá.



### Creando una escena

Vamos a crear una sencilla escena que no haga nada, simplemente que exista:

```python
import pygame
from director import Scene

class Escena_1(Scene):
    def __init__(self, director):
        super().__init__(director)
        
    def on_draw(self, screen):
        pass
    
    def on_update(self):
        pass
    
    def on_event(self):
        pass
```

Como vemos nuestra escena hereda de **Scene** (puedes ver que en el código pone `scene.Scene`, esto es porque yo la tengo en un archivo aparte llamada scene), como vemos en el **init** lo primero que hacemos es llamar al **init** de Scene y pasarle el objeto director. Luego implementamos y sustituimos los métodos de la clase padre con los de nuestras escena. En esta caso los tres con la sentencia `pass`, que no hace nada.

Veamos como inicializar la escena, volviendo al archivo **main**.

```python
import pygame
import escenarios
from director import Director

def main():
    dir = Director()
    escena1 = Escena_1(dir)
    dir.new_scene(escena1)
    dir.loop()

if __name__ == "__main__":
    pygame.init()
    main()
```



Este es el archivo **main** de nuestro proyecto, como vemos importa tres módulos, **pygame** para que pueda ser inicializado, el módulo **director** que contiene la clase director y el modulo **scene_home** que contiene la escena con la que queremos iniciar nuestro juego.

Luego ya en la función **main** creamos el objeto director con **`dir = director.Director()`**. Esto llama al constructor del objeto director que como vimos arriba crea la ventana, le pone titulo, crea el reloj y define la variable **`self.scene = None`**.

A continuación creamos un objeto scene con nuestra escena: **`scene = scenehome.SceneHome(dir)`**. y llamamos al método **`change_scene`** de la clase director pasándole como parámetro el objeto scene que acabamos de crear, veamos que hace este método.

```python
def change_scene(self, scene):
	self.scene = scene
```



### Continuando con el objeto director

Nos quedaba por explicar lo siguiente del objeto director.

```python
# detecta eventos
elf.scene.on_event()

# actualiza la escena
self.scene.on_update()

# dibuja la pantalla
self.scene.on_draw(self.screen)
pygame.display.flip()
```

Pues lo que hace es llamar a los tres métodos de nuestra escena cargada que se encarga de gestionar las actualizaciones, los eventos y el dibujado. Por último se llama a **`pygame.display.flip()`**  para dibujar la pantalla.

Como vemos ya tenemos la manera de cargar una escena cualquiera desde nuestro objeto director con sus propios métodos de actualización, eventos y dibujado. Ahora para cambiar de scene solo hace falta llamar desde cualquiera parte dentro de nuestra escena activa a **`director.change_scene(scene)`** donde scene es la nueva escena que queremos que pase a tener el control ya que esto modificará a `self.scene` que es la que implementa los métodos.

