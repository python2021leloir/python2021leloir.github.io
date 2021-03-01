<a href="https://colab.research.google.com/github/Ferorti/escuela2021/blob/main/clases/clase_08_manejo_cadenas.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

# Cadenas de texto en python

**Ejemplo de cadenas de texto en python**


```
cadena1 = 'Los primeros 20 aminoácidos de la proteína BRAF'
cadena2 = 'son MAALSGGGGGGAEPGQALFN'
print(cadena1)
print(cadena2)
```

    Los primeros 20 aminoácidos de la proteína BRAF
    son MAALSGGGGGGAEPGQALFN
    

# Funciones útiles para el manejo de cadenas

**Concatenar cadenas**


```
cadena3 = cadena1 + ' ' + cadena2 + '.'
print(cadena3)
```

    Los primeros 20 aminoácidos de la proteína BRAF son MAALSGGGGGGAEPGQALFN.
    

**Multiplicar cadenas**


```
cadena4 = "AUG" #codón de la Metionina
#obtener una cadena de nucleótidos de 6 Metioninas
cadena5 = cadena4 * 6
print(cadena5)
```

    AUGAUGAUGAUGAUGAUG
    

**Longitud, cantidad de caracteres**


```
print(len(cadena5))
```

    18
    

**Buscar una subcadena**


```
pos = cadena3.find("20")
print(cadena3)
print(pos)
```

    Los primeros 20 aminoácidos de la proteína BRAF son MAALSGGGGGGAEPGQALFN.
    13
    


```
#si la cadena no está devuelve -1
pos = cadena3.find("P15056")
print(pos)
```

    -1
    

**Convertir a mayúscula o minúsculas**


```
cadena7 = cadena1.lower()
cadena8 = cadena1.upper()
cadena9 = cadena1.capitalize()
print(cadena1)
print(cadena7)
print(cadena8)
print(cadena9)
```

    Los primeros 20 aminoácidos de la proteína BRAF
    los primeros 20 aminoácidos de la proteína braf
    LOS PRIMEROS 20 AMINOÁCIDOS DE LA PROTEÍNA BRAF
    Los primeros 20 aminoácidos de la proteína braf
    

**Remplazar texto**


```
cadena10 = cadena3.replace("BRAF", "BRAF (Uniprot: P15056)")
print(cadena3)
print(cadena10)
```

    Los primeros 20 aminoácidos de la proteína BRAF son MAALSGGGGGGAEPGQALFN.
    Los primeros 20 aminoácidos de la proteína BRAF (Uniprot: P15056) son MAALSGGGGGGAEPGQALFN.
    


```
# cadena.replace(oldtext, newtext) remplazar todas las ocurrencias
# cadena.replace(oldtext, newtext, -1) remplazar todas las ocurrencias
# cadena.replace(oldtext, newtext, 1) remplazar la 1ra ocurrencia
# cadena.replace(oldtext, newtext, 2) remplazar la 1ra y segunda ocurrencia

cadena11 = cadena3.replace("G", "-")
cadena12 = cadena3.replace("G", "-", -1)
cadena13 = cadena3.replace("G", "-", 1)
cadena14 = cadena3.replace("G", "-", 2)
print(cadena3)
print(cadena11)
print(cadena12)
print(cadena13)
print(cadena14)
```

    Los primeros 20 aminoácidos de la proteína BRAF son MAALSGGGGGGAEPGQALFN.
    Los primeros 20 aminoácidos de la proteína BRAF son MAALS------AEP-QALFN.
    Los primeros 20 aminoácidos de la proteína BRAF son MAALS------AEP-QALFN.
    Los primeros 20 aminoácidos de la proteína BRAF son MAALS-GGGGGAEPGQALFN.
    Los primeros 20 aminoácidos de la proteína BRAF son MAALS--GGGGAEPGQALFN.
    

**Subcadena**


```
cadena15 = cadena1[16:27]
print(cadena1)
print(cadena15)
```

    Los primeros 20 aminoácidos de la proteína BRAF
    aminoácidos
    

**Dividir cadena por un separador**


```
separador1 = " "
lista1 = cadena1.split(separador1)
print(cadena1)
print(lista1)
```

    Los primeros 20 aminoácidos de la proteína BRAF
    ['Los', 'primeros', '20', 'aminoácidos', 'de', 'la', 'proteína', 'BRAF']
    


