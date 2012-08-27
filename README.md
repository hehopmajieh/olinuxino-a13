olinuxino-a13 Notes:
======================================
1. Replacing U-boot using android adb

    ./adb shell

in adb shell:
    
    mkdir /sdcard/nanda
    
    mount -tvfat /dev/block/nanda /sdcard/nanda
    
    exit
push new uboot:

    ./adb push <path_to_uboot>/u-boot.bin /sdcard/nanda/u-boot.bin

Reboot:

    ./adb shell reboot

2.Flashing boot.img using fastboot
  
  Connect to Debug uart : 
  
    UEXT Pin2 -> GND
  
    UEXT Pin3 -> TX
  
    UEXT Pin4 -> RX
  
    Serial 115200, 8, N, 1
    
When uboot appears stop booting process pressing key on keyboard. 
Write fastboot on u- boot terminal
Go to dir with android SDK platform-tools and start fastboot
    
    ./fastboot boot <path_to_boot.img>/boot_sd.img

After flashing ends reboot device:

    ./fastboot reboot
    
3. SD Card image:
  Make two partitions :
  1.20MB ext2/3/4
  2.Rest
Extract image on partition 2:
Debian image aviable here :
    
        http://31.13.212.1/debian.tgz

extract it to root folder of mmc partition 2 :
      
      tar zxfv debian.tgz -C /<path_to_mount_point_>/







    
  