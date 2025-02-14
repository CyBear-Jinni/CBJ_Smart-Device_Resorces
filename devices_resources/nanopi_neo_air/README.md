# Setting Up NanoPi NEO Air With CyBear Jinni

<p>1. Install the <a href="https://drive.google.com/drive/u/1/folders/195TFucX-MwShKbvXsU5i5MoE85uCOjvg">OS image</a> into an sd card.</p>

<p>2. Insert the sd card to the NanoPi NEO Air device and connect it to the computer with USB to TTL Serial Cable/Console Cable.</p>

<p>3. Open the terminal and connect to it with the following command:</p>

`sudo screen /dev/ttyUSB0 115200`

After that it will ask you to choose new password for root.

<p>4. Update the device date with the command </p>

`sudo date -s "23 Sep 2020 16:01:50"`

<p>5. Create the file 'setup_new_smart_device.sh' on the device

`nano setup_new_smart_device.sh`

And copy the content from the file `setup_new_smart_device.sh` in the repository into that file.

The keyboard shortcuts to copy into nano text manager is ctrl+shift+v

Now replace the text wifiSsid to your wifi name and wifiPassword to your wifi password in the line

nmcli dev wifi connect wifiSsid password wifiPassword

And to save and exist press ctrl+x  and than press y to accept.

<p>6. Make the script executable by running the command </p>

`chmod +x setup_new_smart_device.sh`

<p>7. Run the script as root with the command</p>

`sudo ./setup_new_smart_device.sh`

and enter your password

<p>8. After the device have rebooted update the time again with does too commands (don't forget to change the time in the command to the correct time for you)</p>

`sudo date -s "23 Sep 2020 16:01:50"`

`sudo hwclock -w`

<p>10. Now it should run already but the os armbian for the NanoPi NEO Air currently does not have good cpu speed configuration by default.</p>

In order to let the device work range of lower speeds follow the following steps.    

`sudo armbian-config` --> System --> CPU --> 480000 -> 1008000
