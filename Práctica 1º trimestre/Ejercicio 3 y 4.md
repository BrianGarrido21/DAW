El módulo mod_wsgi es necesario para permitir la ejecución de aplicaciones Python, como aplicaciones basadas en Django o Flask, en el servidor Apache. Aquí tienes cómo activarlo en un servidor Ubuntu:

## PASO 1: Instalar el módulo mod_wsgi
1. Instala el módulo mod_wsgi para Apache:
   ```bash
   sudo apt install libapache2-mod-wsgi-py3
   ```
![Screenshot 2024-12-10 at 19 09 35](https://github.com/user-attachments/assets/898f3e23-fc99-4ef9-a0c6-cae1effe51dc)

## Paso 2: Activar el módulo wsgi

1. Activa el módulo en Apache:
2. Reinicia Apache para aplicar los cambios:
![Screenshot 2024-12-10 at 19 13 18](https://github.com/user-attachments/assets/4a1a5be1-a80d-45ed-befd-c3edb33d9208)

## Paso 3: Configurar una aplicacición con python
1. Descargar las librerias que vayas a utilizar.
![Screenshot 2024-12-10 at 19 16 10](https://github.com/user-attachments/assets/10fa1ce8-11fe-4e55-aefa-6a246604f9bd)
![Screenshot 2024-12-10 at 19 18 15](https://github.com/user-attachments/assets/2513ceb5-df01-43c5-b1e3-ad67484071a9)

2. Crea un directorio para tu aplicación:
```bash
sudo mkdir flaskapp
sudo chown $USER:$USER flaskapp
cd flaskapp
```
3. Crea un archivo Python llamado app.py:
```bash
nano app.py
```
E introduce esto:
```bash
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hola Mundo Flask"

if __name__ == '__main__':
    app.run()
```

## Paso 3: Crear el archivo WSGI

1. Crear un archivo llamado flaskapp.wsgi
   ```bash
   nano flaskapp.wsgi
   ```
![Screenshot 2024-12-10 at 19 24 31](https://github.com/user-attachments/assets/17a09f72-66fa-4416-800b-6713b68e907c)

## Paso 4: Configurar Apache
1. Crea un archivo de configuracion de apache
   ```bash
    sudo nano /etc/apache2/sites-available/flaskapp.conf
   ```
  ![Screenshot 2024-12-10 at 19 34 02](https://github.com/user-attachments/assets/631ea3c5-6cd3-459c-98db-0052d2cf8b1f)

## Paso 5: Comprobar la aplicación

![Screenshot 2024-12-11 at 07 49 53](https://github.com/user-attachments/assets/0cc82592-516a-46e2-8957-4827b0089c67)
