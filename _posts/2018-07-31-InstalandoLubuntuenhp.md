---
layout: post
title: Instalando Lubuntu en un HP 15-bs088ns
tags: Lubuntu
mathjax: true
eye_catch: 
---

## Arrancar desde un usb

Pulsando *ESC* al encender accedemos a un menú que nos permite arrancar desde el *USB*.

## Primer problema: La wifi

Realtek y su hardware propietario. El caso es que la instalación no la reconoce.

Seguí el siguiente [enlace](https://h30434.www3.hp.com/t5/Notebook-Wireless-and-Networking/Realtek-8723DE-wifi-module-amp-Bluetooth-Linux-driver/td-p/6477307). De los dos métodos, el DKM porque el otro fallaba (había que modificar las fuentes para el kernel 4.15).

Además para poder activar el módulo tuve que desabilitar el *secure boot* de la BIOS (Con F10)



