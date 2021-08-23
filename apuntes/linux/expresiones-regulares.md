# Expresiones Regulares

Las expresiones regulares, también conocidas como **regex**, o **regexp** (por su nombre en inglés, *regular expressions*) son secuencias de caracteres que forman un patrón de búsqueda (Es decir sirven para buscar).

*El término expresión regular surgió en el contexto histórico de la informática durante el desarrollo posterior a la Segunda Guerra Mundial de la teoría de autómatas, una subdisciplina de la informática que investiga y desarrolla modos matemáticos de computación, gracias a está disciplina tenemos **compiladores**.*

_Las expresiones regulares son sensitiveCase, es decir, distinguen entre mayúsculas y minúsculas_.

**TOKEN** :  Compomene de una cadena de caracteres que tiene cierto significado por si solo.

## Herramientas para usar expresiones regulares en Linux

* grep y derivados (egrep ,fgrep, ...)
* awk (Es un lenguaje de programación)
* sed

La mayoría de los lenguajes de programación soportan expresiones regulares.

## Herramientas para usar expresiones regulares en Windows 

* PowerGrep
* EditPad Pro

## Caracteres especiales para expresiones regulares

| Caracter especial  | Significa o representa                                  |
| -----------------  | ------------------------------------------------------- |
| \ t                | Tabulador.                                              |
| \ r                | Retorno de carro (también conocido como "enter").       |
| \ n                | Nueva línea.                                            |
| \ f                | Un salto de página.                                     |
| \ d                | Un dígito del 0 al 9.                                   |
| \ D                | Cualquier caracter que **NO** sea un dígito del 0 al 9. |
| \ w                | Cualquier caracter  alfanúmerico.                       |
| \ W                | Cualquier caracter que **NO** sea alfanúmerico.         |
| \ s                | Un espacio en blanco.                                   |
| \ S                | Cualquier caracter que **NO** sea un espacio en blanco. |
| \ A                | Inicio de cadena (No es un caracter sino una posición). |
| \ Z                | Final de cadena (No es un caracter sino una posición).  |

Atención, la herramienta (grep y sus derivados, egrep, fgrep) no soporta los metacaracteres de la tabla de arriba, por lo cual no es recomendable usarlos, empero, es posible usarlos a través de la bandera **-p** que le indica a *grep* que estamos accediendo al soporte del *Perl* (un lenguaje de programación). La sintaxis para lo anterior sería:

`grep -P '\d' archivo1`

## ¿Cómo usar grep o egrep?

| Nombre del comando | caracteres a buscar o expresión regular | Nombre del archivo donde se desea buscar |
| ------------------ | --------------------------------------- | ---------------------------------------- |
| gre \| egrep       | "GNU"                                   | archivo1                                 |



## Patrones simples

Si se desea buscar un conjunto de caracteres en particulas (un palabra) entonces simplemente podemos escribir lo siguiente:

`grep "ever" archivo1`

Esto significa" buscar una **e** seguida de una **v**, seguida de una **e**, seguida de una **r**" 

## Wildcards (comodines)

### El punto "."

Es un metacaracter que se interpreta como cualquier caracter SIN incluir los saltos de línea.

Ejemplos

`egrep T.m`

### El signo de admiración "!"

Se utiliza para realizar una "búsqueda anticipada negativa".

Ejemplos

Los ejemplos para este caracter van necesariamente en conjunto con otros, es decir, no se usa solo.

### El acento circunflejo "^"

Tiene una doble funcionalidad. 

Como caracter individual su función es representar el inicio de la cadena.

Si se utiliza en conjunto con otros simbolos entonces representará una negación.

Ejemplos

`egrep '^P' texto` 

### El signo de dólar "$"

Representa el final de la cadena de caracteres o el final de la línea. **NO** representa un carácter en especial sino una posición.

Ejemplos

`egrep 'to$' texto `

### La barra (pipe) "|"

Sirve para indicar una de varias opciones. Por ejemplo, la expresión regular "a|e" encontrará cualquier "a" o "e" dentro del texto.

`egrep 'T(o|O)m' texto `

`egrep 'Debian|Ubuntu' regex`

### Los corchetes "[ ]"

Los corchetes tienes dos funciones.

La primera función es que actuán de manera similar a la barra ( "|" ) si dentro de ellos hay una simple secuencia de caracteres.

Su segunda función es definir rangos mediante el signo de guión "-" a esto se le conoce como *grupos o clases de caracteres* 

`egrep '[0-9]' texto `

### Los paréntesis "( )"

Los parentesis se utilizan para agrupar multiplés tokens, estos caracteres permiten combinar tokens con más caracteres de las expresiones regulares, creando así filtros cada vez más específicos.

Ejemplos

`egrep '(este|oeste|norte|sur)' texto`

## Caracteres de cuántificación

### El signo de interrogación "?"

Su función es definir que el caracter que le precede es opcional, es decir, puede o no estar en los resultados de la búsqueda.

Ejemplos

`egrep 'Tom?y' texto`

`grep -E 'https?' texto2`

### El asterisco "*"

El asterisco sirve para encontrar algo que se encuentra repetido *0 o más veces.*

Ejemplo

`egrep 'T*y' texto`

`cp * ../otroDirectorio`

### El signo de suma "+"

Se utiliza para encontrar una cadena que se encuentre repetida *una o más veces.*

Ejemplo

`egrep '[0-9]+' texto `

`grep -E ':[0-9]+' texto2`

### Las llaves "{ }"

Estos caracteres son similares al "*" y al "+", pero permiten establecer un rango más preciso, pro ejemplo que un token se encuentre seguido de dos "c" abc{2} o queun token se encuentre seguido por más de dos "c" abc{2,} o que el token se encuentre seguido de 2  a 5 "c" abc{2,5}

Ejemplo

`egrep 'abc{2}' texto `


## Más ejemplos

#### Encontrar el patrón que tenga la palabra lines seguido de cualquier caracter 

`grep "lines.*empty" demo_file`

#### Encontrar las líneas que tienen que ver con las fechas que van del 2002 al 2004

`grep '200[2-4]' texto2`

#### Encontrar las líneas que tienen que ver con las fechas con el 2002 y el 2008

`grep '200[24]' texto2`

#### Encontrar dos puntos ('':'') y que seguido de ellos **NO** vaya una diagonal 

`egrep ':[^/]' texto2`

#### Encontrar todos los números de 4 cifras

`grep -E '[0-9]{4}' texto2`

`egrep '[a-z]{3,6}' texto2` vs `grep '\<[a-z]{3,6}\>' texto2`

#### Encontrando fechas

`egrep '[0-9]{2}[-/*][0-9][0-9][-/*][0-9]{4}' texto2`

`egrep '[0-9]{2}[-/*][0-9][0-9][^a-zA-Z0-9][0-9]{4}' texto2`

### Concatenando filtros

`ls -a | egrep '.*[aeiou]$' | egrep '^\.'`

` ls -a | egrep '.*[aeiou]$' | egrep '^\.' | sort -r | head -4`
