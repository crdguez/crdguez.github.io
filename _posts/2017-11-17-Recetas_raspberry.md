---
layout: post
title: Recetas para la Raspberry Pi
tags: Raspberry
mathjax: true
eye_catch: 
---

## Redimensionando la tarjeta SD

[Enlace](https://github.com/qrti/shrink)

## Touchscreen

Tengo un pantalla táctil de 3.2 inch con el chip xp12046. Para manejarla he seguido esta documentación:

[Documentación](https://www.waveshare.com/wiki/3.2inch_RPi_LCD_(B))

Para instalar retropie con esa pantalla he visto este [enlace](https://retropie.org.uk/forum/topic/4983/retropie-and-waveshare-3-2-b-screen) y ha funcionado. Lo que no ha funcionado ha sido el lanzamiento de kodi desde retropie, * **No:** (tengo que intentar el siguiente [enlace2](https://www.opendisplaycase.com/kodidisplayinfo-program.html))* . Igual funciona modificar el fichero [guisettings.xml](https://retropie.org.uk/forum/topic/2321/booting-into-kodi-black-screen-flashing-freezing/8). Al final lo que me ha funcionado ha sido modificar el */boot/config.txt* y poner:

```
#hdmi_force_hotplug=1
hdmi_ignore_hotplug=1
```

[Para que el estado en el que se me queda un juego se grabe](https://retropie.org.uk/docs/FAQ/#why-arent-my-in-game-saves-working-properly)

El Kodi queda un poco pequeño, para cambiar el tamaño de la fuente: [enlace](https://forum.kodi.tv/showthread.php?tid=195752)

Para spectrum: [enlace](https://www.fororaspberry.es/viewtopic.php?t=4566)

## Sistemas operativos

### Sugar

He probado [Sugar](https://wiki.sugarlabs.org/go/Sugar_on_a_Stick/Raspberry_Pi) que parece que por fin funciona.

Para cargar la imagen en la sd he lanzado el siguiente comando:

```
xzcat Fedora-SoaS-armhfp-27-1.6-sda.raw.xz | sudo dd status=progress bs=4M of=/dev/sda 
```
Para activar la wifi por temas de derechos:

`sudo curl https://raw.githubusercontent.com/RPi-Distro/firmware-nonfree/master/brcm80211/brcm/brcmfmac43430-sdio.txt -o /lib/firmware/brcm/brcmfmac43430-sdio.txt`

## Luces neopixel con controlador ws2801 para arduino antes de usarlas en la raspberry

[Libreria desarrollada por adafruit](https://github.com/adafruit/Adafruit-WS2801-Library)

Podemos descargarla en la carpeta de *Arduino/libraries* para poder compilar y subir a la placa desde el IDE de Arduino-

Los colores y pines los podemos ver en este [enlace](http://soloelectronicos.com/2017/05/07/como-detectar-la-combinacion-de-colores-de-una-tira-de-leds-ws2801/) -Gracias-

