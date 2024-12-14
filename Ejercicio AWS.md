# 1. Configuración inicial de la instancia AWS

## Iniciar el laboratorio de AWS.
![Screenshot 2024-12-14 at 08 48 42](https://github.com/user-attachments/assets/6d539a95-12c3-42af-bc26-0ab3b88f144c)

1. Cuando ya este listo entramos en el laboratorio y nos deberia salir la pantalla principal.
![Screenshot 2024-12-14 at 08 50 50](https://github.com/user-attachments/assets/4d50b63e-b22a-4a35-b290-914a7c94cdcf)

2. Entramos en instancias
![Screenshot 2024-12-14 at 08 52 24](https://github.com/user-attachments/assets/1cc1745f-68e7-4c08-b95d-312b1d1f3e5c)

3. Lanzamos una nueva instancia
![Screenshot 2024-12-14 at 08 53 28](https://github.com/user-attachments/assets/36441a32-dc85-412e-8123-ba83ebc40210)
Lo configuramos con la configuración dependiendo de uso que le vamos a dar.
![Screenshot 2024-12-14 at 08 57 06](https://github.com/user-attachments/assets/a3f4b108-3611-4a20-a49b-537f4721d5b9)
![Screenshot 2024-12-14 at 08 57 12](https://github.com/user-attachments/assets/e512406a-a8c9-40a0-aaae-46aacc6b7fab)
![Screenshot 2024-12-14 at 08 57 45](https://github.com/user-attachments/assets/4014cba1-82f7-4a95-bcb9-d58c3143d28d)
Y lanzamos la instancia.
No deberia salir así
![Screenshot 2024-12-14 at 08 58 32](https://github.com/user-attachments/assets/3a2b06d3-7d0c-4c6c-9aaf-4b8d8bd2a1cf)

4. Ahora nos conectamos a la instancia desde SSH. Hay que seguir las instrucciones siguientes. 
![Screenshot 2024-12-14 at 08 59 54](https://github.com/user-attachments/assets/b7d29a30-3bf0-47d6-b8cb-a8a52e8e664d)
Antes que nada hay que descargarnos nuestro .pem que se instala. Para descargarlo en la instalación de la instacia hay que darle a "Download Key Pair" y esto se descarga.

Ahora entramos en el directorio donde esté el .pem y ponemos en el terminal la siguiente linea de comandos.
<img width="1102" alt="Screenshot 2024-12-14 at 09 04 43" src="https://github.com/user-attachments/assets/13cc3393-5b0d-48b4-b96c-6a3e15b75f6d" />
Y ya estamos conectados a la maquina virtual de AWS.

# 2. Activar la autenticación con MySql
1. Primero de todo hacemos actualizamos los paquetes con 
```bash
sudo apt update
```

2. Instalamos apache
    <img width="700" alt="Screenshot 2024-12-14 at 09 08 18" src="https://github.com/user-attachments/assets/3f220bc2-39bd-482e-b2aa-7004a3c23e06" />

3. Inicia y habilita el servicio Apache:
   <img width="707" alt="Screenshot 2024-12-14 at 09 09 38" src="https://github.com/user-attachments/assets/19a6070b-8b20-4895-bdfd-899879c60e84" />

4.  Activar la autenticación con MySQL
    Instala mysql:
    <img width="691" alt="Screenshot 2024-12-14 at 09 12 13" src="https://github.com/user-attachments/assets/c24b15f6-5272-4947-88ea-f8f48963cfa0" />

    Ejecutamos el script de seguridad:
    <img width="667" alt="Screenshot 2024-12-14 at 09 13 42" src="https://github.com/user-attachments/assets/1e6cff06-3b9c-4f11-a138-f74514841cf8" />
5. Crea un usuario y una base de datos para la autenticación:
<img width="711" alt="Screenshot 2024-12-14 at 09 15 55" src="https://github.com/user-attachments/assets/19105e0c-0950-440a-a276-dcc82e39446c" />

6. Configura la autenticación en Apache:

Instala el módulo de autenticación para MySQL:

<img width="710" alt="Screenshot 2024-12-14 at 09 18 17" src="https://github.com/user-attachments/assets/b386e7f0-6261-4810-8960-844727251b43" />

Habilita los módulos de Apache necesarios y reinicia apache:
<img width="566" alt="Screenshot 2024-12-14 at 09 19 06" src="https://github.com/user-attachments/assets/904dc149-83bc-467b-9428-058ff01737df" />

Entra al archivo de configuracion de apache:
```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```
Agrega las siguientes directivas para configurar la autenticación:

<img width="790" alt="Screenshot 2024-12-14 at 09 25 32" src="https://github.com/user-attachments/assets/1a41b18c-f7cd-4e78-83e0-71aa96868928" />

7. Crear la base de datos y la tabla de usuarios
   <img width="748" alt="Screenshot 2024-12-14 at 09 28 46" src="https://github.com/user-attachments/assets/93de16e6-a043-4f64-8dbe-db31ed487487" />

   Inserta un usuario. he utilizado bscrypt para encriptar la contraseña
   <img width="911" alt="Screenshot 2024-12-14 at 09 29 35" src="https://github.com/user-attachments/assets/8c947563-baac-4a92-b15b-0d1da9f96b88" />

Y reiniciamos Apache.

# Crear un certificado autofirmado y activar el módulo SSL

1.  Instalar OpenSSL y habilitar el módulo SSL

  ```bash
sudo apt install openssl -y

  ```

  ```bash
sudo a2enmod ssl
  ```

2. Generar un certificado autofirmado
Crea un directorio para almacenar el certificado y la clave privada y genera el certificado y la clave privada:


<img width="923" alt="Screenshot 2024-12-14 at 09 55 49" src="https://github.com/user-attachments/assets/03776191-b7b3-43e1-9418-e29b91e1df29" />

Esto generará dos archivos:
/etc/ssl/certificados/servidor.key (clave privada).
/etc/ssl/certificados/servidor.crt (certificado).

3. Configurar Apache para usar el certificado SSL
Habilitar el archivo de configuración para SSL:
<img width="504" alt="Screenshot 2024-12-14 at 09 56 52" src="https://github.com/user-attachments/assets/da39ebc3-83ee-47c0-ada0-261b5175b556" />

Edita el archivo de configuración del sitio SSL:
<img width="654" alt="Screenshot 2024-12-14 at 09 58 49" src="https://github.com/user-attachments/assets/5934cc2e-68c2-43fc-993a-8391fd47d2fe" />

 Y guardamos.
 Reiniciar Apache.
 
<img width="552" alt="Screenshot 2024-12-14 at 10 00 32" src="https://github.com/user-attachments/assets/c0952514-5f9c-4cea-a674-2144a585e265" />

