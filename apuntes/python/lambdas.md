# Lambdas 

Se trata de crear funciones de manera rápida, just in time, sobre la marcha, para prototipos ligeros que requieren únicamente de una pequeña operación o comprobación.

```python
lambda argumentos: resultado
```


```python
def f(x, y, z):
    return (x+y) * z

print("(5+6) * 4 =",f(5,6,4))
```

    (5+6) * 4 = 44



```python
g = lambda x, y, z: (x+y) * z

print("(5+6) * 4 =",(g(5,6,4)))
```

    (5+6) * 4 = 44


En el ejemplo anterior, un lambda nos permite definir tanto a f y g en una sola línea y ambos tienen el mismo resultado.


```python
def Multiplo(n):
    return lambda a : a * n

productoCon = Multiplo(3)

print("11 * 33 =",productoCon(11)) 

## Podemos incluso devolver una función lambda para pasarle parámetros de otra función en este caso
```

    11 * 33 = 33
