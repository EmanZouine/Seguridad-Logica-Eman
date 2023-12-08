# Cifrado asimétrico con gpg

En esta práctica vamos a cifrar ficheros utilizando cifrado asimétrico utilizando el programa gpg. Puedes encontrar el resumen de comando en esta chuleta o buscar información en internet.

## Tarea 1: Generación de claves (1 punto)

Los algoritmos de cifrado asimétrico utilizan dos claves para el cifrado y descifrado de mensajes. Cada persona involucrada (receptor y emisor) debe disponer, por tanto, de una pareja de claves pública y privada. Para generar nuestra pareja de claves con gpg utilizamos la opción --gen-key:

Para esta práctica no es necesario que indiquemos frase de paso en la generación de las claves (al menos para la clave pública).

### 1. Genera un par de claves (pública y privada). ¿En que directorio se guarda las claves de un usuario?

Para crear las claves publica y privada usamos el comando

    gpg --gen-key

Luego te preguntará el nombre completo y un correo electrónico, cuando los introduzcamos saltará una ventana preguntando por una contraseña

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/899ed685-4741-47c9-9984-fa615b62617f)

Una vez introducida la contraseña saltará otra ventana donde te dira que el nivel de la contraseña es muy bajo porque mi contraseña es "usuario"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/83586762-35fb-4b63-8e68-cb84be056844)

Una vez creadas las claves tendrá que verse así y ademas se guardan en el directorio .gnupg/

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/9e59a3b3-a02b-4822-aaa1-568bb9e5862d)


### 2. Lista las claves públicas que tienes en tu almacén de claves. Explica los distintos datos que nos muestra. ¿Cómo deberías haber generado las claves para indicar, por ejemplo, que tenga un 1 mes de validez?

Para ver las claves públicas que tengo en mi almacén usamos el comando

    gpg --list-keys

Nos mostrará varias cosas entre ellas información sobre el día de creación de la clave pública y su fecha de caducidad, el uuid, las credenciales y la fecha de creación y validez. Además de el nombre de la persona y su correo

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/97b16f3f-8973-429b-8126-71f874dc804e)

Para indicar que las claves tengan una determinada validez, tenemos que haber usado el siguiente comando, aunque este te pregunta antes varias cosas, sobre que tipo de llave quieres y el tamaño, luego de eso ya te pregunta cuando quieres que expire en este caso como es un ejemplo he puesto 1m que sería el equivalente a un mes

    gpg --full-gen-key

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/1ac94236-69df-45a1-904e-4299a3085a70)


### 3. Lista las claves privadas de tu almacén de claves.

Para listar las claves privadas usamos el comando

    gpg --list-secret-keys

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/c29a2fd6-6b2f-4a1b-adb9-40c8fdd81b16)


## Tarea 2: Importar / exportar clave pública (1 punto)

Para enviar archivos cifrados a otras personas, necesitamos disponer de sus claves públicas. De la misma manera, si queremos que cierta persona pueda enviarnos datos cifrados, ésta necesita conocer nuestra clave pública. Para ello, podemos hacérsela llegar por email por ejemplo. Cuando recibamos una clave pública de otra persona, ésta deberemos incluirla en nuestro keyring o anillo de claves, que es el lugar donde se almacenan todas las claves públicas de las que disponemos.

### 1. Exporta tu clave pública en formato ASCII y guardalo en un archivo nombre_apellido.asc y envíalo al compañero con el que vas a hacer esta práctica.

Para exportar la clave publica hacemos uso del comando

    gpg --export -a "Eman Zouine Es-Sakhi" >> eman_zouine.asc

Luego si hacemos un cat al fichero podemos ver que efectivamente contiene la clave

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/0e4bf083-aa4d-4c2b-9545-dc02fcdd5968)

### 2. Importa las claves públicas recibidas de vuestro compañero.

Para este ejercicio lo que he hecho ha sido tomar otra maquina crear la clave ahí y pasarla por scp a mi máquina para importar la clave

Para importar una clave de un compañero usamos el comando

    gpg --import ejemplo_compañero.asc 

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/786901f7-90b5-44db-8b5b-f6a3e416188c)

### 3. Comprueba que las claves se han incluido correctamente en vuestro keyring.

Para comprobarlo basta con listar otra vez las claves públicas que tenemos

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/d744dd4c-eb9d-4173-916c-f7a08aaf730e)


## Tarea 3: Cifrado asimétrico con claves públicas (3 puntos)

Tras realizar el ejercicio anterior, podemos enviar ya documentos cifrados utilizando la clave pública de los destinatarios del mensaje.

### 1. Cifraremos un archivo cualquiera y lo remitiremos por email a uno de nuestros compañeros que nos proporcionó su clave pública.

Para cifrar el fichero con la clave publica de nuestro compañero usaremos las opciones -e y -r de esta forma, una vez lo usemos nos saldrá una advertencia de si queremos usar esta clave publica ya que no se sabe si la persona que afirma ser es cierto

    gpg -e -r "Ejemplo Compañero" fichero1.txt

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/470eae76-595b-47c8-b34e-f5e9423c3ab2)

### 2. Nuestro compañero, a su vez, nos remitirá un archivo cifrado para que nosotros lo descifremos.

Por scp he pasado un fichero cifrado de otra maquina con mi clave publica a mi máquina que tiene la clave privada.

### 3. Tanto nosotros como nuestro compañero comprobaremos que hemos podido descifrar los mensajes recibidos respectivamente.

