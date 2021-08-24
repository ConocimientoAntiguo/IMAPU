# Diccionarios 

Los diccionarios son lo equivalente a tablas Hash, a cada llave se le asigna un valor. 

De manera sencilla podemos dar un ejemplo: 

Tenemos un buró con muchos cajones, en los cajones podemos guardar cosas que en este caso serán variables y cuando queramos buscar una crema en el buró, naturalmente tendremos qué saber en qué cajón está. Los cajones tienen una referencia (el cajón de abajo por ejemplo) y en el caso de los diccionarios, las llaves son los cajones y guardan variables. 

Los diccionarios se escriben entre`{}` llaves y llevan la estructura `{llave:valor,llave:valor,llave:valor}`

**Métodos importantes:**

- `clear()`: Elimina todos los elementos del diccionario
- `copy()`: Devuelve una copia del diccionario
- `fromkeys(x,y)`: Devuelve un diccionario con las claves y el valor especificados
- `get(x)`: Devuelve el valor de la clave especificada
- `items()`: Devuelve una lista que contiene una tupla para cada par clave-valor
- `keys()`: Devuelve una lista que contiene las claves del diccionario
- `pop(x)`: Elimina el elemento con la clave especificada
- `popitem()`: Elimina el último par clave-valor insertado
- `setdefault()`: Devuelve el valor de la clave especificada. Si la clave no existe: inserte la clave, con el valor especificado
- `update(x,y)`: Actualiza el diccionario con los pares clave-valor especificados
- `values()`: Devuelve una lista de todos los valores del diccionario.


```python
miPrimerDiccionario = {1:"Hola",2:"Adiós"}
print("Valor de llave 1: ",miPrimerDiccionario[1])

print("Las llaves que tiene mi diccionario:",miPrimerDiccionario.keys())
print("Las cosas que tiene que mi diccionario:",miPrimerDiccionario.items())
```

    Valor de llave 1:  Hola
    Las llaves que tiene mi diccionario: dict_keys([1, 2])
    Las cosas que tiene que mi diccionario: dict_items([(1, 'Hola'), (2, 'Adiós')])



```python
miDiccionario = {"Hola":[(1,2),6,7,True],"verde":"kiwi","amarillo":"platano","amarillo":"Adiós"}
```


```python
print(miDiccionario["amarillo"])
print("Para acceder al 2 dentro de miDiccionario: ",miDiccionario["Hola"][0][1])
```

    Adiós
    Para acceder al 2 dentro de miDiccionario:  2



```python
##Podemos definir diferentes tipos de objetos para que sea nuestra clave valor, incluso hacer diccionarios de tuplas de listas
dic = {False:[1,True,2.3,"Hola"],1:"Poco"}

print(dic[False])
```

    [1, True, 2.3, 'Hola']



```python
baseDatos = {
    1: {
        "nombre":"Samuel",
        "apellido":"Garrido",
        "NumCuenta":418045231
    },
    2: {
        "nombre":"Alicia",
        "apellido":"Carballido",
        "NumCuenta":423154132
    },
    3: {
        "nombre":"Alejandro",
        "apellido":"Barreiro",
        "NumCuenta":432131523
    },
    4: {
        "nombre":"Ana",
        "apellido":"Lagunas",
        "NumCuenta":462314263
    }
}

for x in baseDatos:
    print(str(baseDatos[x]['NumCuenta'])+": "+baseDatos[x]['nombre']+" "+baseDatos[x]['apellido'])
```

    418045231: Samuel Garrido
    423154132: Alicia Carballido
    432131523: Alejandro Barreiro
    462314263: Ana Lagunas
