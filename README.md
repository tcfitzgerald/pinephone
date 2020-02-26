# pinephone
Things I want to remember for the pinephone

## Writing an image to the emmc
First, I put postmarketOS on an sdcard and booted the pinephone. Next, I used scp to copy the image I wanted to write to the emmc into my home folder on the pinephone.  Then I ssh'd into the pinephone and ran ```sudo dd if=ubuntu.img of=/dev/mmcblk2 bs=4096``` where "ubuntu.img" was a copy of the ubports image and mmcblk2 is the interal emmc on the pinephone.

## Writing an image to the sdcard from the emmc image
/dev/sdb is an example here, use the appropriate tools (e.g. ```lsblk```) to find the correct value to use here
```sudo dd if=image.img of=/dev/sdb```

## Erasing the sdcard to boot to emmc again
mmcblk0 is an example here, use the appropriate tools (e.g. ```lsblk```) to find the correct value to use here
```dd if=/dev/zero of=/dev/mmcblk0 bs=512 count=1```

## Calls / SMS on postmarketOS (as of 2/19/2020 - pine-pinephone-20200218-phosh.img)
from https://forum.pine64.org/showthread.php?tid=9201&pid=60702#pid60702

```
sudo apk add modemmanager
sudo ofonoctl poweron
sudo ofonoctl online
sudo ofonoctl wan --connect --append-dns
sudo /etc/init.d/modemmanager start
sudo rc-update add modemmanager
```
and then reboot
