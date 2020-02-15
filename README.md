# pinephone
Things I want to remember for the pinephone

## Writing an image to the emmc
First, I put postmarketOS on an sdcard and booted the pinephone. Next, I used scp to copy the image I wanted to write to the emmc into my home folder on the pinephone.  Then I ssh'd into the pinephone and ran ```sudo dd if=ubuntu.img of=/dev/mmcblk2 bs=4096``` where "ubuntu.img" was a copy of the ubports image and mmcblk2 is the interal emmc on the pinephone.

