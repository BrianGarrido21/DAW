# Actividad #2: Configuración y Pruebas en el Servidor Apache

Pon en marcha el servidor Apache y lleva a cabo los siguientes cambios en el archivo de configuración.

## Documentación Relevante

Es recomendable leer los siguientes documentos antes de comenzar:

- [Guía para iniciar con Apache HTTP Server 2.4](https://httpd.apache.org/docs/2.4/getting-started.html)
- [Distribución de archivos de configuración en Apache](http://wiki.apache.org/httpd/DistrosDefaultLayout#Win32_.28Apache_httpd_2.2.29)
- [Guía de solución de problemas comunes en Apache (BlueHosting)](https://docs.bluehosting.cl/troubleshooting/servidores/guia-de-solucion-de-problemas-comunes-de-apache.html)

## Tareas a Realizar

1. **Configurar Apache para que utilice el puerto 81 además del 80**:
   - Abre el archivo de configuración de puertos de Apache:
     ```bash
     sudo nano /etc/apache2/ports.conf
     ```
   - Modifica el archivo de configuración de Apache para añadir el puerto 81. Esto suele hacerse en el archivo `ports.conf` agregando la línea:
     ```apache
     Listen 81
     ```
   - Guarda el archivo y cierra el editor.
   - Reinicia Apache para aplicar los cambios:
     ```bash
      sudo systemctl restart apache2
     ```
     
2. **Añadir el dominio “marisma.intranet” en el fichero `hosts`**:
   - Abre el archivo `/etc/hosts`:
     ```bash
     sudo nano /etc/hosts
     ```
   - Edita el archivo `/etc/hosts` y añade la siguiente línea:
     ```
     127.0.0.1 marisma.intranet
     ```
   - Guarda y cierra el archivo.

3. **Modificar la directiva `ServerTokens` para mostrar el nombre del producto**:
   - Abre el archivo de configuración de Apache:
     ```bash
      sudo nano /etc/apache2/apache2.conf
     ```
   - En el archivo de configuración principal (`apache2.conf` o `httpd.conf`), busca la directiva `ServerTokens` y modifícala para que muestre solo el nombre del producto:
     ```apache
     ServerTokens ProductOnly
     ```
   - Guarda y cierra el archivo.
   - Reinicia Apache:
     ```bash
      sudo systemctl restart apache2
     ```

4. **Mostrar el pie de página de Apache en el navegador**:
   - Asegúrate de que la directiva `ServerSignature` esté configurada en On en el archivo de configuración:
     ```bash
      sudo nano /etc/apache2/apache2.conf
     ```
   - Añade o edita la siguiente línea:
      ```apache
      ServerSignature On
     ```
   - Guarda y reinicia Apache:
     ```bash
      sudo systemctl restart apache2
     ```

5. **Crear directorios `prueba` y `prueba2` con páginas de prueba**:
   - Crea los directorios `prueba` y `prueba2` en el directorio raíz de Apache:
     ```bash
        sudo mkdir /var/www/html/prueba
        sudo mkdir /var/www/html/prueba2
     ```
   - Crea una página de prueba en cada directorio:
      ```bash
       echo "<h1>Página de prueba 1 en carpeta prueba</h1>" | sudo tee /var/www/html/prueba/index.html
       echo "<h1>Página de prueba 2 en carpeta prueba2</h1>" | sudo tee /var/www/html/prueba2/index.html
     ```

6. **Redirigir el contenido de la carpeta `prueba` hacia `prueba2`**:
   - Abre el archivo de configuración de Apache para el sitio o un archivo `.htaccess` en `/var/www/html/prueba/`:
     ```bash
     sudo nano /var/www/html/prueba/.htaccess
     ```
   - Añade la directiva de redirección:
     ```apache
      Redirect /prueba /prueba2
     ```
   - Guarda y reinicia Apache:
    ```bash
      sudo systemctl restart apache2
     ```
     
7. **Redirigir solo una página específica en lugar de toda la carpeta**:
   - Prueba a redirigir una sola página de `prueba` a `prueba2` usando una redirección específica.

9. **Usar la directiva `UserDir`**:
   - Activa y configura `UserDir` para permitir a los usuarios tener sus propios directorios accesibles a través del navegador.

10. **Usar la directiva `Alias` para redirigir a una carpeta dentro del directorio de usuario**:
   - Configura la directiva `Alias` en el archivo de configuración para apuntar a un directorio dentro de los directorios de usuario.

11. **Directiva `Options` y verificación de la indexación de directorios en Apache**:
    - Investiga la función de la directiva `Options` y verifica si Apache está indexando directorios.
    - Para desactivar la indexación de directorios, utiliza la configuración:
      ```apache
      Options -Indexes
      ```
