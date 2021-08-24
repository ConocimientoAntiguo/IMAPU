# Herencia 

La herencia hace que se puedan declarar nuevas clases basadas en otras para poder reutilizar el código, generando así una jerarquía de clases dentro de una aplicación. Si una clase deriva de otra, esta hereda sus atributos y métodos y puede añadir nuevos atributos, métodos o redefinir los heredados.

#### Terminología:

- **Superclase:** La clase cuyas características se heredan se conoce como superclase (o una clase base o una clase principal).

- **Subclase:** La clase que hereda la otra clase se conoce como subclase (o una clase derivada, clase extendida o clase hija). La subclase puede agregar sus propios campos y métodos, además de los campos y métodos de la superclase.

- **Reutilización:** La herencia respalda el concepto de “reutilización”, es decir, cuando queremos crear una clase nueva y ya hay una clase que incluye parte del código que queremos, podemos derivar nuestra nueva clase de la clase existente. Al hacer esto, estamos reutilizando los campos/atributos y métodos de la clase existente.

```python
class SerVivo():
    def __init__(self, tipo, reino):
        self.tipo = tipo
        self.reino = reino
```


```python
class Persona:
    def __init__(self, cedula, nombre, apellido, sexo):
        self.cedula = cedula
        self.nombre = nombre
        self.apellido = apellido
        self.sexo = sexo

    def hablar(self, mensaje):
        return mensaje

    def getGenero(self, sexo):
        genero = ('Masculino','Femenino')
        if sexo == "M":
            return genero[0]
        elif sexo == "F":
            return genero[1]
        else:
            return "Desconocido"
```

```python
class Supervisor(Persona):

    def __init__(self, cedula, nombre, apellido, sexo, rol):
        Persona.__init__(self, cedula, nombre, apellido, sexo)
        self.rol = rol
        self.tareas = ['10','11','12','13']

    def consulta_tareas(self):
        return self.tareas
```


```python
Fulano = Supervisor(123,"Erick","Aguilar","M","supervisor de caja 1")
print(Fulano.consulta_tareas())
```

    ['10', '11', '12', '13']


Los casos de herencia múltiple en python se dan cuando una clase secundaria o hija hereda atributos y metodos de mas de una clase principal o padre. Basta con separar con una coma ambas principales a la hora de crear la clase secundaria:


```python
class Chalan(Persona,SerVivo):
    def __init__(self, cedula, nombre, apellido, sexo, rol,tipo,reino):
        Persona.__init__(self, cedula, nombre, apellido, sexo)
        SerVivo.__init__(self,tipo,reino)
        self.rol = rol
        self.tareas = ['Cargar bultos','Tirar losa',"Alinear"]
        
    def consulta_tareas(self):
        return self.tareas
```


```python
ElCarlangas = Chalan(1234,"Carlos","De Dios","M","Chalanazo","Humano","Animal")
```


```python
ElCarlangas.tipo
```




    'Humano'




```python
ElCarlangas.consulta_tareas()
```




    ['Cargar bultos', 'Tirar losa', 'Alinear']




```python
ElCarlangas.getGenero('M') ## Cómo arreglarían este error??
```




    'Masculino'
