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
