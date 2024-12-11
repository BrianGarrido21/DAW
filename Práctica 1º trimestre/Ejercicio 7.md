## Paso 1: Instalar Nginx
1. Actualiza los repositorios e instala Nginx:

```bash
  sudo apt update
  sudo apt install nginx
```
2. Configura Nginx para escuchar en el puerto 8080:
Edita el archivo de configuración predeterminado de Nginx:

```nginx
server {
    listen 8080;
    server_name servidor2.centro.intranet;

    root /var/www/html;
    index index.php index.html index.htm;
    
    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php8.1-fpm.sock; # Asegúrate de usar la versión de PHP instalada
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
```

3. Enlaza el archivo de configuración si es necesario:
   ```bash
    sudo ln -s /etc/nginx/sites-available/default /etc/nginx/sites-enabled/
   ```

4. Prueba la configuración de Nginx

## Paso 2: Configurar PHP en Nginx

3. Crea un archivo de prueba PHP en el directorio raíz:
   ```bash
    echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/index.php
   ```

4. Entra al dominio por el puerto 8080

   http://servidor2.centro.intranet:8080
![Screenshot 2024-12-11 at 09 10 44](https://github.com/user-attachments/assets/26658c2a-9a2b-4799-a672-04b109570be2)

5. Crea un enlace simbólico de phpMyAdmin para Nginx:

```bash
sudo ln -s /usr/share/phpmyadmin /var/www/html/phpmyadmin
```

http://servidor2.centro.intranet:8080/phpmyadmin

![Screenshot 2024-12-11 at 09 13 13](https://github.com/user-attachments/assets/bec55efd-dd7c-4c24-90ee-f55bcdb72425)
