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

`sudo update-rc.d octoprint2 default 99`

**restart**

`sudo reboot`

