# Integridad, firmas y autenticación

## Tarea 1: Firmas electrónicas (3 puntos)

En este primer apartado vamos a trabajar con las firmas electrónicas, para ello te pueden ayudar los siguientes enlaces:

* Intercambiar claves

* Validar otras claves en nuestro anillo de claves públicas

* Firmado de claves (Debian)

GPG

### 1. Manda un documento y la firma electrónica del mismo a un compañero. Verifica la firma que tu has recibido.

**Hecho en el pdf 2**

### 2. ¿Qué significa el mensaje que aparece en el momento de verificar la firma?

El mensaje que aparece significa que no confiamos en esa firma ni nosotros ni nuestro anillo de confianza ya que no se puede asegurar que la firma pertenezca a la persona que dice ser.

gpg: Firma correcta de "Pepe D <[josedom24@gmail.com](mailto:josedom24@gmail.com)>" [desconocido]
gpg: ATENCIÓN: ¡Esta clave no está certificada por una firma de confianza!
gpg: No hay indicios de que la firma pertenezca al propietario.
Huellas dactilares de la clave primaria: E8DD 5DA9 3B88 F08A DA1D 26BF 5141 3DDB 0C99 55FC

### 3. Vamos a crear un anillo de confianza entre los miembros de nuestra clase, para ello.

* Tu clave pública debe estar en un servidor de claves

Para subir la clave a un servidor de claves usamos el comando 

    gpg --keyserver keys.gnupg.net --send-key 0E0B264BA066FCCE0886256E911A401769998319

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/4fc07fca-7b20-442e-bf48-203c68801458)

* Escribe tu fingerprint en un papel y dárselo a tu compañero, para que puede descargarse tu clave pública.

* Te debes bajar al menos tres claves públicas de compañeros. Firma estas claves.

Para bajarme las claves públicas tenemos que usar el comando

    gpg --keyserver keys.gnupg.net --recv-keys D84DBF4EB85CEF1F95982F4E7D3A4870CB108806

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/a5eee933-354b-42bf-9a63-704871e14ed5)


Y para poder firmar y que confiemos en esas claves las hemos de firmar con el comando pero antes lo listaremos con el comando:

    gpg –list-keys

    gpg –sign-key 2E5DAE28ECBBBB37982214EB0CD06447118A7327 

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/f86dc81d-fabb-4e01-9230-73e3566b4e86)

Si volvemos a listar las claves podemos ver que ya sí que hay confianza cambiando  lo de que no es conocida “unknown” a “full”

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/b9782a5d-03cc-466e-aded-0d0e540fdf88)

Tu debes asegurar que tu clave pública es firmada por al menos tres compañeros de la clase.

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/7d32ecc4-2c83-476f-a8e7-5b355f38d254)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/c32afc18-902f-4eba-a318-d1e8ade0378c)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/20593a92-4e62-4937-af39-8d57f559e788)

* Una vez que firmes una clave se la tendrás que devolver a su dueño, para que otra persona se la firme.

* Cuando tengas las tres firmas sube la clave al servidor de claves y rellena tus datos en la tabla Claves públicas PGP 2020-2021

* Asegúrate que te vuelves a bajar las claves públicas de tus compañeros que tengan las tres firmas.

### 4. Muestra las firmas que tiene tu clave pública.

Para ver las firmas de mi clave pública usamos el comando

    gpg --list-sigs 0E0B264BA066FCCE0886256E911A401769998319

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/66123095-568f-43d8-993d-f0736606ba7c)

### 5. Comprueba que ya puedes verificar sin “problemas” una firma recibida por una persona en la que confías.

### 6. Comprueba que puedes verificar con confianza una firma de una persona en las que no confías, pero sin embargo si confía otra persona en la que tu tienes confianza total.


## Tarea 2: Correo seguro con evolution/thunderbird (2 puntos)

Ahora vamos a configurar nuestro cliente de correo electrónico para poder mandar
correos cifrados, para ello:

