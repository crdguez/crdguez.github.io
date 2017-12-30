---
layout: post
title: Recetas para la Raspberry Pi
tags: Raspberry
mathjax: true
eye_catch: 
---

## Touchscreen

Tengo un pantalla táctil de 3.2 inch con el chip xp12046. Para manejarla he seguido esta documentación:

[Documentación](https://www.waveshare.com/wiki/3.2inch_RPi_LCD_(B))

## Sistemas operativos

### Sugar

He probado [Sugar](https://wiki.sugarlabs.org/go/Sugar_on_a_Stick/Raspberry_Pi) que parece que por fin funciona.

Para cargar la imagen en la sd he lanzado el siguiente comando:

```
xzcat Fedora-SoaS-armhfp-27-1.6-sda.raw.xz | sudo dd status=progress bs=4M of=/dev/sda
```
