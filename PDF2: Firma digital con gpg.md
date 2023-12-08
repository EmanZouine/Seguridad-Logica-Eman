# Firma digital con gpg

Una firma digital certifica un documento y le añade una marca de tiempo. Si posteriormente el documento fuera modificado de cualquier modo, el intento de verificar la firma fallaría. La utilidad de una firma digital es la misma que la de una firma escrita a mano, sólo que la digital tiene una resistencia a la falsificación. Por ejemplo, la distribución del código fuente de GnuPG viene firmada con el fin de que los usuarios puedan verificar que no ha habido ninguna manipulación o modificación al código fuente desde que fue archivado.

Sigue el manual de gpg: Firmar y verificar firmas para realizar este ejercicio.

## Ejercicios: 


### 1. Selecciona un documento pdf y encríptalo y fírmalo (opción --sign). Envíalo a un compañero, que debe en primer lugar verificar la firma y posteriormente descifrar el documento.

Para hacer este ejercicio usaremos un pdf de sumas que he descargado y para cifrarlo primero tenemos que crear una firma y poner el nombre y correo electrónico como identificador:

    gpg --gen-key

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/3054841c-039f-4038-b4d8-2b9d0813fc3d)

Una vez ya creada la firma firmamos con esta el documento y no hará falta especificar cual usar ya que solo hay una, usamos el comando:

    gpg --sign documento.pdf

Y te pedirá una contraseña:

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/406d7fd8-ab40-498a-95f8-250a81ce8453)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/db8c521a-98c2-4fde-b625-8f4922461cdf)

Pasamos el pdf firmado por scp

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/df61eafb-004b-47ad-accf-2c9000a280cd)

Una vez ya pasado el documento lo verificamos, pero nos dirá que es imposible comprobar la firma porque no la hemos ni enviado ni recibido, para ello lo que haremos será enviar la clave a un servidor y que el cliente la reciba con los comandos

    gpg --keyserver keys.gnupg.net --send-key 0E0B264BA066FCCE0886256E911A401769998319

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/107eb184-7d75-46eb-8f5b-914a29e04932)

Y para recibir la clave ejecutamos el comando:

    gpg --keyserver keys.gnupg.net --recv-keys 0E0B264BA066FCCE0886256E911A401769998319

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/9370aea8-6b87-47a0-a02a-65ab9f4d21c0)

Una vez ya tenemos la clave podremos ver el firmado del documento al desencriptarlo con el siguiente comando

    gpg --output documento.pdf  --decrypt documento.pdf.gpg

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/a7751154-3cbc-40f2-a2a2-e35b0f63fe61)

### 2. Realiza el mismo ejercicio pero obteniendo una firma ASCII.

Para hacer lo mismo pero con firmas ASCII usamos el comando
 
    gpg --clearsign documento.pdf

Nos preguntará la contraseña de la clave que ya tenemos

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/550314c7-98c0-4c1b-bef4-a909243fe971)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/628038bc-6cf5-42a1-b530-56e228a1c205)

Lo pasamos también por scp

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/53736d55-0886-4fe7-9a4d-fc768afeffe5)

Y desencriptamos el documento

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/077c1390-68d5-4dae-8812-8cf3f708dad7)

### 3. Ahora sólo queremos firmar un documento. Firma un documento (opción --detach-sign). A continuación envía el documento original y la firma a un compañero para que verifique que el documento está firmado por tí.

Para este ejercicio usaremos el mismo documento de antes con el comando

    gpg --detach-sign documento.pdf

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/4014303a-e635-4bb5-9ced-a615540879ce)

Lo pasamos por scp

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/f4a97887-be6e-4656-a8f7-98b55143b77c)

Y hacemos un –verify para verificar la firma

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/33f58770-ff39-45d4-8c85-01026d2feef9)
