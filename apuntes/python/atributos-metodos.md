# Atributos y métodos 

### Atributos: características con las que cuenta un objeto -> Adjetivos calificativos
### Métodos: cosas que puede hacer el objecto -> verbos

### Atributos de instancia
Atributos de Instancia

Los atributos de instancia son aplicables a un solo objeto. Determinan el estado en el que se encuentra un objeto.

**Ejemplo:**
El atributo altura en la clase Persona es de instancia, debido a que cada persona tendrá su propia altura.

### Atributos de clase

  Un atributo de clase es un atributo común a todos los objetos instanciados de la clase. Al estar definido en la clase no hace falta instanciar la clase para utilizarlo. Las constantes se suelen definir como atributos de clase.

**Ejemplo:**
El atributo cantidadDeOjos en la clase Persona es de clase, debido a que todas las instancias de la clase persona tendrán igual cantidad de ojos.


```python
class Empleado:
    cedula = "V-13458796" ## Atributo de clase
    def inicializar(self,nombreInsertado):
        self.nombre = nombreInsertado ## Atributo de instancia

juanito = Empleado()
juanito.inicializar("Juan")

## La cédula es incorrecta ya que no será la misma en todos los empleados
print("La cédula de todos es:",juanito.cedula) 


## Nombre es correcto ya que existe y es diferente para cada objeto
print("El nombre del empleado es:",juanito.nombre)
```

    La cédula de todos es: V-13458796
    El nombre del empleado es: Juan


### Métodos de clase -> Puede o no existir el objeto 🐳
Un método de clase puede modificar el estado de una clase, accediendo a los atributos de dicha clase, aún cuando el método es invocado desde una clase. En lugar de definirse utilizando self como primer parámetro, se utiliza cls.

### Métodos de instancia -> Tiene a fuerzas que existir el objeto 🌱
Son los que hemos visto def(self):

### Métodos estáticos -> Puede o no existir el objeto pero no puede acceder a los atributos del mismo 🐙
Los métodos estáticos están restringidos en su ámbito, de tal manera que no tienen acceso a los atributos del objeto. Se definen de forma idéntica a una función, sin necesidad de ingresar el parámetro inicial self.



```python
class PoblacionCensada:
    poblacion = 0
    nombre = ""
    poblacion = 0
    @classmethod
    def opera_poblacion(cls, operador, cantidad):
        cls.poblacion = eval(str(cls.poblacion) + operador + str(cantidad))
    
    @classmethod
    def despliega_total(cls):
        return cls.poblacion
    
    def __init__(self, nombre, numero=0):
        print("Se ha creado la población",nombre," con ",numero," habitantes")
        self.nombre = nombre
        self.poblacion = numero
        self.opera_poblacion('+', self.poblacion)   
    
    
    def imprimirHola(self):
        print("Hola mi nombre es: ",self.nombre," y mi número de habitantes es: ",self.poblacion)
```


```python
print("Método de clase: ",PoblacionCensada.despliega_total())
```

    Método de clase:  0



```python
print("Método de clase: ",PoblacionCensada.imprimirHola()) ## No se puede ya que imprimirHola
#No tiene ningún decorador para indicar que es de clase
```


```python
Chalco = PoblacionCensada("Valle de Chalco",1000000)
Chalco.imprimirHola()
```

    Se ha creado la población Valle de Chalco  con  1000000  habitantes
    Hola mi nombre es:  Valle de Chalco  y mi número de habitantes es:  1000000



```python
## Probamos un método estático para traer una dirección ip
class Servidor:
    usuarios_activos = set(())
    
    def __init__(self, dominio, lista):
        self.lista_usuarios = lista
        self.dominio = dominio
    
    def conexion(self, usuario):
        if usuario in self.lista_usuarios:
            self.usuarios_activos.add(usuario)
        else:
            return False
        
    @staticmethod
    def ping(ip):
        return ip
    
    @staticmethod
    def ImprimirHola():
        print("Hola")
```


```python
Servidor.ping("192.168.17.8")
```




    '192.168.17.8'



### Método init 

El método __init__ es el primer método que se ejecuta cuando se crea un objeto.
El método __init__ se llama automáticamente. Es decir es imposible de olvidarse de llamarlo ya que se llamará automáticamente.


```python
class Empleado:

    def __init__(self):
        self.nombre=input("Ingrese el nombre del empleado:")
        self.sueldo=float(input("Ingrese el sueldo:"))

    def imprimir(self):
        print("Nombre:",self.nombre)
        print("Sueldo:",self.sueldo)

    def paga_impuestos(self):
        if self.sueldo>3000:
            print("Debe pagar impuestos")
        else:
            print("No paga impuestos")
```


```python
sam = Empleado()
```

    Ingrese el nombre del empleado:Sam
    Ingrese el sueldo:10



```python
print("Primer día de explotación de Samuel")
sam.imprimir()
```

    Primer día de explotación de Samuel
    Nombre: Sam
    Sueldo: 10.0



```python
print("¿Samuel debe pagar impuestos?")
sam.paga_impuestos()
```

    ¿Samuel debe pagar impuestos?
    No paga impuestos
