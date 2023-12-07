# Cifrado simétrico con gpg

GnuPG  (la versión libre de PGP o mejor dicho Pretty Good Privacy), nos permite cifrar cualquier tipo de archivo que podremos mandar “libremente” con cierta seguridad de que nadie lo podrá leer.

Como ya sabéis el cifrado simétrico es el tipo de cifrado más sencillo que hay, es más rápido de procesar y por desgracia menos seguro que el cifrado asimétrico.

Para empezar la prueba tenemos que tener un archivo de cualquier tipo e introducir en la terminal de Linux el comando gpg con el parámetro -c para cifrar y -d para descifrar.

Por ejemplo para cifrar el fichero fichero.txt:

gpg -c fichero.txt

Nos pide la clave de encriptación y nos genera el fichero fichero.txt.gpg.

Para desencriptar el fichero simplemente ejecutamos:

gpg -d fichero.txt.gpg

Nos pide la clave y nos muestra el contenido del fichero original (Nota: si estáis usando gnome al introducir la clave para realizar la encriptación se guarda en una cache, por lo que no os va a pedir la clave a la hora de desencriptar)

Si queremos recuperar el fichero original:

gpg -d fichero.txt.gpg > fichero2.txt

# Ejercicios:

## 1. Crea un documento de texto con cualquier editor o utiliza uno del que dispongas.

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/8782aae5-1995-4a78-b885-1933193092d7)


## 2. Cifra este documento con alguna contraseña acordada con el compañero de al lado.

Ciframos el fichero de texto con:

gpg -c fichero.txt

Una vez ejecutas el comando introduces la contraseña

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/9a1b0740-58b1-4c8a-9a80-39500d8031f2)

Te da una advertencia de que la contraseña es insegura, en mi caso me ha saltado porque la contraseña es “usuario”

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/fc6a0365-8870-4060-8aee-ae2cc0aff1d0)


## 3. Haz llegar por algún medio al compañero de al lado el documento que acabas de cifrar.

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/97500153-d454-4682-a1c4-85af86effa56)


## 4. Descifra el documento que te ha hecho llegar tu compañero de al lado.

Para descifrar la contraseña usamos el comando:

gpg -d ficherosim.txt.gpg

Luego introducimos la contraseña y podemos ver el contenido del fichero ya descifrado

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/d05fc420-e471-4ba8-bed6-57a55f8d776c)


## 5. ¿Con qué algoritmo se ha cifrado el fichero? Vuelve a cifrar el fichero usando el algoritmo AES256. ¿Puedes hacer permanente esta configuración?

Para ver los detalles del fichero encriptado usamos el comando:

gpg --list-packets ficherosim.txt.gpg

Podemos ver que el algoritmo usado es AES256.CFB

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/3a257012-2dea-4fcb-a9c6-50f380c1bc90)


Como ya esta por defecto no hace falta describir el algoritmo pero en caso de querer especificarlo usamos el comando: 

gpg –cipher-algo AES256 -c ficherosim.txt

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/18cbddb1-010a-4d9c-8825-667274a893da)

## 6. Instala gpg en Windows (Gpg4win), repite el ejercicio en Windows. Puedes encriptar un mensaje en Linux y desencriptarlo en Windows y al contrario.

Una vez instalado Gpg4win crearemos un fichero y lo encriptamos usando el programa “Kleopatra”, lo abrimos y le damos “Firmar/Cifrar” seleccionamos el archivo a cifrar y después dejamos por defecto la configuración, luego le damos a “Cifrar”

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/7adb3be4-bebf-4dba-a519-603f4957d4ed)

Ahora mientras carga nos pedirá una contraseña de cifrado, usaré la misma otra vez, “usuario”

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/6bf082b6-73fe-47b1-9a1b-d1d14f0be1f1)

Nos saldrá la misma advertencia que antes pero le damos a que tome esa contraseña

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/41048241-bfdd-46fe-a68c-9fbcba63b891)

Un vez cifrado saldrá como Cifrado correctamente

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/984bdbe9-822e-41d3-b127-603eeaaba28c)

Pasamos el fichero de Windows a Linux con WinSCP

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/1f1cb7f0-ced6-40f7-a4b8-0bd96e700a98)

Hacemos lo mismo pasando el fichero de Linux a Windows

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/fb0574df-750b-4003-8b1e-aea4ed9521f2)

Desciframos el fichero de Windows en el Linux y comprobamos que sí que podemos leer el contenido

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/749ed5d4-0063-4c37-8af9-52a8221fbbf4)

Lo comprobamos también en el Windows con Kleopatra, le damos a “Descifrar/verificar”, seleccionamos el archivo y ponemos la contraseña del fichero

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/736542e1-074b-40a9-9fee-df0e7065b5a4)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/ef5822bf-eaed-478b-932f-b9852cb3c1e2)

Aparecerá que se ha descifrado, lo vemos en la ruta donde se ha guardado y podemos ver el contenido del fichero

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/52b10613-72bd-4b3f-a01e-3e02f515c2cd)

## 7. openssl es otra herramienta que nos permite cifrar mensajes de forma simétrica, investiga como se realiza este ejercicio utilizando esta herramienta

Para cifrar los ficheros con openssl de forma simétrica hemos de usar el comando 

openssl enc -aes-256-cbc -in ficherosim.txt -out ficherosim.enc

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/6771804f-ef93-4b8b-9e68-90b1a3fae4f5)


Para descifrar un fichero cifrado con openssl usamos el mismo comando que antes solo que añadimos el “-d” delante y cambiamos los ficheros, en “-in” pondremos el fichero cifrado de antes y en “-out” donde se guardará el fichero descifrado.

openssl enc -d -aes-256-cbc -in ficherosim.enc -out ficherodescifrado.txt

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/837aeea1-8dba-4a11-94d1-9d424960c71f)

