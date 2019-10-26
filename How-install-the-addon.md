## Installing on Windows / MacOS / IOS / Linux / LibreELEC (Devices Raspberry PI, x86-64, etc...)
Download the repository zip file: [repository.castagnait-1.0.0.zip](https://github.com/castagnait/repository.castagnait/raw/master/repository.castagnait-1.0.0.zip)

If it is a device: copy this file to an USB flash drive or memory card, and connect it to the device

Now open Kodi and in the browser addon, choose _Install from zip file_, navigate to the download folder (or USB flash drive/memory card) and install: repository.castagnait-1.0.0.zip

Then choose _Install from repository_, select CastagnaIT repository and Netflix addon.

**Note to Linux distros (not for Ubuntu / Utuntu flavors)**<br/>
On some linux distributions some additional libraries are needed

In the terminal run these commands:<br/>
sudo apt install build-essential python-dev python-pip python-setuptools<br/>
pip install --user pycryptodomex

## Installing on OSMC (Devices Raspberry PI, Vero, etc...)
After installing OSMC and completing the configuration of the first boot, you must connect from the computer with a terminal software that support SSH connection type.

On MacOS you can use Terminal app, on Windows [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), on Linux use the “ssh” command.

You can find some detailed instruction on [OSMC WIKI](https://osmc.tv/wiki/general/accessing-the-command-line/)
To connect to OSMC, you need the IP address of device and user/password (default credentials on OSMC WIKI)

After establishing the connection, in the terminal run these commands:<br/>
sudo apt-get update<br/>
sudo apt-get dist-upgrade<br/>
sudo apt-get install python-crypto<br/>
sudo apt-get install build-essential python-pip<br/>
sudo pip install -U setuptools<br/>
sudo pip install wheel<br/>
sudo pip install pycryptodomex==3.8.2<br/>
wget https://github.com/castagnait/repository.castagnait/raw/master/repository.castagnait-1.0.0.zip

Now open Kodi and in the browser addon, choose _Install from zip file_, navigate to the home folder and install: repository.castagnait-1.0.0.zip

Then choose _Install from repository_, select CastagnaIT repository and Netflix addon.