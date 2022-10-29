# VPN SITE-TO-SITE
Imprementacion de una red vpn site to site con fortinet y telnet
## Informacion
### Herramienta de simulacion utilizada

GNS3

 ![Texto alternativo](https://files.catbox.moe/7tbo2j.png)
 
VMWARE

 ![Texto alternativo](https://files.catbox.moe/tqs5bk.jpg)
 
 ### Fortigate
 Los Firewall Fortinet (también conocidos como firewalls de próxima generación NGFW o simplemente FortiGate) son dispositivos de seguridad que permiten la creación de redes seguras y proporcionan una protección amplia, integrada y automatizada contra amenazas emergentes y sofisticadas.
 
  ![Texto alternativo](https://files.catbox.moe/712msq.png)
  
   ### Que es vpn y por que
   
  ![Texto alternativo](https://files.catbox.moe/vilpr4.png)
  
   ### Que es una vpn site to site
   
   Un túnel VPN site-to-site permite establecer conexiones seguras entre múltiples ubicaciones geográficas a través de una red pública como Internet. Una VPN site-to-site extiende la red de una compañía, haciendo que los recursos informáticos de una ubicación estén disponibles en otras ubicaciones.
   
![Texto alternativo](https://files.catbox.moe/fpgxyq.png)

   ### Diferencias entre VPN Site-to-Site de las VPN de Acceso Remoto
   
   VPN Site-to-Site: Sirve para conectar redes LAN completas entre sí, esto es que el router servidor conectara a todos los clientes que están conectados a él, con todos los equipos que están conectados al router cliente.

VPN Acceso Remoto: Sirve para conectar a un usuario en particular con la red principal del router servidor.

 ### Protocolos utilizados
 
 - Vpn
 - Telnet
 - Voip
 - Ipsec
 - Isakmp
 ### Componentes utilizados
 
 - Maquinas virtuales
 - Foryigate
 - Router Cisko 3725
 - Switches

## Desarrollo
### Configuracion de Fortigate
#### WAN:
Para la configuracion del fortigate se habilitaron dos interfaces las cuales serian para WAN y otra para LAN. Mediante la consola de comandos se configuro manualmente el puerto 1 para la interfaz WAN, esto se muestra en la siguiente imagen:

 ![Texto alternativo](https://files.catbox.moe/g4ghci.png)

 ![Texto alternativo](https://files.catbox.moe/g20xkp.png)

 Como se observa en la imagen, le asignamos una direccion IP al puerto y le permitimos los protocolos que permitira.

#### LAN:
Para la configuracion de la interfaz LAN se uniero los dos puertos que conectan las dos redes LAN para hacer uso del Software switch, el cual sirve para simplificar la comunicación entre dispositivos conectados a diferentes interfaces de FortiGate. De este modo tendran la misma Gateway y no habra problemas de comunicacion.

 ![Texto alternativo](https://files.catbox.moe/2ymm1y.png)

### Configuracion de Router Cisco
#### WAN y LAN:
Se realizo la configuracion de los routers asignandoles una IP a cada puerto correspondiente, utilizando el protocolo dhcp para asignar IP en la interfaz de salida a la WAN y manualmente para la interfaz LAN.

 ![Texto alternativo](https://files.catbox.moe/f1ualv.png)

 Como se muestra en la imagen la asignacion de las IP y prueba de conexion.

#### Telnet:
 Se realizo la configuracion de telnet en los router cisco para poder acceder a su consola desde cualquier maquina que se encuentre en la red.

 ![Texto alternativo](https://files.catbox.moe/5xn0lu.png)
 
 Para el telnet se necesita ingresar un usuario y contraseña por el cual acceder desde la consola.
 
 #### VPN:
 Se realizo la configuracion del VPN entre los dos dispositivos Cisco, el cual se detalla la configuracion en las siguientes imagenes:
 
- Configurar una política para la fase 1 del túnel (ISAKMP)

![Texto alternativo](https://files.catbox.moe/8rpqw6.png)

- Configurar una ACL para definir qué tráfico se cifrará y un 'Conjunto de transformación' que dictará el cifrado y el hash para la fase 2 (IPSEC)

![Texto alternativo](https://files.catbox.moe/sbzx4t.png)

- Crear un 'mapa criptográfico' que se utiliza para aplicar la configuración de la fase 2 a una interfaz.

![Texto alternativo](https://files.catbox.moe/5euf6g.png)

- Aplicar ese mapa criptográfico a una interfaz, en este caso la WAN.

![Texto alternativo](https://files.catbox.moe/ykdy7a.png)

Esta configuracion se debe de realizar en los dos dispositivos Cisco, y realizar las pruebas para verificar el funcionamiento.

### Configuracion de VoIP
Para realizar esta central VoIP se utilizo una maquina con sistema operativo Linux para realizar las configuraciones de las direcciones para los telefonos virtuales.

Primero se debe de realizar la instalacion de la herramienta asterisk, el cual por medio de este es que se realizan las conexiones de paquetes SIP.

![Texto alternativo](https://files.catbox.moe/5pkkuv.png)

Luego debemos de crear las extensiones que se utilizaran, siendo en este caso 'ext101' y 'ext102'.

![Texto alternativo](https://files.catbox.moe/byv9l2.png)

Podemos observar que ya existen las direcciones que se crearon.

![Texto alternativo](https://files.catbox.moe/ba7bve.png)
![Texto alternativo](https://files.catbox.moe/rgcyfe.png)

Por ultimo utilizando la herramienta Zoiper, se colocan las direcciones creadas y se realizan las pruebas de conexion.

![Texto alternativo](https://files.catbox.moe/lc6oyz.png)

## Topologia
![Texto alternativo](https://files.catbox.moe/8jtdfy.png)
