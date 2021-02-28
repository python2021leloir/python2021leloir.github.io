# Control de flujo

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ferorti/escuela2021/blob/main/clases/clase_06_control_de_flujo.ipynb)

## Secciones
- ¿Cómo se controla el flujo de ejecución en python?
- Ejecución condicional
- Repetición de código

## ¿Cómo se controla el flujo de ejecución en python?

El flujo de ejecución es la secuencia ordenada precisa de instrucciones de código que se
ejecutan mientras un programa está en funcionamiento.

Es posible escribir programas que sea una secuencia lineal de instrucciones.

![](https://github.com/Ferorti/escuela2021/raw/main/images/svg/linear_flow.svg)

Pero, lo más común es que cualquier programa sea algo más parecido a esto...

![](https://github.com/Ferorti/escuela2021/raw/main/images/svg/non_linear_flow.svg)


```python
Hay dos mecanismos generales para guiar el flujo de ejecución de un programa.

- La ejecución condicional
- Bucles o ciclos para repetir código.
```

## Ejecución condicional

La palabra clave __if__ permite la ejecución de cierta parte de código:


```python
if condición:
    código si se cumple la condición
else:
    código si no se cumple la condición
```


```python
n = 10.05

if n == int(n) :
    print(n, "es un número entero")
else:
    print(n, "no es un número entero")
```

    10.05 no es un número entero
    

La rama de ejecución "else:" puede no estar presente si no es necesaria.


```python
n = 10.05
if n == int(n) :
    print(n, "es un número entero")
```

Para completar, escribir un programa que elija un número al azar entre 0 y 1 y que imprima "es mayor a 0.5" o "no es mayor a 0.5" según corresponda. 


```python
from random import random
a = random()
print(a)
```

    0.8686256651297604
    

## Repetición de código    

Con la palabra clave __for__ vimos como repetir una tarea para cada elemento de una lista o diccionario.


```python
bolsillo = ['las llaves', 'una billetera', 'muchas monedas', 'un pendrive']

for cosa in bolsillo:
    print("En mi bolsillo siempre llevo", cosa)
```

    En mi bolsillo siempre llevo las llaves
    En mi bolsillo siempre llevo una billetera
    En mi bolsillo siempre llevo muchas monedas
    En mi bolsillo siempre llevo un pendrive
    

La función __range()__ genera un rando de número enteros desde cero al un número que se quiera.

Es función se puede usar en un __for__ para repetir una tarea una cierta cantidad de veces.


```python
for i in range(5):
    print("Repitiendo tarea [", i, ']')
```

    Repitiendo tarea [ 0 ]
    Repitiendo tarea [ 1 ]
    Repitiendo tarea [ 2 ]
    Repitiendo tarea [ 3 ]
    Repitiendo tarea [ 4 ]
    

Otra forma de repetir código es con la palabra clave __while__, que permite ejecutar código mientras se cumple cierta condición.


```python
a = 4
while a >= 1:
    print("El valor actual de a es", a)
    a -= 1
```

    El valor actual de a es 4
    El valor actual de a es 3
    El valor actual de a es 2
    El valor actual de a es 1
    

Para completar, escribir una función que busque en un lista de caracteres, la posición del primer caracter que sea una vocal mayúscula o un número.



```python
lista_de_prueba = ['a', 'b', 's', 'X', '5', 'a', 'E']

```
