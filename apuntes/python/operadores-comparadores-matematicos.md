# Operadores y comparadores matemáticos

Dentro de la programación existe mucha lógica. Varios elementos de comparación en matemáticas como lo es <, >, ≤, ≥, ≠(!=), o algún método dentro de los objetos tienen la función de devolver un elemento **BOOLEANO** (BOOLEANO: TRUE OR FALSE). Nos devuelve este booleano para determinar si es cierto o falso el enunciado.

Además de los clásicos operadores matemáticos descritos por los siguientes símbolos:

- \+ : Suma
- \- : Resta
- \* : Producto
- / : División
- // : División entera 
- % : Módulo o residuo 



```python
a = 6
b = 5
c = 5
print("La suma a+b es: "+str(a)+" + "+str(b)+" = ",a+b)
print("La resta a-b es: "+str(a)+" - "+str(b)+" = ",a-b)
print("El producto a*b es: "+str(a)+" * "+str(b)+" = ",a*b)
print("El cociente a/b es: "+str(a)+"/"+str(b)+" = ",a/b)
print("El cociente entero a/b es: "+str(a)+"//"+str(b)+" = ",a//b)
print("El módulo o residuo a%b es: "+str(a)+"%"+str(b)+" = ",a%b)


## OJO:
## =  1 signo significa asignación, 
## == doble significa preguntar si son iguales a python

print("\n")
print("¿a es igual a b?",a == b) 
print("¿b es igual a c?",b == c)
print("¿a es menor que 5?",a<5)
print("¿b es mayor a c?",b>c)
print("¿c es diferente de 6?",c!=6)

# No solamente se pueden comparar números, también cadenas de texto

texto1 = "Hola"
texto2 = "Hola"
print("¿texto1 es igual a texto2?",texto1 == texto2)
## Tener cuidado al comparar strings de esta manera, se recomienda 
## funciones especializadas.
```

    La suma a+b es: 6 + 5 =  11
    La resta a-b es: 6 - 5 =  1
    El producto a*b es: 6 * 5 =  30
    El cociente a/b es: 6/5 =  1.2
    El cociente entero a/b es: 6//5 =  1
    El módulo o residuo a%b es: 6%5 =  1
    
    
    ¿a es igual a b? False
    ¿b es igual a c? True
    ¿a es menor que 5? False
    ¿b es mayor a c? False
    ¿c es diferente de 6? True
    ¿texto1 es igual a texto2? True
