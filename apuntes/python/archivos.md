# Archivos 

Python incorpora un tipo integrado llamado file, el cual es manipulado mediante un objeto archivo el cual fue generado a través de una función integrada.

La biblioteca OS nos permite manipular archivos del sistema operativo. Como eliminarlos, moverlos y otras cosas que podríamos hacer desde shell.


```python
#Listar el contenidos de una carpeta
import os
print("Contenido de la carpeta:",os.listdir("./"))

#Mostrar el actual directorio de trabajo
print("Directorio actual:",os.getcwd())

#Mostrar el tamaño del archivo en bytes del archivo pasado en parámetro

print("Este documento pesa en bytes:",os.path.getsize("El lenguaje de programación Python - Básico.ipynb"))

#Para renombrar un archivo
# os.rename("Ana_Poleo","Ana_Carolina")

```

    Contenido de la carpeta: ['.DS_Store', 'El lenguaje de programación Python - Básico.ipynb', 'img', '.gitignore', '.ipynb_checkpoints']
    Directorio actual: /Users/samuelarturogarridosanchez/Desktop/Proteco/Python2020-2/Teoría/Básico
    Este documento pesa en bytes: 123819


### Manipulación de archivos y su contenido


```python
import os

print("Creación de un archivo")

nombre = 'ejemplo.txt'

archivo = open(nombre, 'w') # abre el archivo datos.txt en formato w de escritura
archivo.write('Prueba para ver si se escribe en el archivo.\nY otra línea\nY otra') ## String que se escribe
archivo.close() ## Cerramos el puntero

## Determinar si el archivo fue creado o no
if nombre in os.listdir("."):
    print("\nArchivo creado en la ruta:"+os.getcwd()+"/"+nombre)
else:
    print("No se encontró al archivo")

print("\nLectura de archivo")

archivo = open(nombre, 'r') ## Se apertura el archivo en formato de lectura
contenido = archivo.read() ## Leemos
print(contenido) # Imprimimos el contenido
archivo.close() ## Cerramos el puntero


print("\nImprimir línea por línea")

archivo = open(nombre, 'r') ## Se apertura el archivo en formato de lectura
for linea in archivo: ## Tiene un iterador interno para recorrer línea por línea
    print("Línea: ",linea)
print("\n")
archivo.close() # Cerramos el puntero


print("Eliminar un archivo")

#os.remove(os.getcwd()+"/"+NOMBRE_ARCHIVO)
```

    Creación de un archivo
    
    Archivo creado en la ruta:/Users/samuelarturogarridosanchez/Desktop/Proteco/Python2020-2/Teoría/Básico/ejemplo.txt
    
    Lectura de archivo
    Prueba para ver si se escribe en el archivo.
    Y otra línea
    Y otra
    
    Imprimir línea por línea
    Línea:  Prueba para ver si se escribe en el archivo.
    
    Línea:  Y otra línea
    
    Línea:  Y otra
    
    
    Eliminar un archivo
