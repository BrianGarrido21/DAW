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
```bash
cd /var/www/html
```
2. Descarga WordPress:

![Screenshot 2024-12-10 at 17 22 24](https://github.com/user-attachments/assets/5108bc99-87cc-42b0-8bf4-8b0d5cc471ca)

3. Extrae el archivo:

![Screenshot 2024-12-10 at 17 22 41](https://github.com/user-attachments/assets/1f72fec8-5162-47f8-be7f-d02d4592215d)



6. Mueve los archivos de WordPress al directorio raíz y configura los permisos:

![Screenshot 2024-12-10 at 17 23 07](https://github.com/user-attachments/assets/16aa9108-d5a7-46ea-946a-620f02949fd8)

7. Definimos la base de datos y hacemos paso a paso la instalación de Wordpres
![Screenshot 2024-12-10 at 18 58 26](https://github.com/user-attachments/assets/bc90f21c-9208-4814-b8b6-859ace2f051c)
![Screenshot 2024-12-10 at 19 03 48](https://github.com/user-attachments/assets/5fc9c03d-3756-422e-88db-d37eff28101a)
![Screenshot 2024-12-10 at 19 05 16](https://github.com/user-attachments/assets/9f3e8d05-b87d-4553-bc26-6ba4774c1805)
![Screenshot 2024-12-10 at 19 05 35](https://github.com/user-attachments/assets/85dbaa3e-8e6e-4b1b-9386-a5a008a4e746)
![Screenshot 2024-12-10 at 19 05 52](https://github.com/user-attachments/assets/5a8aa919-f48e-4a8e-8a1f-ff550c6c3942)




