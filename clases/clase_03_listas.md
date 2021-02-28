# Listas

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ferorti/escuela2021/blob/main/clases/clase_03_listas.ipynb)

## Secciones
* Que son las listas
* Acciones comunes que hacemos con las listas
* Métodos y funciones
  * .append()
  * .insert() 
  * .remove()
  * .pop()
  * sorted() y .sort()
* slicing y concatenación
* pertenecia de un elemento
* Bucle For (introduccion)


## ¿Qué es una lista?

* Colección **ordenada** de elementos (datos)
* Mutable (se pueden cambiar los elementos)

Las listas se definen mediante corchetes [] con los elementos que conforman la lista separados por comas ,


```python
genes = ['P53', 'KRAS', 'BRCA1', 'CDKN2A', "BRCA2"]
```


```python
print(genes)
print(type(genes))
```

    ['P53', 'KRAS', 'BRCA1', 'CDKN2A', 'BRCA2']
    <class 'list'>
    

### Qué podemos hacer con una lista?

* Acceder a los elementos
* Modificar elementos
* Contar elementos
* Agregar elementos
* Quitar elementos
* Ordenar la lista
* Saber si un elemento está en la lista


Utilizando los \[ \] podemos acceder a los elementos de la lista según su posición (similar a como hicimos con los strings)


```python
print('El tercer gen de la lista es:', genes[2])
# ¿Por qué uso el índice '2' si quiero acceder al tercer elemento?

```

    El tercer gen de la lista es: BRCA1
    

Completar


```python
print('El primer gen de la lista es:', ______ )
print('El segundo gen de la lista es:', ______ )
print('El anteúltimo gen de la lista es:', ______)

```

    El primer gen de la lista es: P53
    El segundo gen de la lista es: KRAS
    El anteúltimo gen de la lista es: CDKN2A
    

Utilizando los índices y la asignación podemos modificar los elementos de la lista


```python
genes2 = genes.copy() # copiamos la lista para no modificar la original
print(genes2)
```

    ['P53', 'KRAS', 'BRCA1', 'CDKN2A', 'BRCA2']
    


```python
genes2[2] = 'MYC'
print(genes2)
```

    ['P53', 'KRAS', 'MYC', 'CDKN2A', 'BRCA2']
    


```python
genes2[0] = genes[-1]
print(genes2)
```

    ['BRCA2', 'KRAS', 'MYC', 'CDKN2A', 'BRCA2']
    


```python

```

Para saber cuántos elementos contiene la lista usamos la función len( )


```python
print('Tenemos', len(genes), 'en la lista.')
```

    Tenemos 5 en la lista.
    


```python
# recordemos que podemos asignar el largo de la lista a una variable para luego trabajar con ella
cantidad_genes = len(genes)
print('Tenemos', len(genes), 'en la lista.')
```

    Tenemos 5 en la lista.
    

Para agregar elementos a una lista tenemos dos métodos:
* .append() > agrega un elemento al final de la lista
* .insert() >  agrega un elemento en una determinada posición (tenemos que decirle donde va agregar el nuevo elemento)

tener en cuenta que estamos agregando elementos a la lista original


```python
print(genes)
genes.append('RB1')
print(genes)
```

    ['P53', 'KRAS', 'BRCA1', 'CDKN2A', 'BRCA2']
    ['P53', 'KRAS', 'BRCA1', 'CDKN2A', 'BRCA2', 'RB1']
    


```python
genes.insert(3, 'EGFR')
print(genes)
```

    ['P53', 'KRAS', 'BRCA1', 'EGFR', 'CDKN2A', 'BRCA2', 'RB1']
    

Para borrar elementos de la lista podemos utilizar:
* .remove() Quita el elemento de la lista
* .pop() Quita un elemento de la lista según la posición


```python
print("Antes:", genes)
genes.remove("BRCA2")
print("Después:", genes)
```

    ['P53', 'KRAS', 'BRCA1', 'EGFR', 'CDKN2A', 'BRCA2', 'RB1']
    ['P53', 'KRAS', 'BRCA1', 'EGFR', 'CDKN2A', 'RB1']
    


```python
print("Antes:", genes)
genes.pop(3)
print("Después:", genes)
```

    ['P53', 'KRAS', 'BRCA1', 'EGFR', 'CDKN2A', 'RB1']
    




    'EGFR'




```python
print(genes)
genes.pop(-1)
print(genes)
```

    ['P53', 'KRAS', 'BRCA1', 'CDKN2A', 'RB1']
    ['P53', 'KRAS', 'BRCA1', 'CDKN2A']
    


```python
genes = ['P53', 'KRAS', 'BRCA1', 'EGFR', 'CDKN2A', 'BRCA2', 'RB1']
```

Ejercicio:
Con los visto hasta ahora, a partir de la listas __supresores__ y __oncogenes__ genere la lista cancer_genes con los siguientes elementos:

* P53
* KRAS
* BRCA1
* EGFR
* CDKN2A
* BRCA2
* EGFR

No vale escribir los nombres de los genes, pueden crear variables (por ej: ``supresores3 = supresores[2]`` ) para ayudarse


```python
supresores = ["APC", "VHL", "BRCA1", "DCC", "SMAD4", "CDKN2A", "SMAD2", "MEN1", "NF1", "P53", "PTEN", "NF2", "WT1", "BRCA2"]
oncogenes = ["MCF2", "ALK", "EGFR", "HST", "ABL", "KRAS", "RET", "TSC2", "TRK", "MYC"]
# Completar 

```


```python
# Completar:

genes.insert(__, ____)
```

## Ordenar listas

Para ordenar alfabeticamente o de menor a mayor los elementos de una lista podemos utilizar:
* la función __sorted()__
* el método __.sort()__

¿Por qué existen dos formas de hacerlo?

- La función __sorted()__ crea una nueva copia ordenada de la lista.
- El método __.sort()__ ordena la lista original, modificándola.


```python
print(sorted(genes))
```

    ['BRCA1', 'CDKN2A', 'KRAS', 'P53']
    

¿Como sería con sorted?



```python
print(genes.sort())
```

    None
    

Qué paso?

## Sublistas

Si ya tengo una lista creada, es muy fácil crear otra que tenga un parte de la primera (una sublista).

A esta operación se la llama __slicing__.

La sintáxis es idéntica a la usamos con los __strings__.


```python
sublista_de_genes = genes[0:3]
# ¿Cuantos elementos tiene sublista_de_genes?
```

Para completar, hacer una sublista con los últimos tres elementos de la lista genes:


```python

```

## Recorrer una lista

Es muy frecuente que si tenemos una lista querramos visitar cada elemento de esa lista y aplicar sobre ese elemento una función o ejecutar cierto código.

Una forma de recorrer una lista (y otras estructuras de datos) es usando la palabra clave __for__.



```python
for gen in genes: 
    print("El gen", gen, "tiene", len(gen), "caracteres") # Esta línea de código se ejecuta por cada elemento en la lista genes.
#   | Notar el indentado

```


```python
for gen in genes:
    print("El gen", gen, "tiene la letra 'A'?...", 'A' in gen)
```

    El gen P53 tiene la letra 'A'?... False
    El gen KRAS tiene la letra 'A'?... True
    El gen BRCA1 tiene la letra 'A'?... True
    El gen CDKN2A tiene la letra 'A'?... True
    El gen BRCA2 tiene la letra 'A'?... True
    

Para completar, recorrer una lista e imprimir el primer caracter de cada gen.


```python

```
