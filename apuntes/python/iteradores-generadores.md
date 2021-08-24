# Iteradores y generadores 

Los "iteradores" y "generadores" son objetos que cuentan con el método __next__(), el cual regresa una serie de objetos de uno en uno cada vez que es invocado.


```python
lista = ['1', 2, 'tres', 4.0]
print(lista)
```

    ['1', 2, 'tres', 4.0]


Creamos un iterador para ir pasando los elementos de una lista


```python
iterador = iter(lista)
print(iterador)
```

    <list_iterator object at 0x108093dd8>



```python
next(iterador)
```




    '1'




```python
next(iterador)
```




    2




```python
next(iterador)
```
    'tres'

### Yield 

Básicamente los generadores se escriben funciones normales, pero usan la sentencia yield en vez de un return dentro de un bucle. Yield funciona de manera similar al return, pero la gracia de usar el yield es que conserva la iteración del bucle para la siguiente vez que se le invoque.


```python
def contador(max):
    n=0
    while n < max:
            yield n
            n=n+1

miCuenta = contador(5)
print(miCuenta)
for i in miCuenta: ## Mandamos a traer lo que nos devuelve yield en cada ciclo
    print(i)
```

    <generator object contador at 0x10805bd58>
    0
    1
    2
    3
    4


El resultado es el mismo que si, en lugar de mycont = contador(5) hubiéramos instanciado una lista: mycont = [0,1,2,3,4] o mycont = range(0,5). Pero de hecho lo que ocurre es muy diferente.

Cuando el intérprete Python encuentra una función que incluye un yield (o varios), entiende que al llamar esta función no obtendremos un valor devuelto con un return, sino que obtendremos un generador (generator).

Un generador se comporta parecido a una lista, en el sentido que puede ser recorrida con un iterador - la diferencia es que los valores no están almacenados en una colección, sino que se generan "on the fly".
