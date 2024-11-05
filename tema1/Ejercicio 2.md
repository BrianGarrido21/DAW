# Actividad #2: Configuración y Pruebas en el Servidor Apache

Pon en marcha el servidor Apache y lleva a cabo los siguientes cambios en el archivo de configuración.

## Documentación Relevante

Es recomendable leer los siguientes documentos antes de comenzar:

- [Guía para iniciar con Apache HTTP Server 2.4](https://httpd.apache.org/docs/2.4/getting-started.html)
- [Distribución de archivos de configuración en Apache](http://wiki.apache.org/httpd/DistrosDefaultLayout#Win32_.28Apache_httpd_2.2.29)
- [Guía de solución de problemas comunes en Apache (BlueHosting)](https://docs.bluehosting.cl/troubleshooting/servidores/guia-de-solucion-de-problemas-comunes-de-apache.html)

## Tareas a Realizar

1. **Configurar Apache para que utilice el puerto 81 además del 80**:
   - Modifica el archivo de configuración de Apache para añadir el puerto 81. Esto suele hacerse en el archivo `ports.conf` agregando la línea:
     ```apache
     Listen 81
     ```

2. **Añadir el dominio “marisma.intranet” en el fichero `hosts`**:
   - Edita el archivo `/etc/hosts` y añade la siguiente línea:
     ```
     127.0.0.1 marisma.intranet
     ```

3. **Modificar la directiva `ServerTokens` para mostrar el nombre del producto**:
   - En el archivo de configuración principal (`apache2.conf` o `httpd.conf`), busca la directiva `ServerTokens` y modifícala para que muestre solo el nombre del producto:
     ```apache
     ServerTokens ProductOnly
     ```

4. **Mostrar el pie de página de Apache en el navegador**:
   - Habilita la directiva correspondiente en el archivo de configuración para visualizar el pie de página en las respuestas del servidor.

5. **Crear directorios `prueba` y `prueba2` con páginas de prueba**:
   - Crea los directorios `prueba` y `prueba2` en el directorio raíz del servidor web (`/var/www/html` en muchas distribuciones) e incluye un par de páginas en cada uno.

6. **Redirigir el contenido de la carpeta `prueba` hacia `prueba2`**:
   - Usa directivas de redirección en el archivo `.htaccess` o en la configuración del sitio para redirigir todas las solicitudes de `prueba` a `prueba2`:
     ```apache
     Redirect /prueba /prueba2
     ```

7. **Redirigir solo una página específica en lugar de toda la carpeta**:
   - Prueba a redirigir una sola página de `prueba` a `prueba2` usando una redirección específica.

8. **Usar la directiva `UserDir`**:
   - Activa y configura `UserDir` para permitir a los usuarios tener sus propios directorios accesibles a través del navegador.

9. **Usar la directiva `Alias` para redirigir a una carpeta dentro del directorio de usuario**:
   - Configura la directiva `Alias` en el archivo de configuración para apuntar a un directorio dentro de los directorios de usuario.

10. **Directiva `Options` y verificación de la indexación de directorios en Apache**:
    - Investiga la función de la directiva `Options` y verifica si Apache está indexando directorios.
    - Para desactivar la indexación de directorios, utiliza la configuración:
      ```apache
      Options -Indexes
      ```
