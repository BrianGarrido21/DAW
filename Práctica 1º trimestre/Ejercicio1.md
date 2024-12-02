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

# Paso 3: Verifica la instalación
Una vez que Apache se haya instalado correctamente, verifica si el servicio está activo ejecutando:
```bash
sudo systemctl status apache2
```
<img width="733" alt="Screenshot 2024-12-02 at 17 25 01" src="https://github.com/user-attachments/assets/15ddb57c-861e-4614-9650-b8eb28602ed0">
