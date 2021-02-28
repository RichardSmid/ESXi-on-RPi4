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
In the extracted UEFI firmware folder, copy its contents onto the sd card.

### 5. On the sd card, remove all the kernelX.img files.
![image](https://user-images.githubusercontent.com/32524000/109423402-7dca2600-79df-11eb-865b-f4e48f63e614.png)

### 6. Replace the config.txt file with the config.txt file provided in this repository.

### 7. Eject the sd card and plug it into the RPi.

### 8. Prepare a usb stick for the ESXi install.

[ESXi iso download](https://bit.ly/2J0bSCn)

Flash the usb stick with the image using one of theese tools.

[Rufus-Windows](https://bit.ly/3jvIVKV)

[Balena Etcher-Mac/Linux](https://bit.ly/35w8p5X)

### 9. Installing ESXi on the RPi.

Prepare your keyboard, because you are going to have to be quick.
Check, that you have both the usb and the sd card plgged in to the RPi.
Power it up, and immediately start hiting the esc key on your keyboard.

After the menu has appeared, navigate down to the Device Manager tab, and select it.
Scroll down to Raspberry pi Configuration, then to advanced configuration.
In advanced configuration, change the enabled Limit RAM to 3 GB from enabled to disabled.
Save the configuration.

Get back to the first page of the menu, and select continue.

The Pi is going to reboot now, after it reboots, you will need to start hitting the esc key again, to enter the menu again.
Scroll down to the Boot Manager tab, select it.
In boot manager, select your usb drive and hit enter.
After you hit enter, press shift+o immediately.
after the "runweasel cdromBoot" type in:
```
autoPartitionOSDataSize=8192
```
Hit enter, and a yellow screen should appear.
Plug in the other, bigger usb stick.
In the menu, sellect the usb stick.
Continue with the installation, by filling in all your data.


![image](https://user-images.githubusercontent.com/32524000/109424799-976e6c00-79e5-11eb-84e5-77d2e47bf21e.png)
After you see this screen, remove the smaller usb stick, that you used to install ESXi.
After you unplugged it, select reboot and hit enter.

### 10. Change the boot order, to always boot from the bigger usb stick.

After the pi reboots, start hitting the esc key again.
In the menu, select boot maintenance manager, then select boot options, and finaly change boot order.
Move the big usb stick to the top of the list, then save and reboot.

### 11. Connect to the Raspberry Pi.

In the yellow part of the screen, you should see your IP address, which you are going to use to acces the ESXi managment interface.
Type the IP address into your browser, login with the default username root and the password you set during the set-up.

### 11. Spin up your first vm.
