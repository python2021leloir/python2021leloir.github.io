# Diccionarios

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ferorti/escuela2021/blob/main/clases/clase_05_diccionarios.ipynb)

## Secciones
- ¿Que son los diccionarios?
- Métodos
- Recorrer un diccionario

##  ¿Qué son los diccionarios?

Son estructuras de datos que asocian dos grupos de datos diferentes.

Se asocia un valor de un grupo, con otro valor del otro grupo.

Veamos el ejemplo:


Tengo dos grupos de datos.

- El primero es una lista con nombre de aminoácidos (código de una letra).
- El segundo es una lista con el peso molecular de los aminoácidos.


```python
amino = [
	'I', 'L', 'K', 'M', 'F',
	'T', 'W', 'V', 'R', 'H',
	'A', 'N', 'D', 'C', 'E',
	'Q', 'G', 'P', 'S', 'Y'
]
pm = [
	131.1736, 131.1736, 146.1882, 149.2124, 165.1900,
	119.1197, 204.2262, 117.1469, 174.2017, 155.1552,
	89.0935,  132.1184, 133.1032, 121.1590, 147.1299,
    146.1451, 75.0669,  115.1310, 105.0930, 181.1894
]
```

El valor en la lista __pm__ en cierta posición corresponde al peso molecular del aminoácido de la lista amino en la misma posición.


```python
print("El peso molecular de", amino[2], "es", pm[2], "gr/mol.")
```

    El peso molecular de K es 146.1882 gr/mol.
    


```python
En lugar de tener dos listas separadas y recordar que el valor de una lista se corresponde con la otra.
Podemmos construir un diccionario, donde la correspondencia es explícita y muy fácil de entender.
```


```python
pesos_de_amino = {
    'I': 131.1736 , # la clave 'I' está asociada al valor 131.1736.
    'L': 131.1736 ,
    'K': 146.1882 ,
    'M': 149.2124 ,
    'F': 165.1900 ,
    'T': 119.1197 ,
    'W': 204.2262 ,
    'V': 117.1469 ,
    'R': 174.2017 ,
    'H': 155.1552 ,
    'A': 89.0935 ,
    'N': 132.1184 ,
    'D': 133.1032 ,
    'C': 121.1590 ,
    'E': 147.1299 ,
    'Q': 146.1451 ,
    'G': 75.0669 ,
    'P': 115.1310 ,
    'S': 105.0930 ,
    'Y': 181.189 
}
```

En este ejemplo, el código de los aminoácidos funciona como una clave (o etiqueta, o __key__) que sirve para acceder al valor que le corresponde.

Para recuperar el valor que le corresponde a una clave uso \[ \]


```python
print("El peso molecular de K es", pesos_de_amino["K"])
```

    El peso molecular de K es 146.1882
    

Si quiero recuperar un valor con una clave que no existe en el diccionario, se genera un error (KeyError).


```python
print("El peso molecular de O es", pesos_de_amino["O"])
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-5-b44ed3dc3461> in <module>
    ----> 1 print("El peso molecular de O es", pesos_de_amino["O"])
    

    KeyError: 'O'



```python
Las claves no tienen que ser __strings__. Pueden otras cosas, por ejemplo números.
```


```python
numero_en_palabras = {
    1: 'Uno',
    2: 'Dos',
    3: 'Tres'
}
print("El número 1 se escribe:", numero_en_palabras[1])
```

    El número 1 se escribe: Uno
    


```python
Para completar, hacer una función que calcula el peso molecular de una proteína, dada su secuencia.
```


```python
def prot_pm(secuencia):
    pm = 0
    pass

secuencia = "MGQCCLPLPL"
print("El peso molecular de", secuencia, "es", prot_pm(secuencia))
```

    El peso molecular de MGQCCLPLPL es 1074.5252
    


```python
## Algunos métodos y funciones de los diccionarios

La función __list()__ aplicada a un diccionario permite obtener una lista con las claves.
```


```python
claves = list(pesos_de_amino)
print("Las claves son:", claves)
```

    Las claves son: ['I', 'L', 'K', 'M', 'F', 'T', 'W', 'V', 'R', 'H', 'A', 'N', 'D', 'C', 'E', 'Q', 'G', 'P', 'S', 'Y']
    

El método __values()__ permite recuperar a todos los valores del diccionario.


```python
valores = list(pesos_de_amino.values())
print("Los valores son:", valores)
```

    Los valores son: [131.1736, 131.1736, 146.1882, 149.2124, 165.19, 119.1197, 204.2262, 117.1469, 174.2017, 155.1552, 89.0935, 132.1184, 133.1032, 121.159, 147.1299, 146.1451, 75.0669, 115.131, 105.093, 181.189]
    

Otra forma de recuperar un valor de un diccionario es con el método __.get()__.


```python
print("El peso molecular de la Alanina es", pesos_de_amino.get("A"), "gr/mol")
```

    El peso molecular de la Alanina es 89.0935 gr/mol
    


```python
print("El peso molecular de la Ornitina es", pesos_de_amino.get("O"), "gr/mol")
# La función .get() no genera un error si una clave no está presente. 
# En cambio devuelve None.
```

    El peso molecular de la Ornitina es None gr/mol
    

Es posible agregar nuevos elementos a un diccionario que ya existe.


```python
pesos_de_amino["U"] = 167.06 # U es Selenocisteina
```
