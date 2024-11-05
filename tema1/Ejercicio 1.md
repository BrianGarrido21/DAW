# Actividad #1 - Paso a Paso

## 1. Arquitectura Web y Plataformas LAMP y WISA

### Arquitectura Web de Tres Capas
1. **Capa de presentación**: Interfaz visual que interactúa con el usuario (HTML, CSS, JavaScript).
2. **Capa de lógica de negocio**: Procesa la lógica de la aplicación (scripts de servidor).
3. **Capa de datos**: Almacena la información en bases de datos.

### Plataformas Web
- **LAMP**: Linux, Apache, MySQL, PHP.
- **WISA**: Windows, Internet Information Services (IIS), SQL Server, ASP.NET.

---

## 2. Preparación del Entorno: Instalar Ubuntu en una Máquina Virtual

Si no tienes Ubuntu instalado en tu equipo, puedes instalarlo en una máquina virtual usando VirtualBox.

### Requisitos:
- [Descarga de VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Imagen de Ubuntu](https://ubuntu.com/download/desktop) (elige la versión que prefieras)

### Pasos:
1. **Instalar VirtualBox**: Abre el instalador descargado y sigue las instrucciones para instalar VirtualBox en tu sistema.
2. **Crear una Máquina Virtual en VirtualBox**:
   - Abre VirtualBox y haz clic en **Nueva**.
   - Especifica el nombre de la máquina virtual y selecciona **Linux** como sistema operativo y **Ubuntu (64-bit)** como versión.
   - Ajusta la memoria RAM y el tamaño del disco duro según las recomendaciones (2 GB de RAM y 20 GB de disco son adecuados).
3. **Montar la Imagen de Ubuntu**:
   - En las configuraciones de la máquina virtual, en **Almacenamiento**, selecciona el archivo ISO de Ubuntu como unidad de disco óptico.
4. **Instalar Ubuntu**:
   - Inicia la máquina virtual y sigue las instrucciones en pantalla para instalar Ubuntu en el disco virtual.

---

## 3. Instalación de la Pila LAMP en Ubuntu

Una vez que tengas Ubuntu listo, puedes instalar la pila LAMP (Linux, Apache, MySQL, PHP). Aquí tienes el paso a paso para instalar cada componente.

### Paso 1: Actualizar los Repositorios
Antes de instalar cualquier paquete, actualiza los repositorios de Ubuntu:

```bash
sudo apt update
```

### Paso 2: Instalar Apache

Instala Apache usando el siguiente comando:

```bash
sudo apt install apache2
```

Verifica que Apache esté funcionando. Abre un navegador web y accede a http://localhost/. Deberías ver la página de bienvenida de Apache.

### Paso 3: Instalar MySQL

Instala MySQL ejecutando el comando:

```bash
sudo apt install mysql-server
```

Configura MySQL con el siguiente comando para asegurarte de que esté seguro:

```bash
sudo mysql_secure_installation
```

Sigue las instrucciones en pantalla para configurar una contraseña segura para MySQL y otros ajustes de seguridad.

### Paso 4: Instalar PHP

```bash
sudo apt install php libapache2-mod-php php-mysql
```

Verifica que PHP esté funcionando. Crea un archivo de prueba en la carpeta de Apache:

```bash
sudo nano /var/www/html/info.php
```

Escribe el siguiente código en el archivo info.php y guárdalo:

```php
<?php
phpinfo();
?>
```

Prueba PHP. Abre un navegador y accede a http://localhost/info.php. Deberías ver una página con la configuración de PHP.
