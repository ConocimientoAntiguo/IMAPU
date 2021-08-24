# Listas 

Son colecciones de elementos que permiten la mutabilidad de elementos. Se delimitan por corchetes `[ ]`

Existen una serie de funciones que nos permiten interactuar con una lista. 
Para una función solo agregamos a la lista un punto, seguido de la función y sus parámetros.     

**lista.funcion(parámetro)**

**OJO:** Los índices de las listas comienzan desde el 0, quiere decir que si nos queremos referir al primer elemento de la lista diremos que está en la posición 0.

**Métodos importantes:**

- `append(x):` Agrega un elemento x al final de la lista.
- `insert(i, x):` Agrega un elemento x en la posición i que le indiquemos.
- `remove(x):` remueve 1 elemento x de la lista. 
- `pop( ):` Nos remueve el último de la lista pero igual nos permite saber cuál fue.
- `clear( ):` Remueve todos los elementos de la lista.
- `index(x):` Nos devuelve el índice o posición de la primer coincidencia de un elemento con x.
- `count(x):` Cuenta cuántos elementos x hay en la lista.
- `sort( ):` Ordena la lista de menor a mayor con números o alfabéticamente con Strings.
- `len( ):` Calcula la cantidad de elementos o longitud de la lista.


```python
## Aquí tenemos una lista, se puede diferenciar de los demás porque tiene [ ] corchetes

lista = [4, 8, 16, 43, 23, 300, 44, 76, 65,44,44]

## Removemos solo 1 elemento 44
lista.remove(44)
print("Lista después de remover un 44: ",lista)

## Para acceder a un elemento en determinada posición, 
## colocaremos el nombre de la lista y entre corchetes el índice
## Ejemplo: lista[0] -> Elemento en la lista en la pos. 0 

print("Elemento en la posición 8 de lista: ",lista[8])

lista.append(100)
print("Lista después de agregar 100 al final:",lista)

lista.insert(2,5)
print("Lista después de insertar 5 en la pos. 2: ",lista)

print("Tamaño lista:",len(lista), ", lista: ",lista)

print("El número 23 se encuentra en la posición: ",lista.index(44))

lista.sort()
print("Lista ordenada: ",lista)
```

    Lista después de remover un 44:  [4, 8, 16, 43, 23, 300, 76, 65, 44, 44]
    Elemento en la posición 8 de lista:  44
    Lista después de agregar 100 al final: [4, 8, 16, 43, 23, 300, 76, 65, 44, 44, 100]
    Lista después de insertar 5 en la pos. 2:  [4, 8, 5, 16, 43, 23, 300, 76, 65, 44, 44, 100]
    Tamaño lista: 12 , lista:  [4, 8, 5, 16, 43, 23, 300, 76, 65, 44, 44, 100]
    El número 23 se encuentra en la posición:  9
    Lista ordenada:  [4, 5, 8, 16, 23, 43, 44, 44, 65, 76, 100, 300]


#### Podemos tener listas con elementos mixtas e incluso listas dentro de listas y estos dentro de listas y sucesivamente. No se recomienda hacer tanto anidamiento.


```python
lista2 = ["Hola","Adiós",2,False,4.5,[1,[2,3],4]]
print("Lista:",lista2)
lista2.append(6)
print("Lista después de agregar un 6: ",lista2)
print("Índice de 2 en la lista",lista2.index(2))
```

    Lista: ['Hola', 'Adiós', 2, False, 4.5, [1, [2, 3], 4]]
    Lista después de agregar un 6:  ['Hola', 'Adiós', 2, False, 4.5, [1, [2, 3], 4], 6]
    Índice de 2 en la lista 2



```python
## Algunos métodos como sort no se podrán ya que los elementos que contiene no son del mismo tipo.
lista2.sort()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-34-71fd039ea1e5> in <module>()
          1 ## Algunos métodos como sort no se podrán ya que los elementos que contiene no son del mismo tipo.
    ----> 2 lista2.sort()
    

    TypeError: '<' not supported between instances of 'int' and 'str'
