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

## Topologia
![Texto alternativo](https://files.catbox.moe/8jtdfy.png)
