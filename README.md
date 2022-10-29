# VPN SITE-TO-SITE
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

#### Telnet
 Se realizo la configuracion de telnet en los router cisco para poder acceder a su consola desde cualquier maquina que se encuentre en la red.

 ![Texto alternativo](https://files.catbox.moe/5xn0lu.png)
 
 Para el telnet se necesita ingresar un usuario y contraseña por el cual acceder desde la consola.

## Topologia
![Texto alternativo](https://files.catbox.moe/8jtdfy.png)