### 1. Configura el cliente de correo evolution con tu cuenta de correo habitual

Para configurar primero instalaremos el evolution

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/24b9fd0b-5b78-4670-b84a-82fb1cf4bb61)

Abrimos la aplicación Evolution y nos saldrá una página de bienvenida, le damos a "Next"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/acad85e0-804c-4626-a967-4e35a8580df7)

Ahora te pregunta si tienes algún backup para usar, le das a "Next"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/3e8262a7-0122-43e9-a5ad-efc6b54a77c1)

Ahora ingresamos nuestros datos, el nombre completo y un correo

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/9faead9c-003c-4742-a0d6-7ced363e9e19)

Ahora seleccionamos el tipo de servidor en mi caso lo pondré en "POP"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/7a28baf4-2f64-4338-8d5f-5a6e8d5ac732)

En las siguientes ventanas dejaremos todo por defecto

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/73ae79a3-3639-4be6-b2ae-b7b82f30a9cf)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/2375f012-9b96-4234-91ff-892cea59ca64)

Después te pone el resumen de la cuenta

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/3032d4b9-9f15-4aab-9f59-3132114f36f9)

Finalmente ya esta configurado bastará en darle a "Apply"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/a786c5ae-be2f-4cfa-87fc-f0304be652df)

Una vez aplicado te pedira la contraseña de la cuenta para poder acceder a los correos

### 2. Añade a la cuenta las opciones de seguridad para poder enviar correos firmados con tu clave privada o cifrar los mensajes para otros destinatarios

Para enviar correos firmados tenemos que modificar las preferencias por eso seguimos la siguiente ruta "Edit -> Preferences -> Composer Preferences -> Signatures -> Add"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/a9c44297-0116-44ec-b978-874e1551ab65)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/b54e3802-026b-47f2-bb40-d879cea32190)

### 3. Envía y recibe varios mensajes con tus compañeros y comprueba el funcionamiento adecuado de GPG

Para enviar un correo le damos a "New" y rellenamos con destinatario, asunto el correo en si y en el apartado "Signature" seleccionamos la firma que hemos ingresado antes en las preferencias

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/9e0901a0-263c-473d-a986-cb5894387159)

Luego hacemos la ruta "Desplegable -> Options -> PGP Encrypt" una vez ya nos aparezca un símbolo de un escudo verde podremos darle a "Send"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/c0400838-3128-47b2-ae09-dde57a287e42)


## Tarea 3: Integridad de ficheros (1 punto)

Vamos a descargarnos la ISO de debian, y posteriormente vamos a comprobar su
integridad.

Puedes encontrar la ISO en la dirección: https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/.

### 1. Para validar el contenido de la imagen CD, solo asegúrese de usar la herramienta apropiada para sumas de verificación. Para cada versión publicada existen archivos de suma de comprobación con algoritmos fuertes (SHA256 y SHA512); debería usar las herramientas sha256sum o sha512sum para trabajar con ellos.

Una vez descargadas la ISO ejecutamos un comando para ejecutar la suma de verificación

    sha512sum -c SHA512SUMS 2> /dev/null | grep netinst

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/1bfa0351-e782-4d72-897f-fe751a7869d1)


### 2. Verifica que el contenido del hash que has utilizado no ha sido manipulado, usando la firma digital que encontrarás en el repositorio. Puedes encontrar una guía para realizarlo en este artículo: How to verify an authenticity of downloaded Debian ISO images

Descargaremos las claves publicas de debian

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/8160d285-f7e4-49ed-9b6f-51fe67e4fcc1)

Verificamos las claves

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/04918a98-f605-45fe-8baf-746d894bd52d)

Comprobamos que ambos ficheros son iguales:

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/451fdd28-0ca4-4b77-bbe4-101b7e211a02)

Código de comprobación de la ISO de debian

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/88869136-d42d-4ac1-894b-a3e785c58c7d)

