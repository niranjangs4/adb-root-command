# adb-root-command
Quick Root Command references
adb pixel : https://dl.google.com/android/repository/platform-tools-latest-linux.zip

Nexus Images: https://developers.google.com/android/nexus/images#mysid

CWM: http://www.clockworkmod.com/rommanager/

Superuser: http://hosted.androidsu.com/superuser/

SuperSU: http://download.chainfire.eu/205/SuperSU/


Root Device
1) Unlock the bootloader (if locked):


```
Code:
adb reboot bootloader
fastboot oem unlock
```
2) Install Supersuer + Root (match the file names with the ones downloaded):

```
Code:
adb push Superuser-3.1.3-arm-signed.zip /sdcard/
adb reboot bootloader
fastboot boot recovery-clockwork-6.0.1.0-maguro.img
```
Flash Superuser: On device, select "install zip from sdcard", then "choose zip from sdcard" and select "Superuser-3.1.3-arm-signed.zip". Confirm install, then "+++++Go Back+++++" and "reboot system now".

3) Lock the bootloader (optional):

```
Code:
adb reboot bootloader
fastboot oem lock
```
Stock Device
1) Unlock the bootloader (if locked):

```
Code:
adb reboot bootloader
fastboot oem unlock
```
2) Install the image files (match the file names with the ones downloaded).
Commands are listed inside flash-all.sh shell script, validate them:

```
Code:
adb reboot bootloader
fastboot flash bootloader bootloader-maguro-primelc03.img
fastboot reboot-bootloader
fastboot flash radio radio-maguro-i9250xxlf1.img
fastboot reboot-bootloader
fastboot -w update image-takju-jro03c.zip
```

3) Lock the bootloader:

```
Code:
adb reboot bootloader
fastboot oem lock
```
Backup Device
```
Code:
adb backup -apk -shared -all -f backup.ab
```
