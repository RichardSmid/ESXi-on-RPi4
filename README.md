# ESXi-on-RPi4

### 1. We need to update the Raspberry pi.
```
sudo rpi-eeprom-update
```
```
sudo rpi-eeprom-update -a
```
### 2. After updating our Pi, we are going to power it off.
``` 
Sudo shutdown now
```
### 3. Wipe the sd card.

Take the sd card out and wipe it with Raspberry pi imager.

### 4. Download and extract the firmware.

[Latest Raspberry Pi Firmware](https://bit.ly/2HpIaG6)

[UEFI Raspberry Pi Firmware](https://bit.ly/3jota8D)

In the extracted file master, go into the boot folder and copy its contents onto the sd card.

### 5. On the sd card, remove all the kernelX.img files.
![image](https://user-images.githubusercontent.com/32524000/109423402-7dca2600-79df-11eb-865b-f4e48f63e614.png)


