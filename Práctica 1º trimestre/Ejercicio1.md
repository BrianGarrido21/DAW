Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet y departamentos.centro.intranet. 
El primero servirá el contenido mediante wordpress y el segundo una aplicación en python

## Paso 1: Actualiza tu sistema
Antes de instalar cualquier software, es recomendable actualizar los paquetes de tu sistema para asegurarte de tener las últimas versiones de los repositorios.
```bash
sudo apt update
```
## Paso 2: Instala Apache
Para instalar Apache en Ubuntu, usa el siguiente comando:
```bash
sudo apt install apache2 -y
```
Esto instalará Apache y las dependencias necesarias.

## Paso 3: Verifica la instalación
Una vez que Apache se haya instalado correctamente, verifica si el servicio está activo ejecutando:
```bash
sudo systemctl status apache2
```
<img width="733" alt="Screenshot 2024-12-02 at 17 25 01" src="https://github.com/user-attachments/assets/15ddb57c-861e-4614-9650-b8eb28602ed0">

<img width="902" alt="Screenshot 2024-12-02 at 18 11 28" src="https://github.com/user-attachments/assets/4b19e359-aaf6-4814-b36e-07ece8a83284">



Para configurar dos dominios personalizados como centro.intranet y departamentos.centro.intranet en Apache, debes realizar algunas configuraciones tanto en el archivo de hosts de tu sistema operativo como en la configuración de Apache.

Aquí están los pasos para hacerlo:

Paso 1: Modificar el archivo /etc/hosts (Local DNS)
El archivo /etc/hosts en tu sistema operativo se utiliza para mapear direcciones IP a nombres de dominio. Deberás añadir las entradas correspondientes para que tu máquina local reconozca los dominios centro.intranet y departamentos.centro.intranet.

Abre el archivo /etc/hosts con un editor de texto (como nano):
```bash
sudo nano /etc/hosts
```
Agrega las siguientes líneas al final del archivo, donde 127.0.0.1 es la dirección IP de tu servidor local (si estás trabajando en un servidor local):

<img width="530" alt="Screenshot 2024-12-02 at 18 04 36" src="https://github.com/user-attachments/assets/ce85e706-f47c-4fc3-a3ea-cc9ae0daef09">

## Paso 4: Instalar php y mysql

Procedemos a instalar php y mysql:

![Screenshot 2024-12-10 at 16 58 30](https://github.com/user-attachments/assets/e07e0b18-41cf-467c-a02f-492849c335a2)

![Screenshot 2024-12-10 at 17 01 09](https://github.com/user-attachments/assets/34fb2f58-86ee-4ec6-98da-67b3c26293ea)

