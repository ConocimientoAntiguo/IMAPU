Software (llamados controladores («drivers» en inglés) o módulos) que les permite comunicarse con el sistema operativo instalado. 

Puedes ver a qué familia pertenece tu CPU usando el comando arch
Otro comando que puedes utilizar para identificar el tipo de CPU en el sistema es el comando lscpu:
La manera más detallada de obtener la información acerca de tu CPU es visualizando el archivo /proc/cpuinfo con el comando cat
 Los flags de una CPU son un componentes muy importantes, ya que señalan qué características soporta la CPU y las capacidades de la CPU.

La tarjeta madre de muchas computadoras contiene lo que se conoce como Basic Input and Output System (BIOS) (o «BIOS de Administración del Sistema» en español). System Management BIOS (SMBIOS) (o «El Sistema de Gestión o Administración de BIOS» en español) es el estándar que define las estructuras de datos y cómo se comunica la información acerca del hardware de la computadora. El comando dmidecode es capaz de leer y mostrar la información del SMBIOS.

Para evitar que el sistema falle por falta de RAM, se utiliza una RAM virtual (o espacio de intercambio «swap space» en inglés). La RAM virtual es un espacio en el disco duro que se utiliza para almacenar temporalmente los datos de RAM cuando el sistema se está quedando sin la RAM.

Para ver la cantidad de la RAM en tu sistema, incluyendo la RAM virtual, ejecuta el comando free. El comando free tiene la opción -m para forzar la salida a ser redondeada al megabyte más cercano y una opción -g para forzar la salida a ser redondeada al gigabyte más cercano

Para ver todos los dispositivos conectados por un bus PCI ejecuta el comando lspci.
La salida del comando lspci puede ser muy importante para identificar los dispositivos que no son compatibles con el kernel Linux. Algunos dispositivos como las tarjetas de vídeo sólo pueden proporcionar una funcionalidad básica sin necesidad de instalar software de controlador propietario.

Para mostrar los dispositivos conectados al sistema vía USB, ejecuta el comando lsusb

Utiliza el comando lsmod para ver los módulos cargados actualmente:

La Capa de Abstracción de Hardware
HAL o «Hardware Abstraction Layer» en inglés, es la Capa de Abstracción de Hardware. El demonio o programa vigilante (o «daemon» en inglés) de la HAL es hald, un proceso que recoge información sobre todos los dispositivos conectados al sistema. Cuando se producen eventos que cambian el estado de los dispositivos conectados, tales como un dispositivo USB es conectado al sistema, el hald emite esta nueva información a los procesos que se hayan registrado para ser notificados sobre nuevos eventos.
El comando lshal te permite ver los dispositivos detectados por HAL.

Los discos duros se dividen en particiones. Una partición es una división lógica de un disco duro, diseñada para tomar una gran cantidad de espacio de almacenamiento disponible y dividirlo en «trozos» más pequeños.

Los comandos fdisk, cfdisk y sfdisk son herramientas para trabajar con las particiones discos MBR.
Las herramientas para gestionar los discos GPT se llaman de manera similar a las contrapartes de fdisk: gdisk, cgdisk y sgdisk.

Las unidades de disco duro están asociadas a los nombres de archivos (llamados archivos de dispositivo) que se almacenan en el directorio /dev. Diferentes tipos de unidades de disco duros reciben nombres ligeramente diferentes: hd para los discos duros IDE (Intelligent Drive Electronics o «Unidad Electrónica Inteligente» en español) y sd para USB, SATA (Serial Advanced Technology Attachment o «Aditamento de Tecnología Serial Avanzada» en español) y los discos duros SCSI (Small Computer System Interface o «Interfaz Estándar de Equipos Pequeños» en español).

Las distribuciones modernas a menudo montan los discos bajo la carpeta /media, mientras que las distribuciones antiguas suelen montarlos en la carpeta /mnt.

Gestionar los Dispositivos
Para poder utilizar un dispositivo en Linux puede haber varios tipos de software que se requieren. El primero es el software de driver. El driver puede compilarse como parte del kernel de Linux, cargado al kernel como un módulo o cargado por un comando de usuario o una aplicación.

