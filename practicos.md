# Casos prácticos

## Versión instalada
Para saber que versión de nginx tenemos instalada solo tenemos que escribir el comando: **nginx -v**

![version](/imagenes/version.PNG)

## Servicio Asociado
El servicio asociado es:

![directorio](/imagenes/servicio.PNG)

## Ficheros de configuración
Los ficheros de configuraicón de nginx se encuentran en la ruta "/etc/nginx/"

![directorio](/imagenes/directorio.PNG)

Hay muchos directorios y archivos aquí pero lo que voy a tomar en cuenta es:

- **nginx.conf** que es el fichero donde se encuentra la configuración general de nginx.
- **sites-available** que es el directorio donde se almacenan los sitios virtuales y donde por defecto ya tenemos uno creado.
- **sites-enabled** que el directorio donde se almacenan los sitios que tenemos activos actualmente y donde por defecto ya tenemos uno.

  '''bash
      openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/selfigned.key -out /etc/ssl/certs/selfsigned.crt
  '''

## Página web por defecto

Al instalar nginx se nos crea una página web por defecto en /var/www/html y sirve para ver si funciona y se ha instalado correctamente.

![paginadefecto](/imagenes/paginadefecto.PNG)

Ahora voy a modificar la página.

![pagina1](/imagenes/pagina1.PNG)

Cuando lo guardemos, ya se habrán aplicado los cambios a la página web.

![resultado1](/imagenes/resultado1.PNG)

## Virtual Hosting

Una definición sencilla de lo que es el balanceo de carga sería la siguiente:
El balanceo de carga es la manera en que las peticiones de Internet son distribuídas sobre una fila de servidores.

![resultado1](/imagenes/web1.PNG)
![resultado1](/imagenes/web2.PNG)

Configuración del archivo hosts para las webs:

![resultado1](/imagenes/hosts.PNG)

Resultado final

![resultado1](/imagenes/resultado1.PNG)

## AUTENTICACIÓN, AUTORIZACIÓN Y CONTROL DE ACCESO

El acceso a las webs se configura de la siguiente manera:

*   **Web1**: Disponible tanto desde la red interna como externa.
    
*   **Web2**: Solo accesible desde la red interna.
    ![resultado1](/imagenes/controlacceso.PNG)

Para aplicar estas restricciones, se deben realizar los siguientes cambios:

1.  **Modificar los archivos en sites-available**
    
    *   Ajustar la configuración de cada sitio en sites-available.
        
2.  **Actualizar el archivo hosts con las IPs permitidas**
    
    *   Definir las direcciones IP autorizadas tanto para la red interna como externa.
      ![resultado1](/imagenes/modificacionhosts.PNG)
        
3.  **Verificación del acceso desde la red interna**
    
    *   Usar curl para comprobar la accesibilidad interna.
        
4.  **Verificación del acceso desde la red externa**
    
    *   Confirmar que la web2 no es accesible desde el exterior.
        ![resultado1](/imagenes/paginaprohibida.PNG)

## AUTENTICACIÓN, AUTORIZACIÓN Y CONTROL DE ACCESO

En web1.org, existe un directorio privado que solo puede ser accedido por usuarios autenticados.

1.  **Actualizar nuevamente sites-available**
    
    *   Configurar el directorio privado dentro del archivo de configuración.
        
2.  **Comprobar que web1.org/privado solicita autenticación**
    
    *   Acceder al directorio para confirmar que se requiere un usuario válido.
        
3.  **Verificar que el acceso autenticado funciona correctamente**
    
    *   Iniciar sesión y comprobar el acceso exitoso.
        

## AUTENTICACIÓN, AUTORIZACIÓN Y CONTROL DE ACCESO

En web1, el directorio privado tiene una configuración especial:

*   **Desde la red externa**: Se requiere autenticación.
    
*   **Desde la red interna**: Acceso libre sin necesidad de autenticación.
    

1.  **Modificar nuevamente los archivos en sites-available**
    
    *   Aplicar las reglas correspondientes para diferenciar el acceso según la red.
        
## SEGURIDAD

Para reforzar la seguridad en web1, se implementará el acceso seguro mediante HTTPS.

1.  **Generar una clave privada y un certificado autofirmado**
![image](https://github.com/user-attachments/assets/64442a44-08ff-45d1-bd59-652f14b27ce2)
