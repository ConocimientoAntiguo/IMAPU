# Polimorfismo 

El polimorfismo es una relajación del sistema de tipos, de tal manera que una referencia a una clase (atributo, parámetro o declaración local o elemento de un vector) acepta direcciones de objetos de dicha clase y de sus clases derivadas (hijas, nietas, …).


Múltiples formas. Un león es a la vez un animal.

Tal como funcionan los lenguajes fuertemente tipados, una variable siempre deberá apuntar a un objeto de la clase que se indicó en el momento de su declaración



```python
class Persona():
    def __init__(self):
        self.cedula = 13765890
    def mensaje(self):
        print("mensaje desde la clase Persona")

class Obrero(Persona):
    def __init__(self):
        self.__especialista = 1
    def mensaje(self):
        print("mensaje desde la clase Obrero")

class Ingeniero(Persona):
    def __init__(self):
        self.__especialista = 2
    def mensaje(self):
        print("Mensaje desde la clase Ingeniero")

class Arquitecto(Persona):
    def __init__(self):
        self.__especialista = 3
    def mensaje(self):
        print("Mensaje desde la clase Arquitecto💅")

obrero_planta = Obrero()
ingeniero_fresa = Ingeniero()
arquitecto_pirruris = Arquitecto()

obrero_planta.mensaje()
ingeniero_fresa.mensaje()
arquitecto_pirruris.mensaje()

print("\n")

super(Arquitecto, arquitecto_pirruris).mensaje()
super(Ingeniero, ingeniero_fresa).mensaje()
super(Obrero, obrero_planta).mensaje()


```

    mensaje desde la clase Obrero
    Mensaje desde la clase Ingeniero
    Mensaje desde la clase Arquitecto💅
    
    
    mensaje desde la clase Persona
    mensaje desde la clase Persona
    mensaje desde la clase Persona



```python
class Perros(object): #Declaramos la clase principal Perros, todas heredan de la clase object
    def ladrar (self):
        print ("""GUAAAUU GUAAAUU!""")
    def grunir (self):
        print ("""GRRRRRR GRRRRR""")

class Caniche (Perros):#La clase secundaria hereda de la clase principal perros
    def ladrar(self):
        print ("""guau guau guau""")
        
    def grunir(self):
        print ("""gññññiii gñññiiii""")

class Pastor_Aleman(Perros):#La clase secundaria hereda de la clase principal perros
    def ladrar(self):
        print ("""GuaUUU GUAAAUUU GuaUUU""")
        
    def grunir(self):
        print ("Agrfgregreff aggrrfsgrrr")
 
    
class Shepadoodle (Caniche,Pastor_Aleman):#La clase hereda de las clases hijas de su padre Perros
    def ladrarx(self, veces):
        for cuantas in range(veces):
            super(Shepadoodle, self).ladrar()

Tommy = Pastor_Aleman()
Piny = Caniche()
Cuchele = Shepadoodle()
Cuchele.ladrarx(5)
```

    guau guau guau
    guau guau guau
    guau guau guau
    guau guau guau
    guau guau guau
