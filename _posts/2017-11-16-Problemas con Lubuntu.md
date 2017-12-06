---
layout: post
title: Soluciones a mis problemas con la instalación de Lubuntu en mia ASUS Z9200U
tags: Lubuntu
mathjax: true
eye_catch: 
---

## Primer problema: La wifi

La tarjeta wifi es una Broadcom Limited BCM4318 [AirForce One 54g] 802.11g Wireless LAN Controller (rev 02)

[Fuente donde está la solución](https://blog.desdelinux.net/solucionar-problema-con-wifi-broadcom-43xx-en-ubuntu-despues-de-la-actualizacion/)

## Segundo problema: La resolución de la pantalla

La tarjeta grafica es Silicon Integrated Systems [SiS] 661/741/760 PCI/AGP or 662/761Gx PCIE VGA Display Adapter

[Fuente donde está la solución](https://askubuntu.com/questions/455888/low-resolution-on-lubuntu-14-04-sis)

## No tengo capturador de pantalla

Esto lo he solucionado con el comando scrot -s desde ejecutar

## PCManFM no tiene opción para compartir carpetas

`sudo apt-get install system-config-samba`

El comando anterior me da una GUI para configurar las carpetas compartidas. Desde el menú no me ha funcionado, he tenido que lanzarlo desde la línea de comandos:

`sudo system-config-samba`
 
 En caso que falle:
 
 `sudo touch /etc/libuser.conf`
 
 Y volver a ejecutar el comando lanzador
