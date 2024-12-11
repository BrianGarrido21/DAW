
## Paso 1: Instalar AWStats y configurar Apache para AWStats

![Screenshot 2024-12-11 at 08 38 44](https://github.com/user-attachments/assets/e65887fa-cd56-47de-b65a-58fa4a13c040)

```bash
sudo nano /etc/apache2/conf-available/awstats.conf
```

![Screenshot 2024-12-11 at 08 45 04](https://github.com/user-attachments/assets/8947d2f6-e412-4327-ba65-9706277842bc)


## Paso 2: Configurar AWStats 

1. Copia el archivo de configuracion por defecto.
   ```bash
   sudo cp /etc/awstats/awstats.conf /etc/awstats/awstats.localhost.conf
   ```

2. Edita el archivo de configuración para tu entorno local:
   ![Screenshot 2024-12-11 at 08 52 34](https://github.com/user-attachments/assets/5aabb1a9-706c-4b2a-98bb-cdafe53edd89)

## Paso 3: Generar las estadísticas

![Screenshot 2024-12-11 at 09 01 08](https://github.com/user-attachments/assets/ec27f463-76a0-4c0d-9ad4-704c12ea03f9)

## Paso 4: Acceder a AWStats en tu navegador
![Screenshot 2024-12-11 at 08 56 56](https://github.com/user-attachments/assets/80b8c549-f9d9-4572-b6df-ed4146ea5703)
