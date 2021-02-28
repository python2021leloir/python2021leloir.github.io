# Objetos

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ferorti/escuela2021/blob/main/clases/clase_07_clases_y_objetos.ipynb)

## Secciones
- ¿Que son las objetos?
- ¿Qué es un método?
- Crear objetos propios.


En general las listas y los diccionarios son suficientes para representar muchos de los datos con los que trabajamos día a día.

Sin embargo a veces es preferible tener una estructura que se ajuste mejor a nuestro problema particular.

Por ejemplo, si en el día a a día trabajamos con secuencias de ADN, es conveniente tener una __clase__ de objetos que tenga la funcionalidad espefíca que vamos a necesitar.

Biopython tiene un tipo de objetos para representar secuencias.

Este tipo de objeto se llama __Seq__.



```python
from Bio.Seq import Seq

seq = Seq("atgactgctacggtctacttgacac")
print(type(seq))

translated = seq.translate()
print(translated)
```

    <class 'Bio.Seq.Seq'>
    MTATVYLT
    

## ¿Qué son los métodos?

Los métodos son "funciones" especiales que están atadas a una clase de objeto.

```
mi_seq = Seq("atg") # mi_seq es una [instacia] de la [clase] Seq.

mi_seq.translate() # translate es un [método] del objeto mi_seq.

```

## Crear clases de objetos

![](https://github.com/Ferorti/escuela2021/raw/main/images/svg/class_coockies.svg)


```python
class SuperSeq(): # Con la palabra clave class creo una nueva clase.
    
    def __init__(self, seq):
        # __init__ es un método especial que sirve para crear nuevas instancias.
        print("Estoy creando una nueva instancia de SuperSeq")
        self.datos = seq
        # self hace referencia al objeto que está siendo usado.
        # datos es una nueva variable que está siendo creada y 
        # está ligada al objeto. 
    
    def largo(self):
        # es un método definido por mi que devuelve el largo de la secuencia
        return len(self.data)

superseq1 = SuperSeq("atg")
print(superseq1.datos)
print(superseq1.len())


```

    Estoy creando una nueva instancia de SuperSeq
    atg
    

## Todo en python son objetos

Los objetos están por todos lados en python, tanto que a veces ni lo notamos.

- Las listas y los diccionarios son objetos.
- Los strings son objetos
- Los números son objetos



```python
mi_numero = 2.6
mi_numero.is_integer() # is_integer es un método
```




    False




```python
"texto".find("x") # find es un método
```




    2




```python
# Hasta la funciones son objetos
print(abs.__str__()) # __str__ es un método
print(type(abs))
```

    <built-in function abs>
    <class 'builtin_function_or_method'>
    
