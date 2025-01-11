# Activity #3

1. ### La UHU (Universidad de Huelva) tiene varios servidores DNS. Consulta a tu servidor DNS por defecto sus direcciones IP al menos 2 de ellos.
   **nslookup** es una herramienta de administración de red para consultar el Sistema de nombres de dominio (DNS) para obtener el mapeo de nombres de dominio o direcciones IP o cualquier otro registro DNS específico.
   
![Screenshot 2025-01-11 at 09 36 29](https://github.com/user-attachments/assets/8ae70065-5579-4dd0-9ee2-b1fb64324de0)

2. ### ¿Son las respuestas anteriores autoritativas? 

Para identificar otros servidores DNS autoritativos del dominio uhu.es, puedes ejecutar el siguiente comando:

![Screenshot 2025-01-11 at 09 54 53](https://github.com/user-attachments/assets/212b9b6d-62da-4e65-a25b-0446af2fe1d4)

3. ### Consulta la dirección IP de un servidor de correo de uhu.es.

   ![Screenshot 2025-01-11 at 09 57 19](https://github.com/user-attachments/assets/b0348110-98f6-43a0-8004-2c0fa642adc5)

4. ### ¿Son las respuestas anteriores autoritativas?

   Podemos comprobar que no son autoritativas. Porque no encuentra respuestas autoritativas.

5. ### Si hay más de un servidor autoritativo para el dominio uhu.es, ¿cómo sabemos cuál es el primario?¿en qué fecha se actualizó por última vez?¿cúal es la dirección e-mail del administrador?
   
![Screenshot 2025-01-11 at 17 30 19](https://github.com/user-attachments/assets/16c26338-99a8-4cd4-aa91-a6433d5f932b)


1. **Servidor Primario (Primary Name Server):**
   - `origin = master.infoblox`
   Esto indica que el servidor primario es **`master.infoblox`**. Este es el servidor autoritativo encargado de gestionar la zona DNS de `uhu.es`.

2. **Correo del Administrador del Dominio:**
   - `mail addr = please_set_email.absolutely.nowhere`
   Esto significa que **no se ha configurado una dirección de correo válida** para el administrador del dominio. Es un error común cuando los administradores no actualizan correctamente el registro SOA.

3. **Fecha de Última Actualización (Serial):**
   - `serial = 2019022119`
   El número de serie sigue el formato `YYYYMMDDNN`:
   - **2019022119** se descompone como:
     - **Año:** 2019
     - **Mes:** 02 (febrero)
     - **Día:** 21
     - **Número de cambios en ese día:** 19

   Esto indica que la última actualización fue el **21 de febrero de 2019** y que ese día hicieron **19 cambios** en los registros DNS.


### **Conclusión:**

| Pregunta                | Respuesta                              |
|-------------------------|----------------------------------------|
| **Servidor Primario**    | `master.infoblox`                      |
| **Última Actualización** | 21 de febrero de 2019                  |
| **Correo del Admin**     | No configurado (please_set_email.absolutely.nowhere) |

6. ### Comprueba que el DNS inverso está bien configurado para dns-1.uhu.es.

  1. Para comprobar si el DNS inverso está bien configurado para dns-1.uhu.es, lo que debes hacer es verificar si la dirección IP asociada a ese nombre de dominio realiza una resolución inversa adecuada. Esto se hace utilizando el comando nslookup o dig en modo inverso.
  ![Screenshot 2025-01-11 at 17 33 49](https://github.com/user-attachments/assets/002ed84f-3cce-4034-a954-4da889bb21be)

   2. A continuación, realiza la búsqueda inversa con esa IP:

   ![Screenshot 2025-01-11 at 17 35 09](https://github.com/user-attachments/assets/deff4302-9035-4c71-888e-13ec98fc84af)

7. ### Comprueba que el DNS inverso está bien configurado para **www.bp.com**

   ![Screenshot 2025-01-11 at 17 53 55](https://github.com/user-attachments/assets/4fe8ae46-505c-4255-ac89-15b1c14853f6)

   Este es un nombre de host asociado con Amazon Web Services (AWS). Esto ocurre porque bp.com está alojado en servidores de AWS,
   y el proveedor no ha configurado correctamente un registro PTR (Pointer Record) para que esa dirección IP apunte de vuelta a bp.com.

8. ### Por defecto, el comando NSLOOKUP devuelve los registros de tipo A. ¿Qué se obtiene al consultar los registros NS?

   Cuando usas el comando nslookup para consultar los registros NS (Name Server) de un dominio, obtienes la lista de servidores de nombres autoritativos que gestionan la zona DNS de ese dominio.
   
   Los registros NS indican cuáles son los servidores de nombres que tienen autoridad sobre el dominio. Estos servidores almacenan la información DNS, como los registros A, MX, CNAME, etc.

9. ### Consulta el TLD de las páginas de España: “es”.

    ![Screenshot 2025-01-11 at 18 07 26](https://github.com/user-attachments/assets/fb6c1d5d-49e5-4a4b-aa26-9d6675e42d8c)

Estos servidores son los responsables de gestionar la zona DNS de **todos los dominios `.es`**.

- El **TLD `.es`** tiene varios servidores de nombres distribuidos, gestionados principalmente por **Red.es**, la organización que administra los dominios `.es`.
- Estos servidores responden por todos los dominios registrados bajo **.es**.

10. ### ¿Se obtiene alguna respuesta? No, porque por defecto se buscan registros de tipo A y tipo AAAA. Como “es” no es un FQDN, lo lógico es buscar registros NS para saber qué servidores lo resuelven.
    
 La clave está en que el dominio es no es un FQDN (Fully Qualified Domain Name) que pueda devolver un registro de tipo A o AAAA. Por eso, si intentas consultarlo directamente con un simple comando nslookup es, no obtendrás ninguna respuesta útil.

11. ### Consulta las direcciones IP de www.google.com.
    
![Screenshot 2025-01-11 at 18 11 54](https://github.com/user-attachments/assets/a298660a-0745-4c21-b925-84fdd96bc8ef)

12. ### ¿Puede un mismo nombre de dominio traducirse en varias direcciones IP distintas?
    
Sí, un mismo nombre de dominio puede traducirse en varias direcciones IP para:
- Balancear la carga entre servidores.
- Garantizar alta disponibilidad y redundancia.
- Optimizar la velocidad y la experiencia del usuario mediante sistemas como Anycast.

 
