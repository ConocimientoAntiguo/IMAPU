# Operadores lógicos. 

Los operadores lógicos son los que trabajan con valores booleanos, nos devuelven falso o verdadero y son la escencia de las condiciones. 

### Operador AND

El operador and evalúa si las condiciones TODAS se cumplen:


```python
True and False
```




    False



Podemos combinar varios operadores AND dentro de la sentenia if, pero tener en cuenta que todas las condiciones deberán ser ciertas para ejecutar el bloque de código que contiene el condidicional o mandarlo para el bloque else.


```python
examenes = int(input("Ingrese el número de exámenes: "))
tareas = int(input("Ingrese el número de tareas: "))
participaciones = int(input("Ingrese el número de participaciones: "))

if examenes >= 10 and tareas >=10 and participaciones >=10:
    print("Podrás ir a la peda")
else:
    print("Híjole creo que no se va a poder")
```

    Ingrese el número de exámenes: 10
    Ingrese el número de tareas: 20
    Ingrese el número de participaciones: 40
    Podrás ir a la peda


### Operador OR

El operador **or** evalúa si **ALGUNO** DE LOS VALORES ES VERDADERO


```python
tengoPaseFiesta = False
miCompaTiene = True

if tengoPaseFiesta or miCompaTiene:
    print("Podemos pasar")
else:
    print("Nos quedamos fuera")
```

    Podemos pasar



```python
edad = 18
dinero = 10000
fama = 80 #supongamos que se mide del 1 al 100

if edad >= 18 or dinero >= 1000 or fama >= 50:
    print("Ya llegué paps")
else:
    print("No te preocupes príncipe, ahí para la otra")
```

    Ya llegué paps


### Operador NOT

El operador **not** devuelve el valor opuesto al valor booleano.


```python
print(not True)
```

    False



```python
mayonesa1 = "Hellmans"
mayonesa2 = "Nestlé"

if mayonesa1 is not "McCORMICK":
    print("Un toque del sabor de mayonesa McCORMICK")
    
if mayonesa2 != "McCORMICK":
    print("Un toque del sabor de mayonesa McCORMICK")
```

    Un toque del sabor de mayonesa McCORMICK
    Un toque del sabor de mayonesa McCORMICK


**Aquí aparece una situación.** ⚠️

Es bastante frecuente que se use de sinónimos a **is** y **==** o **is not** con **!=**. 

Aunque suelen funciona de forma similar sus comportamientos no son exactamente iguales. 

**is** devolverá TRUE si las 2 variables apuntan al mismo objecto.

**==** devolverá TRUE si los valores de las variables son iguales.



```python
a = 1000
b = 999
```


```python
print("¿a es b+1?",a is b + 1)
```

    ¿a es b+1? False



```python
print("¿a continene un valor igual a b+1?",a == b + 1)
```

    ¿a continene un valor igual a b+1? True

