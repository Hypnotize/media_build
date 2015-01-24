This is a copy of the real media_build.git hosted on linuxtv.org

Install it by

- git clone https://github.com/Hypnotize/media_build.git
- ./build
- make
- sudo make install

In case of errors, like "No rule to make target 'modules'", make sure that your kernel headers are installed.
If not simply type:

- cd /usr/src
- Ask for root privileges by typing "sudo -s" and type in the password

- apt-get install linux-headers-$(uname -r)
- rm -rf /lib/modules/YOURKERNEL/build
- rm -rf /lib/modules/YOURKERNEL/src
- ln -s /usr/src/YOURKERNEL /lib/modules/YOURKERNEL/build
- ln -s /usr/src/YOURKERNEL /lib/modules/YOURKERNEL/src
- cp /boot/config-YOURKERNEL /usr/src/YOURKERNEL/.config

And then retry as normal user:
- cd /path/to/media_build/
- make distclean
- make clean
- ./build
- make
- sudo make install

Then reboot, your DVB-T device should be listed under /dev/dvb/ like "adapter0"
