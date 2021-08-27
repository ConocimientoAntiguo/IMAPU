# Empaquetamiento y compresión

El Empaquetamiento de Archivos se utiliza cuando uno o más archivos se tienen que transmitir o almacenar lo más eficientemente posible. Hay dos aspectos:

* El Empaquetamiento - Combina varios archivos en uno solo, lo que elimina la sobrecarga en archivos individuales y los hace más fácil de transmitir
* Compresión – hace los archivos más pequeños mediante la eliminación de información redundante

Comprimir los Archivos
Cuando se habla de compresión, existen dos tipos:

* Lossless (o «sin pérdida» en español): No se elimina ninguna información del archivo. Comprimir un archivo y descomprimirlo deja algo idéntico al original.
* Lossy (o «con pérdida» en español): Información podría ser retirada del archivo cuando se comprime para que al descomprimir el archivo de lugar a un archivo que es un poco diferente que el original. Por ejemplo, una imagen con dos tonos de verde sutilmente diferentes podría hacerse más pequeña por tratar esos dos tonos como uno. De todos modos, el ojo no puede reconocer la diferencia.

Linux proporciona varias herramientas para comprimir los archivos, la más común es gzip.
Lo contrario del comando gzip es el comando gunzip. Por otra parte, gzip –d hace la misma cosa (gunzip es sólo un script que invoca el comando gzip con los parámetros correctos).
Gzip puede también actuar como un filtro que no lee ni escribe nada en el disco sino recibe datos a través de un canal de entrada y los escribe a un canal de salida.
Hay otro par de comandos que operan prácticamente idénticamente al gzip y gunzip. Éstos son el bzip2 y bunzip2. Las utilidades del bzip utilizan un algoritmo de compresión diferente (llamado bloque de clasificación de Burrows-Wheeler frente a la codificación Lempel-Ziv que utiliza gzip) que puede comprimir los archivos más pequeños que un gzip a costa de más tiempo de CPU. Puedes reconocer estos archivos porque tienen una extensión .bz o .bz2 en vez de .gz.

Empaquetando Archivos
El empacamiento de archivos . La utilidad tradicional de UNIX para archivar los ficheros es la llamada tar, que es una abreviación de TApe aRchive (o «archivo de cinta» en español).
Tar toma varios archivos y crea un único archivo de salida que se puede dividir otra vez en los archivos originales en el otro extremo de la transmisión.
Tar tiene 3 modos que deberás conocer:

	• Crear: hacer un archivo nuevo de una serie de archivos
	• Extraer: sacar uno o más archivos de un archivo
	• Listar: mostrar el contenido del archivo sin extraer
  
La creación de un archivo requiere dos opciones de nombre. La primera, c, especifica el modo. La segunda, f, le dice a tar que espere un nombre de archivo como el siguiente argumento. 
Los tarballs pueden ser comprimidos para transporte más fácil, ya sea comprimiendo un archivo con gzip o diciéndole a tar que lo haga con la a opción z 
Mientras que UNIX no trata las extensiones de archivo especialmente, la convención es usar .tar para los archivos tar y .tar.gz o .tgz para los archivos tar comprimidos. Puedes utilizar bzip2 en vez de gzip sustituyendo la letra z con j y usando .tar.bz2,.tbz, o .tbz2 para una extensión de archivo
En el archivo tar, comprimido o no, puedes ver lo que hay dentro utilizando el comando t

	• t: listar documentos en el archivo en el archivo empaquetado
	• j: descomprimir con bzip2 antes de la lectura
	• f: operar en el nombre de archivo access_logs.tbz
	• Finalmente, puedes extraer el archivo con la marca –x
  
Tar se efectuará de manera recursiva hacia los subdirectorios automáticamente cuando comprime y almacenará la información de la ruta de acceso dentro del archivo.
Es importante mantener la opción –f al final, ya que el tar asume que lo que sigue es un nombre de archivo. 
El tar tiene muchas más funciones, como la capacidad de utilizar los patrones al extraer los archivos, excluir ciertos archivos o mostrar los archivos extraídos en la pantalla en lugar de un disco. 

## Archivos ZIP
Linux pero también es compatible con los comandos zip y unzip. Con el tar y gzip/gunzip se pueden utilizar los mismos comandos y las mismas opciones para hacer la creación y extracción
El modo predeterminado del zip es añadir documentos a un archivo y comprimir.
tar requiere la opción –f para indicar que se está pasando un nombre de archivo, mientras que el zip y unzip requiere un nombre de archivo, por lo tanto no tienes que decir explícitamente que se está pasando un nombre de archivo.
Zip no se efectuará de manera recursiva hacia los subdirectorios por defecto, lo que es un comportamiento diferente del tar.  debes utilizar el comando –r para indicar que se debe usar la recursividad
El listado de los archivos en el zip se realiza por el comando unzip y la opción –l (listar)

