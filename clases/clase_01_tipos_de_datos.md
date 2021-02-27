
# Python para Bionformática

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ferorti/escuela2021/blob/main/clases/clase_01_tipos_de_datos.ipynb)

### Secciones

* Python como calculadora
* Operadores matemáticos
* ¿Qué es una variable?
* Tipos de datos:
  * numéricos
  * strings
  * booleanos

---

## Python como calculadora

Algunas cuentas con Python:


```python
3 
```




    3




```python
4 * 10
```




    40




```python
10 ** (10 + 4)
```




    100000000000000




```python
(12 - 2) * 2 / (10 - 2)
```




    2.5



Si quiero guardar el resultado de una cuenta? Lo asignamos a una variable.

Una variable es una etiqueta que utilizamos para referenciar al valor.

* pueden incluir letras, numeros y guiones bajos (_)
* no pueden empezar con un numero
* son _case sensitive_ (diferencia entre mayuscula y minusculas)

Ahora podemos hacer cuentas con el nombre de la variable pi en lugar de hacerlo con el valor:


```python
pi = 3.14
```

![](../images/svg/variable.svg)

y realizar operaciones con la variable


```python
20 * pi
```




    62.8318



Calcular (y guardar) el área de un círculo de diametro 50.


```python
area = pi * (50 / 2) ** 2 # Area de un círculo de di+ametro 50
```


```python
diametro = 50
radio = diametro / 2
area = pi * radio ** 2
```

Si queremos imprimir en pantalla el valor de una variable podemos hacerlo con la función print():
```python
print(variable)
```
* impriman en la pantalla las variables diametro, radio, y area



En python podemos tener diferentes **tipos de datos**.

Los más simple son:

* Numéricos
```python
int:      3, 8, -12, 100
float:    2.3, 0.01, -2,31
complex:  2 + 3j 
```

* Cadenas de texto (se escriben entre comillas )
```python
string:  'Texto', "a", '28', "", "ATGTGCGTGGAAGATGCG"
    ```



* Booleanos
```python
bool:     True, False```






```python
entero = 2021
flotante = pi
texto = "ATGTGCGTGGAAGATGCG"
```


```python
print(entero, flotante, texto) # la función print nos permite imprimir más de un elemento
```

    2021 3.14159 ATGTGCGTGGAAGATGCG



Para conocer el tipo de dato de un valor o una variable utilizamos la función type():


```python
type(pi)
```




    float




```python
print(type(100))
print(type())
print(type("Txt"))
```

    <class 'int'>





    str



## Operadores Matemáticos

En python, los operadores y las funciones que podamos utilizar sobre un dato va a depender de su tipo.
+ ¿Qué tipo de dato obtenemos de sumar dos enteros?
+ ¿Qué tipo de dato obtenemos de divir un entero por otro entero?
+ ¿Podremos sumar dos cadenas de texto?


```python
suma = 9 + 2
div = 9 / 2

print(type(suma))
print(type(div))
```

    <class 'int'>
    <class 'float'>



```python
# es float es porque la division no es exacta?
div = 8/2
print(div, type(div))
```

    4.0 <class 'float'>



```python
45 + 10
```




    55




```python
'45' + '10' 
```




    '4510'




```python
El operador suma + suma algebraicamente dos enteros y concatena dos strings.
```


```python
# Qué pasa si "sumo" un entero y un string?
```


```python
45 + '10'
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-53-70f3accf862c> in <module>
    ----> 1 45 + '10'
    

    TypeError: unsupported operand type(s) for +: 'int' and 'str'


El operador suma + hace la suma algebraica cuando se lo aplica sobre dos enteros mientras que sobre cadenas de texto las concatena.

En algunos casos es neceario convertir un tipo de dato en otro.
Las funciones:
+ int() convierte un valor a entero
+ float() a flotante
+ str() a string
+ bool() a booleanos

Esto no siempre es posible, depende el caso


```python
print( 45 + int("10"))
print( "45" + str("10"))
```

    55
    4510



```python
int("treinta")
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-61-d6e1b6ee3daa> in <module>
    ----> 1 int("treinta")
    

    ValueError: invalid literal for int() with base 10: 'treinta'


* Ejercicio
+ Convertir la palabra "3.14" a flotante y almacenar el resultado en una variable
+ convetir valor obtenido a entero

Ejercicio:

