# Activity #1


1. ### ¿Qué es TLD? ¿Cómo se clasifican los dominios de nivel superior?, Pon algunos ejemplos.
  Top Level Domain (TLD) Es uno de los dominios en el nivel más alto en se Sistema de nombre de dominio jerárquico de Internet despues del dominio raíz.
  Los nombres de dominio de nivel superior se instalan en la zona raíz del espacio de nombres. 
  
  Por ejemplo, en el nombre de dominio www.example.com, el dominio de nivel superior es .com.
   La responsabilidad de la gestión de la mayoría de los dominios de nivel superior está delegada a organizaciones específicas por la ICANN, una comunidad de múltiples partes interesadas de Internet, que opera la Autoridad de Números Asignados de Internet (IANA)

2. ### ¿Qué es FQDN?, Pon algún ejemplo de FQDN.
  El término **Fully Qualified Domain Name (FQDN)** se refiere a la dirección completa y única necesaria para tener presencia en Internet. 
  Está compuesta por el nombre de host y el de dominio y se utiliza para localizar hosts específicos en Internet y acceder a ellos mediante la resolución de nombres.
  
  El Fully Qualified Domain Name consta como mínimo de tres etiquetas: el dominio de nivel superior, el nombre de dominio y el nombre de host, 
  si bien hay ocasiones en las que se incluyen también subdominios.

  El siguiente ejemplo ilustra la estructura de un Fully Qualified Domain Name:

  hosting.ionos.es.
  
  > {Nombre de host} . {Dominio} . {TLD} . {Raíz} 
   
3. ### ¿Qué son los root servers? , ¿Cuántos root servers hay?, ¿Cuántos servidores raíz físicos existen y dónde se encuentran?, ¿Qué es anycast?

Los **Root Name Servers** son servidores de nombres encargados de gestionar la zona raíz del Sistema de Nombres de Dominio (DNS) en Internet. Estos servidores desempeñan una función crucial en la estructura del DNS, ya que responden directamente a las solicitudes de registros en la zona raíz y proporcionan información sobre los servidores de nombres autorizados para los dominios de nivel superior (TLD).

Actualmente, existen 13 servidores raíz distribuidos en todo el mundo, cuyos nombres siguen el formato "letra.root-servers.net". Sin embargo, es importante destacar que no todos ellos son servidores únicos. Siete de los trece son, en realidad, conjuntos de servidores distribuidos geográficamente mediante la técnica de anycast, lo que permite una mayor disponibilidad y redundancia.

Históricamente, diez de estos servidores se encontraban ubicados en los Estados Unidos. Con el tiempo, algunos de ellos han comenzado a operar mediante redes anycast, lo que permite que múltiples servidores compartan la misma dirección IP y respondan a las solicitudes desde ubicaciones distintas. Además, tres servidores raíz se instalaron originalmente en otras ciudades del mundo: uno en Estocolmo (I), otro en Ámsterdam (K) y uno más en Tokio (M).
      
La técnica de anycast es un método avanzado de direccionamiento y enrutamiento que optimiza la transmisión de información dentro de una red. En este esquema, los datos son enviados al nodo más cercano o al mejor destino desde el punto de vista topológico. Esto mejora la eficiencia y reduce la latencia en las comunicaciones, ya que las solicitudes se procesan por el servidor más cercano al usuario que realiza la consulta.

4. ### ¿Qué es un archivo de zona (zone file)? Indica para qué sirven los registros de un archivo de zona. Pon un ejemplo de un archivo de zona e interpreta la información almacenada

Un **Zone File** del DNS es un archivo de texto que describe una zona DNS. Una zona DNS es un subconjunto, a menudo un dominio único, de la estructura jerárquica de nombres de dominio del DNS. El archivo de zona contiene asignaciones entre nombres de dominio y direcciones IP y otros recursos, organizados en forma de representaciones de texto de registros de recursos (RR). Un archivo de zona puede ser un archivo maestro DNS, que describe de manera autoritaria una zona, o puede usarse para enumerar el contenido de una caché DNS.

Los registros de un archivo de zona sirven para establecer las configuraciones esenciales del dominio, permitiendo la resolución de nombres de dominio a direcciones IP. Cada registro de recurso (RR) en un archivo de zona proporciona información específica sobre el dominio o subdominio. Los principales registros que se encuentran en un archivo de zona son:

- **SOA (Start of Authority)**: Define la autoridad principal para la zona DNS, indicando el servidor que contiene la información autoritaria y otros detalles relevantes, como la persona responsable y los tiempos de actualización.
- **NS (Name Server)**: Define los servidores de nombres autoritativos para la zona.
- **A (Address)**: Asocia un nombre de dominio a una dirección IPv4.
- **AAAA (Address)**: Asocia un nombre de dominio a una dirección IPv6.
- **CNAME (Canonical Name)**: Define un alias para otro nombre de dominio.
- **MX (Mail Exchange)**: Indica los servidores de correo que gestionan los correos electrónicos para el dominio.
- **TXT (Text)**: Contiene información de texto asociada al dominio, como configuraciones de verificación y seguridad.
- **PTR (Pointer)**: Utilizado en resoluciones inversas para asociar una dirección IP con un nombre de dominio.

A continuación, se muestra un ejemplo de un archivo de zona ficticio para el dominio `example.com`:

```
$TTL 86400
@   IN  SOA ns1.example.com. admin.example.com. (
            2025011101 ; Serial
            3600       ; Refresh
            1800       ; Retry
            1209600    ; Expire
            86400 )    ; Minimum TTL

    IN  NS  ns1.example.com.
    IN  NS  ns2.example.com.

@   IN  A   192.168.1.1
www IN  A   192.168.1.2
mail IN  A   192.168.1.3

@   IN  MX  10 mail.example.com.
    IN  TXT "v=spf1 include:_spf.google.com ~all"
```
