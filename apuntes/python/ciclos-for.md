# Ciclo for (para cada) 

Los ciclos for en python funcionan tienen una estructura algo distinta en Python que por ejemplo C o Java. Para poder utilizarlo tendremos que hacer uso de la palabra reservada **in** y luego a decisión,

La función `range()` nos devuelve un arreglo de números.

Si range(x) le insertamos solo 1 parámetro, **"x"** simboliza el punto de llegada -1 desde 0 de 1 en 1.

Si a range(x,y) le insertamos 2 parámetros, **"x"** simboliza el punto de partida y **"y"** el punto de llegada -1 y va contando de 1 en 1 hasta llegar.

Si a range(x,y,z) le insertamos 3 parámetros, **"x"** simboliza el punto de partida, **"y"** el punto de llegada -1 y z de cuanto en cuánto va salteando.


```python
jaja = [1,4,6,8]
jaja.append(1)
jaja.append(2)
jaja.append(3)
print(jaja)
```

    [1, 4, 6, 8, 1, 2, 3]



```python
listaNormal = []

for numeroInsertar in range(-4,-60,-2):
        listaNormal.append(numeroInsertar)

print(listaNormal)
```

    [-4, -6, -8, -10, -12, -14, -16, -18, -20, -22, -24, -26, -28, -30, -32, -34, -36, -38, -40, -42, -44, -46, -48, -50, -52, -54, -56, -58]



```python
a = range(10)
b = range(-10,10)
c = range(-10,10,2)

print("Primer ciclo")
for i in a:
    print(i)

print("\nSegundo ciclo")
for i in b:
    print(i)

print("\nTercer ciclo")
for i in c:
    print(i)
```

    Primer ciclo
    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    
    Segundo ciclo
    -10
    -9
    -8
    -7
    -6
    -5
    -4
    -3
    -2
    -1
    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    
    Tercer ciclo
    -10
    -8
    -6
    -4
    -2
    0
    2
    4
    6
    8


**Los ciclos for pueden implementarse con range() o con una colección (lista, tupla o diccionario) para que sea recorrido. No es necesario colocar contadores adicionales.** 


```python
for i in [1,5,9,2,6,9,0]:
    print(i)
```

    1
    5
    9
    2
    6
    9
    0



```python
jaja2 = [1,4,6,8]
for i in range(0,3,1): # ¿Cómo modifico ésto para que sea más sencillo?
    jaja2.append(i)
print(jaja2)
```

    [1, 4, 6, 8, 0, 1, 2]



```python
## Para recorrer un diccionario el for irá recorriendo las llaves, será nuestro deber colocar
## el nombre del diccionario con la clave para que nos traiga el valor.

frutas = {'Fresa':'Roja','Limón':'Verde','Papaya':'Naranja','Manzana':'amarilla','Guayaba':'rosa'}
for llave in frutas:
    print(llave, 'es de color', frutas[llave])
    
```

    Fresa es de color Roja
    Limón es de color Verde
    Papaya es de color Naranja
    Manzana es de color amarilla
    Guayaba es de color rosa
