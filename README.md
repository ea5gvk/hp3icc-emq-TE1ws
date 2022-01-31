# emq-TE1ws
![alt text](https://raw.githubusercontent.com/hp3icc/emq-TE1ws/main/emq-te1-rev12e.jpg)

hp3icc Proyecto Todo en uno , MMDVMHost ,Direwolf , Multimon-ng , Ionosphere , Dvswitch, YSFReflector , YSF2DMR , HBLink3 , FreeDMR , NoIP , Dashboard Websock

Dashboard html sobre websock , soporte GPSD , CM108 .

Continuamente todo el contenido publicado aqui, es actualizado , si esta observando atravez de un link compartido , dirijase al link principal :

https://github.com/hp3icc/emq-TE1ws

Ultima revision: emq-TE1ws-Rev15 30/1/2022 

#

El proyecto Todo en uno (emq-TE1ws), es una compilación que reúne aplicaciones de diferentes desarrolladores, enfocadas para uso de radioaficionados. Constante mente se trabaja en mejoras y actualizaciones, a medida que los desarrolladores de las aplicaciones incluidas lanzan nuevas versiones.
Todas las aplicaciones compiladas en esta imagen son 100% operativas, solo debe configurar sus parámetros e iniciar las aplicaciones que desee utilizar , según la capacidad y disponibilidad de su hardware .

Cualquier información sobre como configurar sus parámetros en las diferentes aplicaciones compiladas en esta imagen, debe dirigirse a los diferentes sitios de soporte de cada aplicación o desarrollador.

Especial agradecimiento al colega y amigo TI4OP Oscar , por sus aportes y revisiones de los scripts, para la creación del Bash de instalación de esta imagen.

#

Listado de aplicaciones de radioaficionados, que incluye la imagen y bash de instalación :

Direwolf 

Muntimon-NG 

Ionosphere

MMDVMHost

pYSFReflector 

YSF2DMR

Dvswitch 

FreeDMR

NoIP

GoTTY

WiFi-AP -opcional version AP

Esta versión cuenta con Dashboard HTML corriendo sobre websock , para el MMDVMHost y Reflector YSF , estan preconfigurados a puerto http 80 , pero desde el menú puede cambiar al puerto 8000, 8080 , o cualquier otro de su preferencia .

se agrega Librerias y aplicacion de gps y GPSD

Se agrega lista mundial de nombres de TG de la red DMR brandmeister .

Se agrega listado de nombres de salas del Proyecto Treehouse EUROPELINK según el DG-ID correspondiente .


Compatible con Raspberry pi : zero , P2 , P3 y P4

#


#

# Instalación desde terminal:

Puede instalar en su sistema operativo (Ubuntu , raspberry , Debian ) utilizando el Bash de auto instalación desde su consola terminal con permisos de super usuario, importante su sistema operativo debe tener instalado sudo y wget  antes de utilizar el Bash de auto instalación .

* Pre-requisitos :
 
 curl
 
* Bash de auto instalación :

 Proyecto emq-TE1 con accespoint WiFi
 
      sh -c "$(curl -fsSL https://github.com/hp3icc/emq-TE1ws/raw/main/emq-TE1x-AP.sh)"
      

 Proyecto emq-TE1 sin accespoint WiFi - recomendado para vps o equipos de escritorio de una sola coneccion a internet
 
      sh -c "$(curl -fsSL https://github.com/hp3icc/emq-TE1ws/raw/main/emq-TE1x.sh)"


#

# Instalación en memoria micro sd para Raspberry:

si posee equipo raspbery , puede descargar y utilizar la imagen preconfigurada  lista para cargar en su memoria micro sd , para esto solo deberá descargar el archivo de la imagen preconfigurada para raspberry, descomprimir el archivo .zip y cargar en su memoria micro sd utilizando herramientas como BalenaEtcher , Rufus o cualquier otra herramienta para cargar el archivo .img a la memoria micro sd.

 Puede descargar la imagen para raspberry desde cualquiera de los siguientes links:
 
 Imagen para raspberry, proyecto emq-TE1 con accespoint WiFi, recomendado para Raspberry Zero W, Zero2 W, B3, B3+, PI4
 
* https://mega.nz/file/cF8GSaoY#tEpkklOpP_a2WK7I8PhBt7-ImCmrOFUobZzNIA8uhUo


Imagen para raspberry, proyecto emq-TE1 sin accespoint WiFi - recomendado para Raspberry Zero, Zero-W, Zero2, Zero2 W  B2, B3, B3+, PI4

* https://mega.nz/file/IRlWVIxb#ZTiIE4CmMnep37N-YhjW3eCTIINKuKrzMgayPXViWtc

#

# Configuración

Puede configurar desde consola terminal, aplicación cliente ssh o utilizar su navegador Web puerto 8022, ingresando al ip local de su raspberry o hostname.

Ejemplo: 

* 10.0.0.1:8022/  

* emq-te1:8022/ 

Usuario:    pi

Contraseña:  Panama507

si esta configurando desde terminal o clliente ssh, una vez allá iniciado sesión , escriba la palabra:   menu 

De esta forma accederá al listado de aplicaciones incluidas en la compilación y sus configuraciones, recuerde guardar los cambios con la combinación de teclas:     Ctrl + X , posteriormente iniciar o detener la aplicación ya configurada .

A partir de version 12d , se agrega funcion de reinicio automatico del equipo , esto es posible mendiamte prueba de ping al internet cada 1 minuto, esta fumcion esta apagada , si desea utilizar , entre al menu de reinicio de equipo y habilite  

Si desea habilitar más de un Dashboard a la vez, recuerde cambiar los puertos http para evitar conflictos, para esto se incluye dicha opción en el menú de :

* pYSFReflector  
* MMDVMHost
* Dvswitch
* FreeDMR

# Nota importante 

* Si utiliza la imagen pre-compilada para Raspberry , recuerde cambiar la contraseña por una de su preferencia . 

* Si usted utiliza emq-TE1wsRev8 a la version emq-TE1-ws-Rev10b , y utiliza dashboard de YSFReflector simultaneamente con MMDVMHost , debe corregir los puertos websock de los dashboard de YSFReflector y MMDVMHost, para esto solo debe utilizar la herramienta de correccion para las revisiones 8 a 10b

wget https://github.com/hp3icc/emq-TE1ws/raw/main/rev8WS-to-rev10b-fix-websosk-conflict.sh

sh rev8WS-to-rev10b-fix-websosk-conflict.sh

* La nueva version emq-TE1-Rev10c o posteriores , NO requiere esta correccion 

#
# WIFI 

Si su equipo cuenta con dispositivo de red inalámbrica (WIFI) o es modelo Raspberry Zero W , después de haber grabado la imagen en la memoria microSD con la herramienta Rufus , Balena u otra aplicación , debe descargar y copiar el archivo wpa_supplicant.conf, a la partición con el nombre boot en su memoria microSD.
Puede descargar el archivo wpa_supplicant.conf del siguiente link:

https://drive.google.com/file/d/1uFjl1BbzPBdRQ9g7LTMr3bB1FAgP5ILB/view?usp=sharing

Este archivo puede ser editado con el Notepad y dentro de este archivo, debe incluir los nombres de redes wifi y contraseñas de cada una, a las que desea que su raspberry se conecte, puede agregar una o cuantas redes wifi tenga, para que su equipo se conecte.

#

# WiFi-AP

Ahora el proyecto emq-TE1ws , incluye la funcion de modo ap a nuestro equipo, esta funcion nos permite utilizar nuestro mini computador Raspberry como un reuter WiFi o si tenemos un hotspot o aprs sobre raspberry zero W, nos facilita la conexion a nuestro equipo , para agregar una nueva coneccion a redes wifi conocidas .

La funcion de de WiFi-AP puede ser apagada o encendida en el menu wifi

Para conectarse a su equipo, selecciones la red wifi con el nombre:

emq-TE1-AP

contraseña para su coneccion wifi:

Panama507

Para cambiar el nombre y la contraseña de su WiFi-AP , entre al menu editar wifi , luego en editar AP WiFi, y reemplace el nombre actual en la linea ssid= :

ssid=HP3ICC-1HS

la contraseña debe ingresarla en formato hexadecimal, reemplasando la actual que esta en la linea  wpa_psk= :

wpa_psk=cdfce0488f50bac6d77d911e44b33d5c9c7652dc7c7f81c6489bac8a683e04a1

Para generar su contraseña correctamente en formato hexadecimal, es el calculo entre el ssid y su contraseña alfanumerica, puede utilizar el siguiente link, ingresando sus datos y luego dar click en generar :

http://jorisvr.nl/wpapsk.html


* Nota:

  si su equipo es un vps , servidor fijo , mini pc o solo utiliza las mismas conecciones de internet , se recomienda la version de emq-TE1 sin WiFi-AP .

#

Exitos en sus proyectos con raspberry 

HP3ICC

Esteban Mackay Q.

73.

#

# emq-TE1ws
![alt text](https://raw.githubusercontent.com/hp3icc/emq-TE1ws/main/emq-te1-rev12e.jpg)

 hp3icc All-in-one Project, MMDVMHost, Direwolf, Multimon-ng, Ionosphere, Dvswitch, YSFReflector, YSF2DMR, HBLink3, NoIP, Dashboard Websock

 Html dashboard over websock, GPSD support, CM108.

 Continuously all the content published here is updated, if you are looking through a shared link, go to the main link:
 
 https://github.com/hp3icc/emq-TE1ws
 
 Last revision: emq-TE1ws-Rev15 1/30/2022 

#

The All-in-one project (emq-TE1ws), is a compilation that brings together applications from different developers, focused on the use of radio amateurs. Improvements and updates are constantly being worked on, as the developers of the included applications release new versions.

All the applications compiled in this image are 100% operational, you just have to configure their parameters and start the applications you want to use, according to the capacity and availability of your hardware.

Any information on how to configure its parameters in the different applications compiled in this image should be directed to the different support sites of each application or developer.

Special thanks to the colleague and friend TI4OP Oscar, for his contributions and reviews of the scripts, for the creation of the installation Bash of this image.

#

List of amateur radio applications, including image and installation attempt:

 Direwolf 

Muntimon-NG 

Ionosphere

MMDVMHost

pYSFReflector 

YSF2DMR

Dvswitch 

FreeDMR

NoIP

GoTTY

WiFi-AP - optional AP version
 
 
 This version has HTML Dashboard running on websock, for the MMDVMHost and YSF Reflector, they are preconfigured to http port 80, but from the menu you can change to port 8000, 8080, or any other of your preference.

 Libraries and gps and GPSD application is added

 Added worldwide list of TG names from DMR brandmeister network.

 A list of room names of the Treehouse EUROPELINK Project is added according to the corresponding DG-ID.

 Raspberry pi compatible: zero, P2, P3 and P4

 #

# Installation from terminal:

You can install on your operating system (Ubuntu, raspberry, Debian) using the self-install Bash from your terminal console with super user permissions, importantly your operating system must have sudo and wget installed before using the self-install Bash. 

* Prerequisites:
 
 curl

* Self-install bash:

 Emq-TE1 project with WiFi access point

      sh -c "$(curl -fsSL https://github.com/hp3icc/emq-TE1ws/raw/main/emq-TE1x-AP.sh)"

 Emq-TE1 project without WiFi access point - recommended for vps
 
      sh -c "$(curl -fsSL https://github.com/hp3icc/emq-TE1ws/raw/main/emq-TE1x.sh)"


#

# Installation in micro sd memory for Raspberry:

 If you have raspbery equipment, you can download and use the preconfigured image ready to load into your micro sd memory, for this you just need to download the preconfigured image file for raspberry, unzip the .zip file and load it into your micro sd memory using tools such as BalenaEtcher, Rufus or any other tool to load the .img file to the micro sd memory.

  You can download the raspberry image from any of the following links:


  Image for raspberry, emq-TE1 project with WiFi accespoint, recommended for Raspberry Zero W, Zero2 W, B3, B3+, PI4

 * https://mega.nz/file/cF8GSaoY#tEpkklOpP_a2WK7I8PhBt7-ImCmrOFUobZzNIA8uhUo


 Image for raspberry, emq-TE1 project without WiFi access point - recommended for Raspberry Zero, Zero W, Zero2, Zero2 W, Zero-2,  B2, B3, B3+, PI4

 * https://mega.nz/file/IRlWVIxb#ZTiIE4CmMnep37N-YhjW3eCTIINKuKrzMgayPXViWtc

 #

 # Setting

 You can configure from terminal console, ssh client application or use your Web browser port 8022, entering the local ip of your raspberry or hostname.

 Example: 

 * 10.0.0.1:8022/  

 * emq-te1: 8022 / 

 User: pi

 Password: Panama507


If you are configuring from terminal or ssh client, once logged in, write the word: menu

In this way you will access the list of applications included in the compilation and their configurations, remember to save the changes with the key combination: Ctrl + X, then start or stop the already configured application.

As of version 12d, the automatic restart function of the equipment is added, this is possible by means of a ping test to the internet every 1 minute, this function is off, if you want to use, enter the equipment restart menu and enable

If you want to enable more than one Dashboard at the same time, remember to change the ports to avoid conflicts, for this this option is included in the menu of :

* pYSFReflector  
* MMDVMHost
* Dvswitch
* FreeDMR

 # Important note
 
 * If you use the pre-compiled image for Raspberry, remember to change the password to one of your preference.

 * If you use emq-TE1wsRev8 to version emq-TE1-ws-Rev10b, and use the YSFReflector dashboard simultaneously with MMDVMHost, you must correct the websock ports of the YSFReflector and MMDVMHost dashboards, for this you should only use the correction tool for the revisions 8 to 10b

wget https://github.com/hp3icc/emq-TE1ws/raw/main/rev8WS-to-rev10b-fix-websosk-conflict.sh

sh rev8WS-to-rev10b-fix-websosk-conflict.sh

 * The new version emq-TE1-Rev10c or later, does NOT require this correction

#

 # WIFI 

If your computer has a wireless network device (WIFI) or is a Raspberry Zero W model, after having recorded the image in the microSD memory with the Rufus, Balena or other application, you must download and copy the wpa_supplicant.conf file, to the partition named boot on your microSD memory.

 You can download the wpa_supplicant.conf file from the following link:

 https://drive.google.com/file/d/1uFjl1BbzPBdRQ9g7LTMr3bB1FAgP5ILB/view?usp=sharing

 This file can be edited with the Notepad and within this file, you must include the names of Wi-Fi networks and passwords of each one, to which you want your raspberry to connect, you can add one or how many Wi-Fi networks you have, so that your equipment connect.

 #
 
 # WiFi-AP

 Now the emq-TE1ws project includes the function of ap mode to our equipment, this function allows us to use our Raspberry mini computer as a WiFi reuter or if we have a hotspot or aprs on raspberry zero W, it facilitates the connection to our equipment, to add a new connection to known Wi-Fi networks.

 The WiFi-AP function can be turned on or off in the Wi-Fi menu.

 To connect to your computer, select the Wi-Fi network with the name:

 emq-TE1-AP

 password for your wifi connection:

 Panama507

 To change the name and password of your WiFi-AP, enter the edit wifi menu, then edit WiFi AP, and replace the current name in the line ssid =:

 ssid = HP3ICC-1HS

 The password must be entered in hexadecimal format, replacing the current one that is in the wpa_psk = line:

 wpa_psk = cdfce0488f50bac6d77d911e44b33d5c9c7652dc7c7f81c6489bac8a683e04a1

 To generate your password correctly in hexadecimal format, it is the calculation between the ssid and your alphanumeric password, you can use the following link, entering your data and then click on generate:

 http://jorisvr.nl/wpapsk.html

 * Note:

   If your equipment is a vps, fixed server, mini pc or only uses the same internet connections, the emq-TE1 version without WiFi-AP is recommended.

 #



 Successes in your projects with raspberry 

 HP3ICC
 
 Esteban Mackay Q.
 
 73.
#
