# octoprint
nastavenie pre viac tliaciarni

**Nalogovat sa ako root**

`sudo -su`

`sudo su`

`cd /etc/init.d`

**Kopia povodnej verzie Octoprintu**

`sed s/octoprint/octoprint2/ < octoprint | sed s/OctoPrint/OctoPrint2/ | sed s/bin\\/octoprint2/bin\\/octoprint/ > octoprint2`

**nastavime opravnenia**

`chmod 755 octoprint2`

`cd /etc/default`

**nastavime port 5001 na druhy Octoprint**

`sed s/PORT=5000/PORT=5001/ < octoprint | sed s/HOST=127.0.0.1/HOST=0.0.0.0/ | sed s/\$PORT/\$PORT\ --basedir\ \\/home\\/pi\\/.octoprint2/ > octoprint2`

**update nastaveni**

`sudo update-rc.d octoprint2 defaults 99`

**restart**

`sudo reboot`

`SUBSYSTEM=="tty", ATTRS{idVendor}=="1a86", ATTRS{idProduct}=="7523", ATTRS{devpath}=="1.3", SYMLINK+="ttyANET"`

**Nastavenie path**
`sudo nano /etc/udev/rules.d/99-usb.rules`

**Ender 3**
idVendor=0403
idProduct=6001
0403 6001
0424 2514

**Ender CR-6 se**
idVendor=1a86
idProduct=7523

http://thomas-messmer.com/index.php/14-free-knowledge/howtos/79-setting-up-octoprint-for-multiple-printers