Código de comprobación de los ficheros SHA512SUMS y SHA256SUMS

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/13b32319-0dbe-4fab-9fa1-4959b17e72ca)


## Tarea 4: Integridad y autenticidad (apt secure) (2 puntos)

Cuando nos instalamos un paquete en nuestra distribución linux tenemos que asegurarnos que ese paquete es legítimo. Para conseguir este objetivo se utiliza criptografía asimétrica, y en el caso de Debian a este sistema se llama apt secure. Esto lo debemos tener en cuenta al utilizar los repositorios oficiales. Cuando añadamos nuevos repositorios tendremos que añadir las firmas necesarias para confiar en que los paquetes son legítimos y no han sido modificados.

Busca información sobre apt secure y responde las siguientes preguntas:

### 1. ¿Qué software utiliza apt secure para realizar la criptografía asimétrica?

Software de encriptación GPG (GNU Privacy Guard, gnupg.org, paquete gnupg) es un software de encriptación utilizado para cifrar y firmar documentos digitales, especialmente el correo, que utiliza criptografía híbrida: combina criptografía simétrica (por su rapidez), con criptografía asimétrica (por no necesitar compartir claves secretas). Sigue el estándar OpenPGP del IETF (Internet Engineering Task Force) y está integrado en numerosos programas como Secure-APT, Kmail, Evolution, Mozilla-Thunderbird, etc.

### 2. ¿Para que sirve el comando apt-key? ¿Qué muestra el comando apt-key list?

Sirve para gestionar la lista de claves que APT usa para autenticar paquetes. Los paquetes autenticados mediante estas claves se consideran de confianza. 

### 3- En que fichero se guarda el anillo de claves que guarda la herramienta apt-key?

El anillo de claves que gestiona apt-key se encuentra en /etc/apt/trusted.gpg.

### 4. ¿Qué contiene el archivo Release de un repositorio de paquetes?. ¿Y el archivo Release.gpg?. Puedes ver estos archivos en el repositorio http://ftp.debian.org/debian/dists/Debian10.1/. Estos archivos se descargan cuando hacemos un apt update.

Debian contiene un archivo llamado Release, el cual se actualiza cada vez que cualquiera de los paquetes en el archivo cambian. Entre otras cosas, el fichero Release contiene algunos md5sums por cada paquete listado en él. 

### 5. Explica el proceso por el cual el sistema nos asegura que los ficheros que estamos descargando son legítimos.

El sistema nos asegura que los ficheros que estamos descargando son legítimos mediante la verificación de la firma digital del fichero Release que se encuentra en el repositorio de paquetes.

### 6. Añade de forma correcta el repositorio de virtualbox añadiendo la clave pública de virtualbox como se indica en la documentación.

Primero añadimos esa linea al fichero

    echo "deb https://download.virtualbox.org/virtualbox/debian buster contrib" >> /etc/apt/sources.list

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/76c6c758-80a8-4246-a9e0-901be2a13af8)

Después ejecutamos los siguientes comandos

    wget -q https://www.virtualbox.org/download/oracle\_vbox\_2016.asc -O- | apt-key add -
    wget -q https://www.virtualbox.org/download/oracle\_vbox.asc -O- | apt-key add -

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/965a04dc-0f19-48b9-b233-02f33305a942)

Y ya instalaremos el paquete

    apt install virtualbox-6.1

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/5e94e2cd-fa66-4a26-a0fa-58f9580882ad)


## Tarea 5: Autentificación: ejemplo SSH (2 puntos)

Vamos a estudiar como la criptografía nos ayuda a cifrar las comunicaciones que hacemos utilizando el protocolo ssh, y cómo nos puede servir también para conseguir que un cliente se autentifique contra el servidor. Responde las siguientes cuestiones:

### 1. Explica los pasos que se producen entre el cliente y el servidor para que el protocolo cifre la información que se transmite? ¿Para qué se utiliza la criptografía simétrica? ¿Y la asimétrica?

