
Proteger el acceso a la aplicación Python mediante autenticación básica en Apache es un enfoque sencillo. Aquí tienes cómo configurarlo:

## Paso 1: Habilitar el módulo de autenticación de Apache
1. Asegúrate de que los módulos de autenticación de Apache estén habilitados
   ```bash
    sudo a2enmod auth_basic
    sudo a2enmod authn_file
    sudo systemctl restart apache2
   ```

## Paso 2: Crear un archivo de contraseñas
1. Usa el comando htpasswd para crear un archivo de contraseñas:
   ```bash
    sudo htpasswd -c /etc/apache2/.htpasswd usuario1
   ```

2. Para agregar más usuarios:

```bash
  sudo htpasswd /etc/apache2/.htpasswd usuario2
```

## Paso 3: Configurar la autenticación en el archivo de sitio

1. Edita el archivo de configuración de tu sitio (por ejemplo, /etc/apache2/sites-available/flaskapp.conf):
   ```bash
   sudo nano /etc/apache2/sites-available/flaskapp.conf
    ```

2. Añade el bloque de autenticación dentro del <Directory> de tu aplicación:
   ```apache
     <Directory /var/www/flaskapp>
      Require all granted
  
      AuthType Basic
      AuthName "Acceso Restringido"
      AuthUserFile /etc/apache2/.htpasswd
      Require valid-user
    </Directory>
   ```


