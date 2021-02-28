# Funciones

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ferorti/escuela2021/blob/main/clases/clase_04_funciones.ipynb)

## Secciones
- ¿Que son las funciones?
- ¿Como definir funciones propias?
- Importar módulos y funciones 


## ¿Qué son las funciones?

Anterioremente, usamos algunas funciones como __len()__, que permite calcular el tamaño de un elemento, o __type()__, que devuelve el tipo de cierto dato.

Podemos pensar a las funciones como porciones que código que:

- Tienen un funcionalidad muy específica.
- Son potencialmente usables en muchos contextos diferentes.
- Evita tener que escribir el mismo código una y otra vez.
- Ayudan a simplificar la estructura del código.



Veamos un ejemplo con la función __len()__


```python
texto = "En un lugar de la Mancha, de cuyo nombre no quiero acordarme, ..."
largo = len(texto)
# 'texto' es un argumento de la función len(). 
# Las funciones pueden tener cero, uno, o más argumentos.
# El valor de retorno de la función len() es asignado a la variable largo.
# Todas las funciones en python devuelven uno o más valores de retorno.
```


```python
print_result = print("hola")
print("El resultado de print(hola) es ", print_result)
```

    hola
    El resultado de print(hola) es  None
    

Las funciones pueden devolver el valor __None__.

La función __pow()__, que sirve para calcular la potencia de los números, acepta dos argumentos:

- Uno que corresponde a la base.
- El otro al exponente.



```python
dos_al_cubo = pow(2,3)
print("Dos elevado al cubo es", dos_al_cubo)
```

    Dos elevado al cubo es 8
    

## Funciones propias

Python tiene muchas funciones predefinidas (como __len()__), pero nosotros podemos crear nuestras propias funciones.

Para crear una función utilizamos la palabra clave __def__ de esta forma:


```python
def feet_inches_to_meters(feet, inches): # Este es el encabezado de la función
    meters = 0.0254 * inches # Este es el cuerpo de la función
    meters += 0.3048 * feet  # Este es el cuerpo de la función
    return meters            # Este es el cuerpo de la función
#   | Tener el cuenta el indentado

print("5 pies y 9 pulgadas equivale a",feet_inches_to_meters(5, 9), "metros")
```

    5 pies y 9 pulgadas equivale a  1.7526 metros
    


```python
def meters_to_feet_inches(meters):
    inches = meters / 0.0254
    feet = int(inches/12)
    inches = inches - 12 * feet
    return feet, inches

pies, pulgadas = meters_to_feet_inches(1.7526)
print("1.7526 metros equivale a", pies, "pies y", pulgadas, "pulgadas")
```

    1.7526 metros equivale a  5 pies y 9.0 pulgadas
    

Para completar, escribir una función que convierta metros en centímetros.


```python

```

Veamos otro ejemplo:


```python
def contar_vocales(texto):
    posibles_vocales = ['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U'] # Y las acentuadas...bah, no importa.
    total_de_vocales = 0
    for letra in texto:
        if letra in posibles_vocales: # if ejecuta un código si se cumple cierta condición.
            total_de_vocales += 1
    return total_de_vocales

print("La palabra 'Avenida' tiene", contar_vocales('Avenida'), "vocales")
```

    La palabra 'Avenida' tiene 4 vocales
    

Para completar, escribir una función que cuente los número mayores a 5 de una lista de números.


```python

```

Para completar, escribir una función parecida a la anterior, pero que permite al usuario de la función cualquier número que quiera, no solo el 5.


```python

```

## Importar módulos y funciones

Python viene con muchas funciones (y objetos) predefinidas.

Estas funciones están agrupadas en un __módulos__ que tienen una funcionalidad relacionada.

Por ejemplo el módulo __random__ tiene funciones que están relacionadas con la generación de números aleatorios.

Algunos funciones de este módulo son:

- random() : Elige un número flotante al azar entre 0 y 1.
- randint() : Elige un número entero de un rando dado por dos valores.
- choice() : Elige una valor de una lista dada

La mayoría de estas funciones predefinidas no están disponibles de primera mano.

Para usarlas tenemos que importar esas funciones o módulos.


```python
import random # Importa el módulo random

print(random.random())
```

    0.9990126024665164
    


```python
from random import randint # Importa la función randint del módulo random

print(randint(1,5))
```

    2
    

Además hay disponibles muchos módulos que no están predefinidos en Python, sino que
pueden obtenerse de __paquetes__ producidos por terceros.

Por ejemplo:

- el paquete __pandas__ contiene módulos para el análisis de datos.
- el paquete __numpy__ contiene módulos para hacer coputación scientifica.
- el paquete __biopython__ contiene módulos con herramientas bioinformáticas.


Para que estos paquetes estén disponibles es necesario instalarlos.

La instalación es diferente según la distribución de Python que se use.

### Python base

Los paquetes se instalan con el comando __pip__.

__pip__ se ejecuta en la línea de comandos del sistema operativo.

```{bash}
> pip install requests
# Estamos instalando el paquete requests. 
# pip se encarga de descargar el paquete, instalarlo y configurarlo.
```

### Anaconda Python

Los paquetes se instalan con el comando __conda__:

__conda__ se ejecuta en la línea de comandos del sistema operativo.

Anaconda trae una interfaz gráfica que ayuda a instalar paquetes.

```{bash}
> conda install requests
# Estamos instalando el paquete requests. 
# conda se encarga de descargar el paquete, instalarlo y configurarlo.
```

### Google Colab

En google Colab se usa también __pip__, peroo no hay un acceso directo a la línea de comandos del sistema operativo.

En una celda se escribe el comando __pip__ que corresponde y se agrega el símbolo __!__ al inicio:

```{python}
!pip install requests
```
