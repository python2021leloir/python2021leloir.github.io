## Funciones Built-in, errores y ayuda

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ferorti/escuela2021/blob/main/clases/clase_02_coding.ipynb)

Además de valores, variables y tipos de datos, ya vimos algunas cosas que todavía no explicamos.

#### Comentarios

Además del codigo que queremos ejecutar, es altamente recomendable comentar/documentar el codigo para facilitar la interpretación del mismo.
Al principio los comentarios pueden parece triviales, pero se vuelven fundamentales mientras se va complejizando el código.
En python podemos comentar una linea con un ``#``.

Todo lo que esté a la derecha del ``#`` será ignorado por el interprete


```python
# Esta linea no sera ejecutada por el interprete de Python
pi = 3.14 # Esta linea tampoco sera tenida en cuenta
print(pi)
```

    3.14
    

Dentro de lo posible evitar comentarios que "redundantes" con el código:


```python
# Defino cuanto vale pi
pi = 3.14 # Pi es igual a 3.14
print(pi) # Imprimo el valor
```

    3.14
    

---

##### Funciones Buil-in

El intérprete de Python tiene una serie de funciones y tipos incluidos en él que están siempre disponibles

Ya vimos algunas, recuerdan cuales?

```python
print() # Imprime en pantalla
int()   # convierte un valor a entero
str()   # convierte un valor a string
len()   # devuelve el largo de una secuencia (por ahora)
```

los valores que les pasamos a una función se donominan argumentos, pueden ser uno, varios o ninguno, dependiendo la función.
Los argumentos se escriben entre paréntesis y si no hay arguementos se escriben los paréntisis solos:


```python
print(1, "comienzo.")  # Dos argumentos
print()                # Ningun argumento
print("final")         # Un argumento
```

    1 comienzo.
    
    final
    

las funciones en python devuelven/retornan valores, esos valores en general pueden:



```python

```


```python
seq = 'ATGGCGT'

len(seq) # la funcion len devuelve 7, si no hacemos nada con eso, ese valor se pierde

print('largo de la secuencia', len(seq)) # imprime en pantalla
largo = len('ATGGCGT')                   # guarda en otra variable
float(len(seq))                          # se lo pasa como argumento a otra funcion
```

    largo de la secuencia 7
    




    7.0






```python
# Que pasa con esto?
largo = print(seq)
```

    ATGGCGT
    


```python

```


```python

```

Más funciones built-in usadas regularmente:
```python
max()
abs()
```


```python
print(max(100, 30))

print(abs(-4.29))
```

    100
    4.29
    


```python
el comportamiento y lo que devuelve una función depende de los argumentos:
```


```python
print(max(12,3,61, 2.3e3)) # Devuelve un float
print(max(12,3,61, 8))     # Devuelve un integer
print(max('B', 'A', "H", 'm', 'M'))       # ?? Devuelve un string
```

    2300.0
    61
    m
    

Qué pasa si ejecutamos el siguiente código
```python
max(3, 'A')
```



---

#### Errores

Los errores al escribir códigos son inevitables y pasan **todo** el tiempo.
Es muy común al hacer los primeros pasos programando que los errores nos ~~den ganas de romper todo~~ desmotiven.
Luego, con práctica y años lo más común es que los errores ~~nos sigan dando ganas de romper todo~~ los veamos como parte normal del desarrollo.

Seguramente ya nos equivocamos es cuestion de tiempo...

Algunos errores comunes que suelen pasar todo el tiempo:


```python
texto = "Python
```


      File "<ipython-input-44-c18a5d7b6629>", line 1
        texto = "Python
                       ^
    SyntaxError: EOL while scanning string literal
    



```python
print(TEXTO)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-45-771c08338beb> in <module>
    ----> 1 print(TEXTO)
    

    NameError: name 'TEXTO' is not defined



```python
texto = 'Python'
texto[8]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-50-2ed3fd604f89> in <module>
          1 texto = 'Python'
    ----> 2 texto[8]
    

    IndexError: string index out of range



```python
texto = 'Python'
texto[3] = 'H'
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-52-6fefb1e6d122> in <module>
          1 texto = 'Python'
    ----> 2 texto[3] = 'H'
    

    TypeError: 'str' object does not support item assignment


Lo primero que hay que hacer cuando nos encontramos con un error es **leer** qué tipo de error es.
Es fundamental no quedarnos con la idea de que "**algo** no anda" o "**algo** está mal", porque los errores en python son muy informativos y facilitan mucho descubrir qué es lo que estamos haciendo mal.

Por ejemplo el primer error:


![](https://github.com/Ferorti/escuela2021/raw/main/)



La gran mayoría de las veces leyendo el informe del error podemos darnos cuenta de cuál es el problema y corregirlo.


~~``texto = "Python``~~
```python
texto = "Python"

```


Tomense un rato para entender cual es el problema en cada caso y como se solucionaría (en los casos que se pueda)


**No desanimarse**
...

y pedir ayuda ;)

---

#### Ayuda en Python

Podemos pedir ayuda utilizando la funcion built-in ``help()`` pansando el nombre de la función como argumento


```python
help(print)
```

    Help on built-in function print in module builtins:
    
    print(...)
        print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
        
        Prints the values to a stream, or to sys.stdout by default.
        Optional keyword arguments:
        file:  a file-like object (stream); defaults to the current sys.stdout.
        sep:   string inserted between values, default a space.
        end:   string appended after the last value, default a newline.
        flush: whether to forcibly flush the stream.
    
    

con ``help(print)`` obtuvimos resumidamente qué hace la función, los argumentos principales que recibe, y una breve descripción de otros argumentos opcionales

Algunos editores o entornos de desarrollo pueden agregar herramientas extras a la función help de python para facilitar la búsqueda de información.
Por ejemplo, si estamos utilizando notebooks podemos agregar dos signos de interrogación a la función y obtener más ayuda.
Tambien podemos apretar ``shift + tab`` dentro del paréntesis, lo que es más dinámico. 


```python
??print
```


    [0;31mDocstring:[0m
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
    
    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
    [0;31mType:[0m      builtin_function_or_method
    



```python
print()
```

Y por supuesto...

Nadie ... Programa ... Sin ... StackOverflow

[![Search on StaackOverflow](https://digital.hbs.edu/platform-digit/wp-content/uploads/sites/2/2018/03/stack-895x200.png)](https://stackoverflow.com/questions/642154/how-to-convert-strings-into-integers-in-python)



<iframe
    width='80%'
    heigth='400'
    src="www.stackoverflow.com">
</iframe>

tomensé un ratito para revisar la ayuda de las funciones que uilizamos hasta ahora.
Por ejemplo


```python
??float
```


    [0;31mInit signature:[0m [0mfloat[0m[0;34m([0m[0mx[0m[0;34m=[0m[0;36m0[0m[0;34m,[0m [0;34m/[0m[0;34m)[0m[0;34m[0m[0;34m[0m[0m
    [0;31mDocstring:[0m      Convert a string or number to a floating point number, if possible.
    [0;31mType:[0m           type
    [0;31mSubclasses:[0m     
    



```python

```
