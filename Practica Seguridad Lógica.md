# Practica Seguridad Lógica

## Actividad 1 - Búsqueda de información

### Rainbowcrack

Rainbowcrack es un programa que genera rainbow tables para usarlas en el crackeo de contraseñas. Se difiere de otros programas de crackeo por fuerza bruta porque usa grandes tablas de desencriptación que reducen el tiempo necesario para crackear una contraseña de forma drástica 

Enlace descarga: http://project-rainbowcrack.com/

Manual de uso: https://www.youtube.com/watch?v=PmFcd--6_Dw


### Grub

GNU GRUB es un gestor de arranque, creado en 1995, capaz de arrancar diferentes tipos de sistemas operativos libres, así como sistemas operativos privativos, a través del arranque en cadena que luego se explica.

Enlace descarga: https://ftp.gnu.org/gnu/grub/

Manual de uso: https://www.gnu.org/software/grub/grub-documentation.html


### Libpam-cracklib

Libpam-cracklib es un módulo de configuración de políticas de contraseña que aumenta la seguridad frente a ataques de crackeo por fuerza bruta 	

Enlace descarga: apt-get install libpam-cracklib

Manual de uso: https://man7.org/linux/man-pages/man8/pam_cracklib.8.html


### Ultimate Boot CD

Ultimate Boot CD es un conjunto de herramientas para realizar pruebas y diagnósticos que se pueden grabar en un Live CD. Este disco se usa, sobre todo, para poder ejecutar pruebas en un ordenador cuyo sistema operativo estuviese dañado y no arrancase bien.

Enlace descarga: https://www.ultimatebootcd.com/download.html

Manual de uso: https://studylib.es/doc/710551/tutorial-de-uso--ultimate-boot-cd


### Ophcrack

Ophcrack es una herramienta para crackear las contraseñas de Windows basada en las tablas Rainbow. ​ Es una implementación muy eficiente de las tablas Rainbow hecha por los inventores de este método.

Enlace descarga: https://ophcrack.sourceforge.io/download.php

Manual de uso: https://joseconejos.wordpress.com/2018/06/10/como-recuperar-o-hackear-una-contrasena-con-ophcrack/


### Slax

Slax es una minidistribución y Live CD del sistema operativo GNU/Linux basado en la distribución Slackware y Debian. No necesita ser instalado, es capaz de arrancar y funcionar desde una unidad de CD, siendo innecesario el uso de un disco duro.

Enlace descarga: https://www.slax.org/?lang=es///en/download.php

Manual de uso: https://tecnopedia.net/linux/instalar-slax-linux-en-tu-pendrive/


### Wifiway - Wifislax

Wifislax es una distribución GNU/Linux en formato *. iso basada en Slackware con funcionalidades de LiveCD y LiveUSB pensada y diseñada para la auditoría de seguridad y relacionada con la seguridad informática en general.

Enlace descarga: https://www.wifislax.com/category/download/versiones-anteriores/

Manual de uso: https://www.wifislax.com/wp-content/uploads/2013/08/MANUAL-BASICO-WIFISLAX3.pdf


### Pwdump

Pwdump es el nombre de varios programas de windows que permiten extraer los hashes LM y NTLM de cuentas de usuario locales desde el fichero SAM. Debe ser ejecutado con permisos de administrador 

Enlace descarga: http://foofus.net/goons/fizzgig/pwdump/downloads.htm

Manual de uso: https://docs.bmc.com/docs/TSInfrastructure11304/pw-dump-937360450.html


### Cain & Abel

Cain & Abel (frecuentemente abreviado a Cain) es una herramienta de recuperación de contraseñas para Microsoft Windows. Puede recuperar muchos tipos de contraseñas utilizando métodos como el sniffing de paquetes de red, también puede crackear varios hashes de contraseñas utilizando métodos maliciosos como ataques de diccionario, de fuerza bruta y ataques basados en "criptoanálisis"

Enlace descarga: https://www.malavida.com/es/soft/cain-and-abel/

