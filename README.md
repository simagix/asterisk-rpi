# Asterisk on Raspberry PI
Install Asterisk/FreePBX on Raspberry PI with Google Voice.

### Motivation
I pay $30+ a month for a VoIP BYOD service, including selected World calling plan.  I already have Asterisk in place at home but has to maintain a VM off Xen.  With the powerful combination of Asterisk, Raspberry PI, and Google Voice, the cost is greatly reduced.

### Installation
- Download image from http://www.raspberry-asterisk.org/downloads/
- Use Win32 Disk Imager to write image, https://sourceforge.net/projects/win32diskimager/
- Disable ipv6, edit /etc/exim4/update-exim4.conf.conf
```
disable_ipv6='true'
```
- Install/configure exim4, http://www.sbprojects.com/projects/raspberrypi/exim4.php
- Follow instructions from http://www.raspberry-asterisk.org/documentation/
- Configure Google Voice as a trunk on FreePBX, Connectivity->Google Voice.  Follow http://jermsmit.com/google-voice-setup-on-freepbx-and-asterisk-version-11/
 
### After Restart
After restart (and module upgrades), reboot doesn't restart amportal.  The command amportal is replaced by fwconsole.  Use the following commands to restart asterisk
```
chmod +x /usr/sbin/fwconsole
fwconsole chown
fwconsole restart
```

### Power Management
Turn off power management will resolve wifi timeout problem.
For Raspberry PI 2
```
echo "options 8192cu rtw_power_mgnt=0" >> /etc/modprobe.d/8192cu.conf
reboot
```
For Raspberry PI 3
```
# enable channel 12 and 13
iwlist wlan0 channel
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo rpi-update
sudo rpi-update 41f8b4812ad653abf321b8c54cb4bee57ebdb129
iwlist wlan0 channel
# turn off power management
sudo iwconfig wlan0 power off
reboot
```