Para descifrarlo usaremos un comando que al usar te pedirá la contraseña de la clave

    gpg -d ficheroejem.txt.gpg

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/0c4fa067-a633-4dfe-8866-a4ba20680d63)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/1726e7b9-232a-4f36-b783-7c1a1d43fbc9)

### 4. Por último, enviaremos el documento cifrado a alguien que no estaba en la lista de destinatarios y comprobaremos que este usuario no podrá descifrar este archivo.

Ahora cifraremos otro archivo pero con una clave distinta a cualquiera que tenga mi otra máquina, una vez pasado por scp si intentamos descifrarlo no podrá ya que no tenemos la clave privada

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/d1ecca92-9789-4bd4-a326-f9fd5970959e)

### 5. Para terminar, indica los comandos necesarios para borrar las claves públicas y privadas que posees.

Para eliminar una clave privada usamos el comando que hará que nos pregunte dos veces por terminal si estamos seguros de querer eliminar la clave y después otras 2 de forma gráfica donde tendremos que clickar

    gpg --delete-secret-keys "Eman Zouine 2"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/0976c772-f55c-48a8-a773-1153ecfe4fbd)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/2c3656c5-36f5-43b4-8beb-8263209d7c39)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/7eb646a4-b444-4781-8b6a-1e85c6f19567)

Para eliminar las claves públicas usamos el comando que al ser la pública no tendrá tantas confirmaciones ya que no es tan importante

    gpg --delete-keys "Eman Zouine 2"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/86854d09-5f78-4b57-b134-0be1f5e3c9fb)


## Tarea 4: Exportar clave a un servidor público de claves PGP (2 puntos)

Para distribuir las claves públicas es mucho más habitual utilizar un servidor específico para distribuirlas, que permite a los clientes añadir las claves públicas a sus anillos de forma mucho más sencilla.

### 1. Genera la clave de revocación de tu clave pública para utilizarla en caso de que haya problemas.

Para generar la clave de revocación usaremos el comando

    gpg --gen-revoke F451BAC0AC313D5DAE5F070B24A06BC381398860

Una vez lo ejecutemos nos preguntaran varias cosas, lo primero es la razón de esa revocación de clave, en mi caso como es una practica seleccionaré 0, luego puedes ponerle una descripción, luego te preguntará la contraseña y ya finalmente creara el certificado de revocación

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/0ea5a2ae-25c0-49b8-8e99-aaf6ffc11e3c)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/ede612fd-b415-4bb3-bafb-972f65df28dc)


### 2. Exporta tu clave pública al servidor pgp.rediris.es

Para exportar una clave pública al servidor usamos el comando (He tenido que usar otro servidor ya que en ese no he podido hacerlo)

    gpg --keyserver keys.gnupg.net --send-key F451BAC0AC313D5DAE5F070B24A06BC381398860

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/7e4a223c-55f8-4b48-9545-18de05dd7b4f)


### 3. Borra la clave pública de alguno de tus compañeros de clase e impórtala ahora del servidor público de rediris.

Para importar una clave pública usamos el comando

    gpg --keyserver keys.gnupg.net --recv-keys F575397D1F24DBA37B2DB8DED3B0DC17CD5B5F7E

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/6c0709ba-7475-48a9-89a4-3132297941be)


## Tarea 5: Cifrado asimétrico con openssl (3 puntos)

En esta ocasión vamos a cifrar nuestros ficheros de forma asimétrica utilizando la herramienta openssl.

### 1. Genera un par de claves (pública y privada).

Para generar el par de claves vamos a usar el algoritmo RSA. Además, vamos a hacer que la clave privada que utilizará el algoritmo AES128. Este par de claves se generará en un único fichero .pem. En este caso, el fichero de salida será key.pem. Por último, especificaremos el tamaño de la clave, que es recomendable que sea de al menos 2048 bits. El comando a ejecutar sería:

    sudo openssl genrsa -aes128 -out key.pem 2048

Ademas te preguntará por una passphrase

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/fce40f73-69f3-46d2-a04f-346a24550acc)


### 2. Envía tu clave pública a un compañero.

Para enviar la clave a mi otra máquina antes tendré que generar la clave pública ya que la generada antes es la privada eso lo haremos con el comando donde indicamos el fichero privado y la salida que será el público

    sudo openssl rsa -in key.pem -pubout -out key.public.pem

Además te pedirá la passphrase de antes

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/57e067da-aa63-489b-9ba4-93b1c23ac007)


### 3. Utilizando la clave pública cifra un fichero de texto y envíalo a tu compañero.

Me he pasado otra clave privada por scp desde la otra máquina ya que es la que usaré para cifrar un archivo

Luego usamos el comando

    openssl pkeyutl -encrypt -in ficherossl.txt -out fichero.enc -inkey clave.publica.pem -pubin

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/1da84d1e-a975-4827-85f3-c2e3da67f70c)


### 4. Tu compañero te ha mandado un fichero cifrado, muestra el proceso para el descifrado.

Para descifrar el fichero enviado por scp usaremos el comando:

    sudo openssl pkeyutl -decrypt -in cifrado.enc -out descifrado.txt -inkey key.pem

Donde te preguntara por la contraseña, luego si hacemos una lectura del fichero descifrado podemos ver que es legible

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/62f54e9f-f2e0-4d63-97f6-3b3129456884)