Los pasos que se producen entre el cliente y el servidor para que el protocolo cifre la información que se transmite son los siguientes:

1. Se lleva a cabo un ‘handshake’ (apretón de manos) encriptado para que el cliente pueda verificar que se está comunicando con el servidor correcto

2. La capa de transporte de la conexión entre el cliente y la máquina remota es encriptada mediante un código simétrico

3. El cliente se autentica ante el servidor.

4. El cliente remoto interactúa con la máquina remota sobre la conexión encriptada.

La **criptografía simétrica** solo utiliza una clave para cifrar y descifrar el mensaje, que tiene que conocer el emisor y el receptor previamente y este es el punto débil del sistema, la comunicación de las claves entre ambos sujetos, ya que resulta más fácil interceptar una clave que se ha transmitido sin seguridad 

La **criptografía asimétrica** se basa en el uso de dos claves: la pública (que se podrá difundir sin ningún problema a todas las personas que necesiten mandarte algo cifrado) y la privada (que no debe de ser revelada nunca). 

### 2. Explica los dos métodos principales de autentificación: por contraseña y utilizando un par de claves públicas y privadas.

* Por contraseña: el cliente envía la contraseña al servidor para que este pueda autentificar al cliente.

* Por par de claves públicas y privadas: el cliente envía su clave pública al servidor para que este pueda autentificar al cliente. El cliente envía su clave privada al servidor para que este pueda autentificar al cliente.

### 3. En el cliente para que sirve el contenido que se guarda en el fichero ~/.ssh/know_hosts?

El contenido que se guarda en el fichero ~/.ssh/know_hosts sirve para que el cliente pueda autentificar al servidor.

### 4. ¿Qué significa este mensaje que aparece la primera vez que nos conectamos a un servidor?

$ ssh debian@172.22.200.74

The authenticity of host '172.22.200.74 (172.22.200.74)' can't be established.

ECDSA key fingerprint is SHA256:7ZoNZPCbQTnDso1meVSNoKszn38ZwUI4i6saebbfL4M.

Are you sure you want to continue connecting (yes/no)?


Implica que la conexión es nueva y que el cliente no tiene guardada la clave pública del servidor. Por lo tanto, el cliente no puede autentificar al servidor. El cliente pregunta al usuario si quiere continuar con la conexión.

Al escribir yes o aceptar la advertencia en la ventana emergente, se agregará entonces la clave a la lista hosts conocidos (archivo known_hosts).

### 5. En ocasiones cuando estamos trabajando en el cloud, y reutilizamos una ip flotante nos aparece este mensaje:

$ ssh debian@172.22.200.74

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

@ WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! @

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!

Someone could be eavesdropping on you right now (man-in-the-
middle attack)!

It is also possible that a host key has just been changed.

The fingerprint for the ECDSA key sent by the remote host is
SHA256:W05RrybmcnJxD3fbwJOgSNNWATkVftsQl7EzfeKJgNc.

Please contact your system administrator.

Add correct host key in /home/jose/.ssh/known_hosts to get rid of this message.

Offending ECDSA key in /home/jose/.ssh/known_hosts:103

remove with:

ssh-keygen -f "/home/jose/.ssh/known_hosts" -R "172.22.200.74"

ECDSA host key for 172.22.200.74 has changed and you have
requested strict checking.


Significa que la clave pública que teníamos asociada a esa dirección IP ha cambiado. Por lo tanto, el cliente no puede autentificar al servidor. Por lo que podría implicar que se está suplantando su identidad.

### 6. ¿Qué guardamos y para qué sirve el fichero en el servidor ~/.ssh/authorized_keys?

El archivo Authorized_keys en SSH especifica las claves SSH que se pueden usar para iniciar sesión en la cuenta de usuario para la que está configurado el archivo. Es un archivo de configuración muy importante, ya que configura el acceso permanente mediante claves SSH y necesita una gestión adecuada.
