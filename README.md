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
 
