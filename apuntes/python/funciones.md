# Funciones 

Una función es un bloque de código con un nombre asociado, que recibe cero o más argumentos como entrada, sigue una secuencia de sentencias, la cuales ejecuta una operación deseada y devuelve un valor y/o realiza una tarea.

La sentencia def es una definición de función usada para crear objetos funciones definidas por el usuario.


```python
 def hola(nombre):   # def: Se utiliza siempre que queramos definir una función
        print("Hola", nombre, "!")
```


```python
hola("Alicia")
```

    Hola Alicia !


### ¿Cómo se le conoce a lo que va entre paréntesis? 
Al definir una función los valores los cuales se reciben se denominan parámetros, pero durante la llamada los valores que se envían se denominan argumentos


```python
def suma(a,b): ## Aquí a y b se le conoce como parámetros
    print(a+b)

suma(5,2) ## aquí a 5 y 2 se le denomina argumentos
```

    7



```python
def f(x,y):
    print(x**2 + 2*x + 1 + y**2)

f(2,4)
```

    25


### Valores de retorno
Qué tal si queremos lo que suceda dentro de la función para otras cosas, no sé digamos que hace una operación matemática y queremos el resultado para otras cuentas. Existe algo que se llama return o valor retorno que quiere decir lo que devuelve la función



```python
def suma(a, b):
    return a + b

print(suma(5,3))
```

    8



```python
## Achis achis y mi suma?

print(suma(5,3))
```

    8



```python
#Vamos a ver un ejemplo matemático x^2

def f(x):
    y = x**2
    return y

operacion = f(5) + 10 # Devolvemos 5**2 + 10
print(operacion) 
```

    35


#### Se puede llamar a los parámetros de una función por posición o por nombre:
#### Y  puede tener parámetros por defecto:


```python
def algo(a,b):
    print("Resta de "+str(a)+" - "+str(b)+" = ",a-b)
    
algo(5,1)
algo(b=5,a=1)
```

    Resta de 5 - 1 =  4
    Resta de 1 - 5 =  -4



```python
## Parámetros por defecto, en caso que no pongas nada se toma el valor indicado al definir
def cosa(a=0,b=5):
    print("Resta de "+str(a)+" - "+str(b)+" = ",a-b)
    
cosa() ## 0 - 5
cosa(b=5,a=1) ## 1 - 5
cosa(10,1) ## 10 - 1
```

    Resta de 0 - 5 =  -5
    Resta de 1 - 5 =  -4
    Resta de 10 - 1 =  9


#### Una función dentro de otra

Es posible tener un def dentro de otro pero para mandar a llamar a una función primero debes mandar a llamar a la que lo contiene. Si mandamos a llamar a la `funcion( )` esta a su vez mandará a llamar a la `funcion2()`


```python
def funcion(p,q):
    r = p + q
    
    def funcion2(s):
        print(s)
        
    funcion2(5)

funcion(8,8)
```

    5



```python
#Función para saber si un número es múltiplo de otro. El primer argumento
## indica la función interna y el otro argumento la función externa

def multiplo(n):
    def multiploDe(num):
        return num%n == 0
    return multiploDe
print("¿Es 9 múltiplo de 3?",(multiplo(9))(3))
```

    ¿Es 9 múltiplo de 3? False



```python
print("¿Es 9 múltiplo de 3?",(multiplo(3))(9))
```

    ¿Es 9 múltiplo de 3? True



```python
##Podemos mandar de lo que sea a los parámetros, hasta listas:

def sumar(numbers):
    result = 0
    for number in numbers:
        result += number
    return result

print("Suma de 4 + 5 = ",sumar([4,5]))
```

    Suma de 4 + 5 =  9
