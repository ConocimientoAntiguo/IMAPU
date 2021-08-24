# Tuplas 

Como las listas, las tuplas siguen la misma estructura. Son idénticas a las listas pero con una pequeña excepción: **NO son mutables**.

Si tratamos de cambiar algún elemento por otro o eliminar, nos marcará un error.

**Métodos importantes:**

- `index(x):` Nos devuelve el índice o posición de la primer coincidencia de un elemento con x.
- `count(x):` Cuenta cuántos elementos x hay en la tupla.
- `len( ):` Calcula la cantidad de elementos o longitud de la tupla.


```python
tupla = (16,53,23,76,98,43,43,56,99,77,21,32) #Se usan paréntesis en lugar de corchetes ()


## Para acceder a un elemento en determinada posición, 
## colocaremos el nombre de la tupla y entre corchetes [] el índice
## Ejemplo: tupla[0] -> Elemento en la lista en la pos. 0 

print("Elemento en la posición 1:",tupla[1])

print("Cantidad de 43 en la tupla:",tupla.count(43))

print("Cantidad de elementos o tamaño de la tupla:",len(tupla))
```

    Elemento en la posición 1: 53
    Cantidad de 43 en la tupla: 2
    Cantidad de elementos o tamaño de la tupla: 12



```python
tupla.append(100)
tupla.sort()
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-2-59e97cb5c63b> in <module>()
    ----> 1 tupla.append(100)
          2 tupla.sort()


    AttributeError: 'tuple' object has no attribute 'append'


> Los errores generados son gracias a que queríamos modificar una tupla, la cual no tiene el método pop,sort,append,insert o similares, que modifican a la misma. Solo podemos usar métodos que no manipulen su estructura.
