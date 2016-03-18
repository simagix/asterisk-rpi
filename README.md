# Asterisk on Raspberry PI
Install Asterisk/FreePBX on Raspberry PI with Google Voice

### Installation
- Download image from http://www.raspberry-asterisk.org/downloads/
- Use Win32 Disk Imager to write image, https://sourceforge.net/projects/win32diskimager/
- Disable ipv6, edit /etc/exim4/update-exim4.conf.conf
```
disable_ipv6='true'
```
- Follow instructions from http://www.raspberry-asterisk.org/documentation/
- Configure Google Voice as a trunk on FreePBX, Connectivity->Google Voice.  Follow http://jermsmit.com/google-voice-setup-on-freepbx-and-asterisk-version-11/
