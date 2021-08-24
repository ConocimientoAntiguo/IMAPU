# Decoradores 

Los decoradores son en sí mismos funciones, que toman como argumento una función y retornan otra función. No es más que una función la cual toma como input una función y a su vez retorna otra función. Puede sonar algo confuso ¿no? lo que nos debe quedar claro es que al momento de implementar un decorador estaremos trabajando, con por lo menos, 3 funciones. El input, el output y la función principal. 


```python
def decorador(pasadaSuma):
    def function(a, b):
        print("Función sumar() llamada!")
        return pasadaSuma(a, b)
    return function

@decorador
def sumar(a, b):
    return a + b

print(sumar(7, 5)) ## Si mando a llamar a sumar, también mandaré a llamar al decorador
```

    Función sumar() llamada!
    12
