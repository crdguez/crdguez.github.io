---
layout: post
title: Mi configuración Retropie para usar el gamehat
tags: Raspberry Retropie
mathjax: true
eye_catch: 
---

En este artículo voy a escribir cómo he configurado retropie para que funcione con la [GameHat de WaveShare](https://www.waveshare.com/game-hat.htm) con su [wiki](https://www.waveshare.com/wiki/Game_HAT). Desde allí descargué la imagen preconfigurada para que funcione todo. Bueno, casi:


## Kodi

* Desde el menú de configuración de Retropie, gestión de paquetes opt, podemos instalar el Port de Kodi
* El **mando**: Kodi no reconoce el mando. Hay que ir a *settings-input-attached_devices* ahí con el ratón, pulsar la primer tecla a mapear, una vez seleccionada, pulsaremos la tecla de nuestro teclado a mapear. Así sucesivamente.
* El **tamaño de fuente**: Los menús se ven pequeños en la pantalla. Podemos editar

```
sudo nano /usr/share/kodi/addons/skin.estuary/xml/Font.xml

```
Yo he sumado 5 a cada tamaño de la fuente por default y ya me va bien
* Ver la TV por internet: Por defecto, retropie instala kodi sin PVR. Yo he ejecutado:
```
sudo apt-get install kodi-pvr-iptvsimple
```

