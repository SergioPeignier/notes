# Raspberry pi configuration

## Install OS image in SD card

+ Download the image
+ Write it into the SD card
+ [see the steps](https://www.raspberrypi.org/documentation/installation/installing-images/)

## Set up Raspberry Pi Zero W with wifi

+ Open the SD card an add a blank file called `ssh` to authorize ssh connections
+ Modify the config.txt to enable hdmi connections
+ Need to allow automatic wifi connections http://weworkweplay.com/play/automatically-connect-a-raspberry-pi-to-a-wifi-network/
+ Need to create and write the supplicant file


http://raspberrypi.stackexchange.com/questions/62933/set-up-a-raspberry-pi-zero-w-without-monitor-or-ethernet-module
https://www.raspberrypi.org/forums/viewtopic.php?t=50312&p=416523
http://raspberrypi.stackexchange.com/questions/62888/rp-sd-card-wlan/62899#62899
https://www.raspberrypi.org/documentation/remote-access/ip-address.md

http://blog.gbaman.info/?p=699




# Robot
https://www.usna.edu/Users/cs/crabbe/SI475/current/vehicles.pdf
http://researcher.watson.ibm.com/researcher/files/us-jconnell/jhc-muram.pdf


# otras cosas

https://www.amazon.es/s/ref=nb_sb_noss?__mk_es_ES=ÅMÅŽÕÑ&url=search-alias%3Daps&field-keywords=Raspberry+Pi+zero+Lcd+Touch+Screen&rh=i%3Aaps%2Ck%3ARaspberry+Pi+zero+Lcd+Touch+Screen
https://www.kubii.fr/es/pantallas-pitft-raspberry-pi/1131-pantalla-tactil-oficial-7-800x480-640522710829.html


# graphic interface with computer https://www.raspberrypi.org/documentation/remote-access/vnc/

# sudo raspi-config

# Change the image resolution with vcnc:
edit /boot/config.txt and remove # from the framebuffer lines to get 1280x720
You have to reboot to see change

# Overclocking: https://es.wikipedia.org/wiki/Overclocking