Manual de uso: https://dis.um.es/~lopezquesada/documentos/IES_1314/SAD/curso/UT4/ActividadesAlumnos/grupo2/documentos/Tutorial_Cain.pdf


### L0pht Crack

L0phtCrack es una herramienta de auditoría y recuperación de contraseñas (ahora llamada LC5), originalmente producida por Mudge de L0pht Heavy Industries. Es usada para verificar la debilidad de las contraseñas y algunas veces para recuperar las que se han olvidado o perdido en sistemas Microsoft Windows.

Enlace descarga: https://l0phtcrack.gitlab.io/

Manual de uso: https://www.youtube.com/watch?v=CzRqN8IQ-i0


### John the Ripper

John the Ripper es una herramienta para recuperación de contraseñas. Originalmente desarrollado para el sistema operativo Unix, puede funcionar en quince plataformas diferentes

Comando descarga: sudo apt-get install john

Manual de uso: https://www.fpgenred.es/Seguridad-Informatica-I/ms_sobre_john_the_ripper.html


### Windows Steady State

Windows SteadyState permite establecer Protección de disco de Windows para eliminar todos los cambios al reiniciar, para eliminar todos los cambios en una fecha y hora concretas, o para no eliminar los cambios.

Enlace descarga: https://www.microsoft.com/es-es/download/details.aspx?id=6692

Manual de uso: https://www.microsoft.com/es-es/download/details.aspx?id=22218


### Keepass Password Safe

KeePass es una herramienta que te ayuda a tener todas tus contraseñas seguras almacenadas en un mismo lugar sin necesidad de tener que memorizarlas todas. 

Enlace descarga: https://keepass.info/download.html

Manual de uso: https://www.youtube.com/watch?v=qpNlX2BcSh0


### DeepFreeze

Deep Freeze es un controlador del núcleo que protege la integridad del disco duro redirigiendo la información que se va a escribir en el disco duro o partición protegida, dejando la información original intacta. Las escrituras redirigidas desaparecen cuando el sistema es reiniciado, restaurando el equipo a su estado original.

Enlace descarga: https://www.faronics.com/es/downloads_es

Manual de uso: https://www.faronics.com/assets/DFS_Manual_S.pdf


## Actividad 2 - Configuración de Contraseñas Seguras en Windows y Linux

Realiza en Windows Server y el Ubuntu Server la configuración básica para el establecimiento de las directivas de complejidad de las contraseñas que se van a utilizar.

## Actividad 3- Ataques contra contraseñas en Sistemas Windows – FICHERO SAM -

El objetivo de la práctica es obtener las contraseñas de los usuarios del siguiente fichero hash y que puedes descargar dentro de los recursos de la unidad. 
(Utiliza rainbowcrack1.2-win)

## Actividad 4- Ataques contra contraseñas en Sistemas Windows

### Caso 1

Utilizar alguna de las herramientas indicadas en el tema para obtener las claves del fichero SAM de los usuarios de un S.O. Windows.

### Caso 2

Utilizar Kali (Exploits Herramienta MetaSploit en línea de comandos y Armitage GUI) para acceder al fichero SAM de un Windows. A continuación utilizando alguna de las aplicaciones que proporciona esta distribución para craquearlas.

### Caso 3

Resetea la clave de administración utilizando alguna de las distribuciones LIVE indicadas en el tema.

## Actividad 5.- Ataques contra contraseñas en Sistemas Linux

Utiliza BackTrack y John The Ripper para descubrir las contraseñas encriptadas de un equipo Ubuntu.

## Actividad 6.- Realiza un listado de este tipo de herramientas y analiza la instalación y configuración de 2 congeladores

## Actividad 7: GRUB.

a) Protege con contraseña el GRUB, para que no se pueda ejecutar secuencia de comandos, como root, en el arranque.

b) Protege contraseña el arranque de los sistemas operativos.

## Actividad 8: Servidor Radius. Autenticación en redes inalámbricas.

a) Instala y configura un servidor freeradius con soporte LDAP.

b) Protege con credenciales de usuario una red inalámbrica, creada con un router Mikrotik.
