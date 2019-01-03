---
layout: post
title: Soluciones a mis problemas con la instalación de Lubuntu en mi ASUS Z9200U
tags: Lubuntu
mathjax: true
eye_catch: 
---

## Primer problema: La wifi

La tarjeta wifi es una Broadcom Limited BCM4318 [AirForce One 54g] 802.11g Wireless LAN Controller (rev 02)

[Fuente donde está la solución](https://blog.desdelinux.net/solucionar-problema-con-wifi-broadcom-43xx-en-ubuntu-despues-de-la-actualizacion/)

En realidad, lo único que hice fue (OJO, probar primero sin instalar bcmwl*, para evitar lo que tuve que hacer al final)

```
sudo apt-get purge b43-fwcutter firmware-b43-installer firmware-b43-lpphy-installer firmware-b43legacy-installer bcmwl*
sudo apt-get install b43-fwcutter firmware-b43-installer bcmwl*
```



Finalmente, después de reiniciar, activar el módulo:

```
sudo modsprobe -r b43 bcma
sudo modprobe b43
```

Bueno, tuve un pequeño problema y era que el módulo no lo cargaba  al reiniciar, lo tenía que hacer a mano:

[https://askubuntu.com/questions/135297/how-do-i-make-modprobe-permanent](https://askubuntu.com/questions/135297/how-do-i-make-modprobe-permanent)

```
echo "b43" | sudo tee -a /etc/modules
```



Además, tenía el modulo b43 en una blacklist, por lo que no lo cargaba: Tuve que comentar la línea que lo metía en el archivo (ver autorespuesta de [https://askubuntu.com/questions/703843/etc-modules-not-working-as-expected](https://askubuntu.com/questions/703843/etc-modules-not-working-as-expected)): 

```
sudo nano /etc/modprobe.d/blacklist-bcm43.conf
```



## Segundo problema: La resolución de la pantalla

La tarjeta grafica es Silicon Integrated Systems [SiS] 661/741/760 PCI/AGP or 662/761Gx PCIE VGA Display Adapter

[Fuente donde está la solución](https://askubuntu.com/questions/455888/low-resolution-on-lubuntu-14-04-sis)

## No tengo capturador de pantalla

Esto lo he solucionado con el comando scrot -s desde ejecutar

## Autologin lightdm

[https://askubuntu.com/questions/967837/how-to-enable-autologin-on-lubuntu-16-04-lts-lightdm/967838](https://askubuntu.com/questions/967837/how-to-enable-autologin-on-lubuntu-16-04-lts-lightdm/967838)



## PCManFM no tiene opción para compartir carpetas

`sudo apt-get install system-config-samba`

El comando anterior me da una GUI para configurar las carpetas compartidas. Desde el menú no me ha funcionado, he tenido que lanzarlo desde la línea de comandos:

`sudo system-config-samba`

 En caso que falle:

 `sudo touch /etc/libuser.conf`

 Y volver a ejecutar el comando lanzador
