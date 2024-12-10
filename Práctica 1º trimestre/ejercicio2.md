Para instalar wordpress:

## Paso 1: Configurar el servidor
Descargar dependecias. Ya hecho en el ejercicio anterior.

## Paso 2: Cofigurar la base de datos
Se hace mediante estos comando.
```sql
CREATE DATABASE wordpress;
CREATE USER 'wordpressuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpressuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```
![Screenshot 2024-12-10 at 17 14 45](https://github.com/user-attachments/assets/a3a695fa-5cd0-49de-9db0-ec8d76c34ab0)

## Paso 3: Descargar Wordpress

1. Ve al directorio raíz del servidor web:

2. Descarga WordPress:

![Screenshot 2024-12-10 at 17 22 24](https://github.com/user-attachments/assets/5108bc99-87cc-42b0-8bf4-8b0d5cc471ca)

3. Extrae el archivo:

![Screenshot 2024-12-10 at 17 22 24](https://github.com/user-attachments/assets/82285787-aff5-46a0-8214-c533bf4a62f4)


5. Mueve los archivos de WordPress al directorio raíz:

6. Configura los permisos:

![Screenshot 2024-12-10 at 17 23 07](https://github.com/user-attachments/assets/16aa9108-d5a7-46ea-946a-620f02949fd8)
