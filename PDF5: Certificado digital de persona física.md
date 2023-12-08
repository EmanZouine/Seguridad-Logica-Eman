# Certificado digital de persona física


## Tarea 1: Instalación del certificado

### 1. Una vez que hayas obtenido tu certificado, explica brevemente cómo se instala en tu navegador favorito.

A través de un correo se descarga el certificado de Persona Física. Debe realizarse desde el mismo navegador desde el que se hizo la petición de obtención del certificado.

### 2. Muestra una captura de pantalla donde se vean las preferencias del navegador donde se ve instalado tu certificado.

En Firefox para ver el certificado tenemos que hacer la siguiente ruta "Ajustes -> Privacidad y Seguridad -> Certificados -> Ver certificados... -> Sus certificados"

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/891c0989-0b3b-4ffc-8988-6f38c005a04d)


### 3. ¿Cómo puedes hacer una copia de tu certificado?, ¿Cómo vas a realizar la copia de seguridad de tu certificado?. Razona la respuesta.

Para copiar el certificado nos quedamos en la misma ruta y seleccionamos la opción de "Hacer copia" y se nos descargará el certificado en nuestro equipo pero antes nos pedirá que le asignemos una contraseña.

Ahora que ya tenemos el certificado, lo mas recomendable es introducirlo en un dispositivo externo.

### 4. Investiga cómo exportar la clave pública de tu certificado.

En la misma ubicación si hacemos doble Click en un certificado aparecerá un visor de certificados. En la pestaña Detalles da la opción de Exportar....

## Tarea 2: Validación del certificado

### 1. Instala en tu ordenador el software autofirma y desde la página de VALIDe valida tu certificado. Muestra capturas de pantalla donde se comprueba la validación.

Para instalar en mi ordenador la autofirma basta con irme a la página de autofirma y descargarlo desde ahí

    https://firmaelectronica.gob.es/Home/Descargas.html

Ahora nos dirigimos a la página de VALIDe para validar nuestro certificado:

Aquí seleccionamos nuestro certificado ponemos el código de seguridad y ya nos dirá si el certificado es válido

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/32d487ea-a639-4435-89ff-82e1b05016cc)
![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/79bae02e-4e01-43d9-b077-532c23e91dea)


## Tarea 3: Firma electrónica

### 1. Utilizando la página VALIDe y el programa autofirma, firma un documento con tu certificado y envíalo por correo a un compañero.

En la página principal seleccionaremos la opción de "Realizar firma" y crearé un fichero ejemplo que firmaré desde la página web

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/79773246-64ee-4cb5-8e37-0d953e60495c)

Seleccionamos la firma a usar

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/bd6ac8d2-824a-46c7-82ce-e7e504825512)

Te pedirá permiso para acceder a la contraseña de la firma

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/8f3a0860-314a-47dd-a676-66a472177f3c)

Y finalmente dirá que se ha firmado correctamente

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/dcb12ea4-b4bf-4c44-bc86-d1483394f59e)


### 2. Tu debes recibir otro documento firmado por un compañero y utilizando las herramientas anteriores debes visualizar la firma (Visualizar Firma) y (Verificar Firma). ¿Puedes verificar la firma aunque no tengas la clave pública de tu compañero?, ¿Es necesario estar conectado a internet para hacer la validación de la firma?. Razona tus respuestas.

### 3. Entre dos compañeros, firmar los dos un documento, verificar la firma para comprobar que está firmado por los dos.


## Tarea 4: Autentificación

### 1. Utilizando tu certificado accede a alguna página de la administración pública )cita médica, becas, puntos del carnet,…). Entrega capturas de pantalla donde se demuestre el acceso a ellas. 

En este caso yo accederé a Clic Salud donde puedes acceder mediante el certificado digital

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/033dc322-6a84-452a-a61d-bffcd22dffdd)

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/9424f130-9fbf-4c3d-835d-66590e7130c9)

![imagen](https://github.com/EmanZouine/Seguridad-Logica-Eman/assets/117440289/b264f1ee-a55a-4012-89e2-2124fe67299e)


# HTTPS / SSL
Antes de hacer esta práctica vamos a crear una página web (puedes usar una página estática o instalar una aplicación web) en un servidor web apache2 que se acceda con el nombre tunombre.iesgn.org.


## Tarea 1: Certificado autofirmado

Esta práctica la vamos a realizar con un compañero. En un primer momento un alumno creará una Autoridad Certficadora y firmará un certificado para la página del otro alumno. Posteriormente se volverá a realizar la práctica con los roles cambiados. Para hacer esta práctica puedes buscar información en internet, algunos enlaces interesantes:

• Phil’s X509/SSL Guide
• How to setup your own CA with OpenSSL
• Crear autoridad certificadora (CA) y certificados autofirmados en Linux

El alumno que hace de Autoridad Certificadora deberá entregar una documentación donde explique los siguientes puntos:

### 1. Crear su autoridad certificadora (generar el certificado digital de la CA). Mostrar el fichero de configuración de la AC.

### 2. Debe recibir el fichero CSR (Solicitud de Firmar un Certificado) de su compañero, debe firmarlo y enviar el certificado generado a su compañero.

### 3. ¿Qué otra información debes aportar a tu compañero para que éste configure de forma adecuada su servidor web con el certificado generado?

El alumno que hace de administrador del servidor web, debe entregar una documentación que describa los siguientes puntos:

### 1. Crea una clave privada RSA de 4096 bits para identificar el servidor.

### 2. Utiliza la clave anterior para generar un CSR, considerando que deseas acceder al servidor con el FQDN (tunombre.iesgn.org).

### 3. Envía la solicitud de firma a la entidad certificadora (su compañero).

### 4. Recibe como respuesta un certificado X.509 para el servidor firmado y el certificado de la autoridad certificadora.

### 5. Configura tu servidor web con https en el puerto 443, haciendo que las peticiones http se redireccionen a https (forzar https).

### 6. Instala ahora un servidor nginx, y realiza la misma configuración que anteriormente para que se sirva la página con HTTPS.
