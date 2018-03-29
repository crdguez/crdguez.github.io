---
layout: post
title: Mi configuración Retropie
tags: Raspberry Retropie
mathjax: true
eye_catch: 
---

En este artículo voy a escribir cómo he configurado retropie para que funcione con dos [mandos wiimote](https://github.com/RetroPie/RetroPie-Setup/wiki/Wiimote-Controller) y con una pantalla [waveshare 3.2"](https://www.waveshare.com/wiki/3.2inch_RPi_LCD_(B)).
Además le he puesto kodi y al poner kodi he puesto mandos snes para que me funcione.

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

## Quitar el marco negro

Para que funcione kodi he tenido que modificar el */boot/config.txt*:


```
# he tenido que comentar la siguiente línea para que no conmute a la salida hdmi
# hdmi_force_hotplug=1

```
Pero entonces me salía un borde negro que no aprovechaba toda la pantalla. Esto se corrige añadiendo al fichero */boot/config.txt*:

```
disable_overscan=1
```

## Aumentar el tamaño de letra de los menús

```
sudo nano /etc/emulationstation/themes/carbon/carbon.xml
```

Y allí cambiar todas las etiquetas *fontSize* a 0.05

Para el de **kodi**, he añadido 10 a todos los tamaños de las fuentes del skin *estuary*:

```
sudo nano /usr/share/kodi/addons/skin.estuary/xml/Font.xml
```

## kodi con mandos snes

Como he tenido problemas con los wiimotes, he configurados los mandos de la snes desde Kodi --> Settings --> System settings --> Input --> Configure attached controllers --> Descargar el add-on de control de snes y configurar los botones (yo he cambiado el A por el B)

## wiimotes en kodi
[enlace](https://trac.kodi.tv/ticket/17313) %parece complicado

## Documentación antigua para configurar los wiimotes:

Es importante configurar primero el teclado y luego añadir el wiimote desde *input config* del menú de retropie, antes de hacer el paso *Register Wiimotes Before Emulationstation Starts (continued)*

```
/opt/retropie/configs/all/autostart.sh 

rebootWithoutWiimotes=0 /home/pi/bin/attachwii.sh
emulationstation #auto




/home/pi/bin/attachwii.sh 

#!/bin/bash
sleep 1 # Wait until Bluetooth services are fully initialized
sudo modprobe uinput
hcitool dev | grep hci >/dev/null
if test $? -eq 0 ; then
    wminput -d -q -c  /home/pi/mywminput 00:19:1D:67:D8:26 > /dev/null 2>&1 &
  #wminput -d -c  /home/pi/mywminput 0C:FC:83:A9:17:6B &
else
    echo "Blue-tooth adapter not present!"
    exit 1
fi


nano mywminput


#Classic-Controller
Classic.Dpad.X = ABS_X
Classic.Dpad.Y = ABS_Y
Classic.LStick.X = ABS_HAT0X
Classic.LStick.Y = ABS_HAT0Y
Classic.RStick.X = ABS_HAT1X
Classic.RStick.Y = ABS_HAT1Y
Classic.A = BTN_A
Classic.B = BTN_B
Classic.X = BTN_X
Classic.Y = BTN_Y
Classic.Minus = BTN_SELECT
Classic.Plus  = BTN_START
Classic.Home  = BTN_MODE
Classic.L  = BTN_TL
Classic.R  = BTN_TR
Classic.ZL = BTN_TL2
Classic.ZR = BTN_TR2

#WiiMote
Wiimote.A   	= BTN_START
Wiimote.B   	= BTN_SELECT
Wiimote.Dpad.X  	= ABS_Y
Wiimote.Dpad.Y  	= -ABS_X
Wiimote.Minus   = BTN_Y
Wiimote.Plus	= BTN_X
Wiimote.Home	= BTN_MODE
Wiimote.1   	= BTN_B
Wiimote.2   	= BTN_A

#Nunchuk
Nunchuk.C = BTN_C
Nunchuk.Z = BTN_Z

Plugin.led.Led1 = 1
#Plugin.led.Led2 = 1
#Plugin.led.Led3 = 1
#Plugin.led.Led4 = 1




  
nano /opt/retropie/configs/all/retroarch.cfg

y 

nano /opt/retropie/emulators/retroarch/retroarch.cfg


#PLAYER 1
input_player1_joypad_index = "0"
input_player1_a_btn = "0"
input_player1_b_btn = "1"
input_player1_x_btn = "3"
input_player1_y_btn = "4"
input_player1_l_btn = "5"
input_player1_r_btn = "6"
input_player1_l2_btn = "7"
input_player1_r2_btn = "8"
input_player1_select_btn = "10"
input_player1_start_btn = "11"
input_player1_up_axis = "+1"
input_player1_down_axis = "-1"
input_player1_left_axis = "-0"
input_player1_right_axis = "+0"
input_player1_l_x_plus_axis = "+2"
input_player1_l_x_minus_axis = "-2"
input_player1_l_y_plus_axis = "-3"
input_player1_l_y_minus_axis = "+3"
input_player1_r_x_plus_axis = "+4"
input_player1_r_x_minus_axis = "-4"
input_player1_r_y_plus_axis = "-5"
input_player1_r_y_minus_axis = "+5"

#PLAYER 2
input_player2_joypad_index = "1"
input_player2_a_btn = "0"
input_player2_b_btn = "1"
input_player2_x_btn = "3"
input_player2_y_btn = "4"
input_player2_l_btn = "5"
input_player2_r_btn = "6"
input_player2_l2_btn = "7"
input_player2_r2_btn = "8"
input_player2_select_btn = "10"
input_player2_start_btn = "11"
input_player2_up_axis = "+1"
input_player2_down_axis = "-1"
input_player2_left_axis = "-0"
input_player2_right_axis = "+0"
input_player2_l_x_plus_axis = "+2"
input_player2_l_x_minus_axis = "-2"
input_player2_l_y_plus_axis = "-3"
input_player2_l_y_minus_axis = "+3"
input_player2_r_x_plus_axis = "+4"
input_player2_r_x_minus_axis = "-4"
input_player2_r_y_plus_axis = "-5"
input_player2_r_y_minus_axis = "+5"


#savestate_auto_save = true
#savestate_auto_load = true
input_enable_hotkey_btn = "10"
input_exit_emulator_btn = "11"
input_menu_toggle_btn = "3"






/home/pi/.emulationstation/es_input.cfg


<?xml version="1.0"?>
<inputList>
  <inputAction type="onfinish">
	<command>/opt/retropie/supplementary/emulationstation/scripts/inputconfiguration.s</command>
  </inputAction>
  <inputConfig type="joystick" deviceName="Nintendo Wiimote">
	<input name="start" type="button" id="11" value="1"/>
	<input name="up" type="axis" id="1" value="1"/>
	<input name="a" type="button" id="0" value="1"/>
	<input name="b" type="button" id="1" value="1"/>
	<input name="down" type="axis" id="1" value="-1"/>
	<input name="right" type="axis" id="0" value="1"/>
	<input name="x" type="button" id="3" value="1"/>
	<input name="select" type="button" id="10" value="1"/>
	<input name="y" type="button" id="4" value="1"/>
	<input name="left" type="axis" id="0" value="-1"/>
  </inputConfig>
</inputList>











nano /home/pi/.kodi/userdata/keymaps/joystick.xml

<?xml version="1.0" encoding="UTF-8"?>
<keymap>
  <global>
	<joystick name="Nintendo Wiimote">
  	<button id="1">Select</button>
  	<button id="2">Back</button>
  	<button id="11">ContextMenu</button>
  	<button id="12">Pause</button>
  	<button id="4">VolumeUp</button>
  	<button id="5">VolumeDown</button>
  	<axis id="1" limit="-1">Left</axis>
  	<axis id="1" limit="+1">Right</axis>
  	<axis id="2" limit="+1">Up</axis>
  	<axis id="2" limit="-1">Down</axis>
	</joystick>
  </global>
</keymap>







/opt/retropie/configs/all/retroarch-joypads/NintendoWiimote.cfg

input_device = "Nintendo Wiimote"
input_driver = "udev"
input_start_btn = "11"
input_exit_emulator_btn = "11"
input_up_axis = "+1"
input_a_btn = "0"
input_b_btn = "1"
input_reset_btn = "1"
input_down_axis = "-1"
input_right_axis = "+0"
input_state_slot_increase_axis = "+0"
input_x_btn = "3"
input_menu_toggle_btn = "3"
input_select_btn = "10"
input_enable_hotkey_btn = "10"
input_y_btn = "4"
input_left_axis = "-0"
input_state_slot_decrease_axis = "-0"

```

