# Proyectodetelecomunicaciones
proyecto
# VPN SITE-TO-SITE
# Desarrollo
# Configuracion de Fortigate
- WAN:
Para la configuracion del fortigate se habilitaron dos interfaces las cuales serian para WAN y otra para LAN. Mediante la consola de comandos se configuro manualmente el puerto 1 para la interfaz WAN, esto se muestra en la siguiente imagen:

![Texto alternativo](https://files.catbox.moe/g4ghci.png)

![Texto alternativo](https://files.catbox.moe/g20xkp.png)

Como se observa en la imagen, le asignamos una direccion IP al puerto y le permitimos los protocolos que permitira.

- LAN:
Para la configuracion de la interfaz LAN se uniero los dos puertos que conectan las dos redes LAN para hacer uso del Software switch, el cual sirve para simplificar la comunicación entre dispositivos conectados a diferentes interfaces de FortiGate. De este modo tendran la misma Gateway y no habra problemas de comunicacion.

![Texto alternativo](https://files.catbox.moe/2ymm1y.png)

# Topologia
![Texto alternativo](https://files.catbox.moe/8jtdfy.png)
