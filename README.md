# Home Assistant Touch Screen on Raspberry Pi 4B+
- Below is a list of steps to install and configure a Home Assistant touchscreen display to run HASS in kiosk mode

## Hardware
- Raspberry Pi 4B+ 4Gb
- Raspberry Pi Official 7" Display
- KKSB Raspberry Pi 4B 7 Inch Touchscreen Case  

## Installation Steps:
- Install RaspianOS 64bit

- Select System Options > Boot / Auto Login > Desktop Autologin: Desktop GUI, automatically logged in as 'pi' user.
``` bash
$ sudo apt install wtype
$ sudo apt update && sudo apt upgrade
$ sudo nano .config/wayfire.ini
```

- Paste in the following:  
``` bash
[autostart]
panel = wfrespawn wf-panel-pi  
background = wfrespawn pcmanfm --desktop --profile LXDE-pi  
xdg-autostart = lxsession-xdg-autostart  
chromium = chromium-browser [https://raspberrypi.com https://time.is/London](https://hass.srv.playantares.com/dashboard-lights/0?kiosk=true) --kiosk --noerrdialogs --disable-infobars --no-first-run --ozone-platform=wayland --enable-features=OverlayScrollbar --start-maximized  
screensaver = false  
dpms = false
```
- Continue with the following steps
``` bash
$ cd /usr/share/plymouth/themes/pix  
$ sudo wget https://antaresnetwork.com/resources/icon.png  
$ sudo rm splash.png  
$ sudo cp icon.png splash.png  
$  sudo plymouth-set-default-theme --rebuild-initrd pix  
$ sudo reboot
```
- Sign in to home assistant
``` bash
  $ sudo reboot
```

### My Website
https://nathen418.com