1) Partiendo de:
```python
a = 1.0
b = '1'
c = '1.1'
```
En cuales de las siguientes opciones obtendríamos ``2.0`` como resultado?

```python
a + float(b)
float(b) + float(c)
a + int(c)
a + int(float(c))
int(a) + int(float(c))
2.0 * b
```


---

### Strings

Como habíamos visto, los strings o cadenas de caracteres se declaran en python escribiendo el texto entre comillas simples '' o dobles ""


```python
texto = "Curso de Python" # o 'Curso de Python'
```

Los ``strings`` son secuencias **ordenadas** de caracteres.

![](../images/svg/string1.svg)

Es decir, podemos identificar cada caracter de la secuencia por su posición en el string, contando de izquierda a derecha.
+ En este caso el primer caracter del string es "C"
+ el segundo caracter es "U"
+ el 8vo es "e"
+ y el noveno es un espacio en blanco " "

A la posición que tiene un elemento (en este caso un caracter) en una secuencia la denominamos **índice** o **index**

Como en muchos otros lenguajes de programación, los índices comienzan con el 0 (el índice del primer elemento es 0, el del segundo es 1, y así...
![](../images/svg/string3.svg)

Para acceder a un caracter de un string utilizamos la notación de corchetes [ ] y el índice:


```python
palabra[0] # Recordar que los índices comienzan con 0

```




    'C'




```python
primer_caracter = texto[0]
print(primer_caracter)
```

    C


Imprimir en pantalla el primer, el segundo, el octavo y último caracter del string palabra.


```python
# completar


```

Si bien podemos acceder al último caracter del string por su índice en caso el ``14``, python nos permite utilizar también los índices contando de derecha a izquierda.
+ Al contar de derecha a izquierda se utiliza los números en negativo (agregandoles un ``-``) y se comienza de ``-1``

![](../images/svg/string4.svg)

Intentemos acceder ahora al primer, el segundo, el octavo y último caracter utilizando índices negativos.


```python
# Completar
```

Además de acceder a los caracteres, podemos obtener subsecuencias de un string.
+ Para esto se utiliza también la notación de corchetes ``[ ]``, pero necesitamos dos índices que indiquen desde donde hasta donde queremos acceder, separadas con dos puntos ``:``.

``palabra = texto[start:stop] ``

el indice del caracter ``P`` es ``9`` y el de la ``n`` es ``14`` o ``-1 ``


```python
print(texto[9])
print(texto[14])
```

    P
    n



```python
print(texto[9:14])
```

    Pytho


Qué pasó?

![](../images/svg/string7.svg)

Ejercicio
Imprimir en pantalla las palabras separadas (pueden obviar de y la)


```python
texto_largo = "Quinta escuela de verano de bioinformatica de la A2B2C"

```

---

### Booleanos

El último tipo de datos que vamos a ver hoy son los booleanos.
Son tipos de datos lógicos que permiten representar valores de lógica binarios:
* ``True``
* ``False``



Los valores del tipo boleaano se escriben con la primer letra mayúscula y sin comillas:
```python
verdadero = True
falso = False
```

utilizando ``and, or y not`` podemos operar con datos del tipo booleano, según las reglas lógicas:


```python
True
```




    True




```python
not True 
```




    False




```python
print('False or True:', False or True)
print('True or True:', True or True)
print('True and False:', True and False)
print('not True:', not True)
```

    False or True: True
    True or True: True
    True and False: False
    not True: False


Es muy muy muy común querer comparar dos o más valores, para eso utilizamos los operadores de comparación:
El resultado de estas comparaciones es un booleano


```python
suma = 3 > 5
print(suma)
print(type(suma))
```

    False
    <class 'bool'>



```python
print('3 < 5: ', 3 < 5)
print('100 == 100', 100 == 100)

```

    3 < 5:  True
    100 == 100 True


Por últmo (por ahora) se pueden combinar operadores lógicos con operadores de comparación:


```python
print('100 == 100 and 10 < 5', 100 == 100 and 10 < 5)
print('100 == 100 or 3 < 5', 100 == 100 and 3 < 5)
```

    100 == 100 and 10 < 5 False
    100 == 100 or 3 < 5 True



```python
x = 10
x_mayor_a_0 = x > 0
letra = 'Z'
letra_es_z = letra == "Z"
print(x_mayor_a_0)
print(letra_es_z)
```

    True
    True



```python
x_mayor_a_0 and letra_es_z
```




    True