```
#lista1 = cadena1.split(separador1) # dividir toda la cadena
lista2 = cadena1.split(separador1, -1) # dividir toda la cadena
lista3 = cadena1.split(separador1, 1) # dividir toda la cadena solo en el 1er separador
lista4 = cadena1.split(separador1, 2) # dividir toda la cadena solo en los 2 primeros separadores
print(cadena1)
print(lista1)
print(lista2)
print(lista3)
print(lista4)
```

    Los primeros 20 aminoácidos de la proteína BRAF
    ['Los', 'primeros', '20', 'aminoácidos', 'de', 'la', 'proteína', 'BRAF']
    ['Los', 'primeros', '20', 'aminoácidos', 'de', 'la', 'proteína', 'BRAF']
    ['Los', 'primeros 20 aminoácidos de la proteína BRAF']
    ['Los', 'primeros', '20 aminoácidos de la proteína BRAF']
    

**Concatenar cadenas con un separador**


```
separador2 = "\t"
cadena16 = separador2.join(lista1) 
print(lista1)
print(cadena16)
```

    ['Los', 'primeros', '20', 'aminoácidos', 'de', 'la', 'proteína', 'BRAF']
    Los	primeros	20	aminoácidos	de	la	proteína	BRAF
    

**Eliminar caracteres iniciales o finales de un texto**


```
cadena17 = "--MAALS------AEP-QALFN--"
cadena18 = cadena16.lstrip("-")
cadena19 = cadena16.rstrip("-")
cadena20 = cadena16.strip("-")
print(cadena17)
print(cadena18)
print(cadena19)
print(cadena20)
```

    --MAALS------AEP-QALFN--
    Los	primeros	20	aminoácidos	de	la	proteína	BRAF
    Los	primeros	20	aminoácidos	de	la	proteína	BRAF
    Los	primeros	20	aminoácidos	de	la	proteína	BRAF
    

Si al utilizar alguna de estas funciones strip(), lstrip() y rtrip() no se especifica el texto de caracteres, por defecto se eliminar los caracteres en blanco que ingluye los espacios, tabulaciones, saltos de línea, entre otros.


```
cadena21 = "  MAALS------AEP-QALFN\n"
cadena22 = cadena21.strip()
print('\"'+cadena21+'\"')
print('\"'+cadena22+'\"')
```

    "  MAALS------AEP-QALFN
    "
    "MAALS------AEP-QALFN"
    

**Formato de cadenas**


```
#Los marcadores de posición se pueden identificar mediante índices con nombre {proteina}, índices numerados {0} o incluso marcadores de posición vacíos {}
txt1 = "Los primeros {naa} aminoácidos de la proteína {proteina} son {secuencia}.".format(naa = 20, proteina="BRAF", secuencia="MAALSGGGGGGAEPGQALFN")
txt2 = "Los primeros {0} aminoácidos de la proteína {1} son {2}.".format(20, "BRAF", "MAALSGGGGGGAEPGQALFN")
txt3 = "Los primeros {} aminoácidos de la proteína {} son {}.".format(20, "BRAF", "MAALSGGGGGGAEPGQALFN")

print(txt1)
print(txt2)
print(txt3)
```

    Los primeros 20 aminoácidos de la proteína BRAF son MAALSGGGGGGAEPGQALFN.
    Los primeros 20 aminoácidos de la proteína BRAF son MAALSGGGGGGAEPGQALFN.
    Los primeros 20 aminoácidos de la proteína BRAF son MAALSGGGGGGAEPGQALFN.
    


```
txt4 = "La proteína {proteina} pesa {peso} Da.".format(
    proteina = "BRAF", naa = 766, peso = 84436.135, iduniprot="P15056"
)
txt5 = "La proteína {proteina} pesa {peso:,.1f} Da.".format(proteina = "BRAF", naa = 766, peso = 84436.135, iduniprot="P15056")
print(txt4)
print(txt5)
```

    La proteína BRAF pesa 84436.135 Da.
    La proteína BRAF pesa 84,436.1 Da.
    

**Algunos tipos de formatos que se pueden utilizar**

:<	Left aligns the result (within the available space)

:>	Right aligns the result (within the available space)

:^	Center aligns the result (within the available space)

:=	Places the sign to the left most position

:+	Use a plus sign to indicate if the result is positive or negative

:-	Use a minus sign for negative values only

: 	Use a space to insert an extra space before positive numbers (and a minus sign befor negative numbers)

:,	Use a comma as a thousand separator

:_	Use a underscore as a thousand separator

:d	Decimal format

:e	Scientific format, with a lower case e

:E	Scientific format, with an upper case E

:f	Fix point number format

:F	Fix point number format, in uppercase format (show inf and nan as INF and NAN)

:n	Number format

:%	Percentage format
