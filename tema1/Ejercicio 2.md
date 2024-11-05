# Actividad #2 - Configuración y Personalización de Apache

## Requisitos previos

### Documentos de consulta recomendados:
- [Introducción a Apache HTTP](https://httpd.apache.org/docs/2.4/getting-started.html)
- [Distribución de archivos de configuración de Apache](http://wiki.apache.org/httpd/DistrosDefaultLayout#Win32_.28Apache_httpd_2.2.29)
- [Solución de problemas comunes en Apache](https://docs.bluehosting.cl/troubleshooting/servidores/guia-de-solucion-de-problemas-comunes-de-apache.html)

### Nota
Si necesitas instalar algún módulo adicional en Apache, usa el comando `a2enmod`:
```bash
sudo a2enmod userdir
```

## Paso 1: Iniciar el servidor Apache
Para iniciar el servidor Apache, usa el siguiente comando:
```bash
sudo systemctl start apache2
```
Verifica que Apache esté funcionando accediendo a http://localhost/ en tu navegador.

## Paso 2: Configurar Apache para usar el puerto 81 además del 80

#### 	1.	Abre el archivo de configuración de puertos:
```bash
sudo nano /etc/apache2/ports.conf
```
####	2.	Añade el puerto 81 modificando o añadiendo la siguiente línea:
```apache
Listen 81
```
