### Prerequisites
* A devices compatible with Kodi (Apple iOS/tvOS is not supported by this add-on)
* Kodi 18 or higher version
* Inputstream.adaptive addon *1
* Cryptdome python library *1 *2
* Inputstream.helper addon *1
* Widevine CDM library *1

*1 Automatically installed<br/>
*2 You need to install it manually only on some linux systems

### Installing on Windows / MacOS / Linux (Android and linux distributions) / LibreELEC
Download the repository zip file: [repository.castagnait-1.0.1.zip](https://github.com/castagnait/repository.castagnait/raw/master/repository.castagnait-1.0.1.zip)

If it is a device: copy this file to an USB flash drive or memory card, and connect it to the device

Now open Kodi and in the browser addon, choose _Install from zip file_, navigate to the download folder (or USB flash drive/memory card) and install: repository.castagnait-1.0.1.zip

Then choose _Install from repository_, select CastagnaIT repository and Netflix addon.

**Note to Linux distros (NOT for: Ubuntu, Utuntu flavors, Android or LibreELEC)**<br/>
On some linux distributions some additional libraries are needed

In the terminal run these commands:<br/>
<pre>
sudo apt install build-essential python-dev python-pip python-setuptools
pip install --user pycryptodomex
</pre>

### Installing on OSMC
After installing OSMC and completing the configuration of the first boot, you must connect from the computer with a terminal software that support SSH connection type.

On MacOS you can use Terminal app, on Windows [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), on Linux use the “ssh” command.

You can find some detailed instruction on [OSMC WIKI](https://osmc.tv/wiki/general/accessing-the-command-line/)
To connect to OSMC, you need the IP address of device and user/password (default credentials on OSMC WIKI)

After establishing the connection, in the terminal run these commands:
<pre>
sudo apt-get update
sudo apt-get dist-upgrade
sudo apt-get install python-crypto
sudo apt-get install build-essential python-pip
sudo pip install -U setuptools
sudo pip install wheel
sudo pip install pycryptodomex
wget https://github.com/castagnait/repository.castagnait/raw/master/repository.castagnait-1.0.1.zip
</pre>

Now open Kodi and in the browser addon, choose _Install from zip file_, navigate to the home folder and install: repository.castagnait-1.0.1.zip

Then choose _Install from repository_, select CastagnaIT repository and Netflix addon.

### Installing on Raspbian (Raspberry system)
Download the repository zip file: [repository.castagnait-1.0.1.zip](https://github.com/castagnait/repository.castagnait/raw/master/repository.castagnait-1.0.1.zip)

Open Raspberry Terminal app and run these commands:
<pre>
sudo apt update
sudo apt install build-essential python-pip
sudo apt install python-setuptools
sudo pip install wheel
pip install pycryptodomex
sudo apt install kodi-inputstream-adaptive
</pre>

Now open Kodi and follow the menu: `Add-ons` > `My add-ons` > `VideoPlayer InputStream`<br/>
so click on `InpuStream Adaptive` and enable it.

Return to the add-on browser, choose _Install from zip file_, navigate to the download folder and install: repository.castagnait-1.0.1.zip

Then choose _Install from repository_, select CastagnaIT repository and Netflix addon.

### Installing on RetroPie (Raspberry system)
Download the repository zip file [repository.castagnait-1.0.1.zip](https://github.com/castagnait/repository.castagnait/raw/master/repository.castagnait-1.0.1.zip), then copy this file to an USB flash drive or memory card, and connect it to the device

Open RetroPie shell and run these commands:
<pre>
sudo apt update
sudo apt install build-essential python-setuptools python-pip
sudo pip install wheel pycryptodomex
sudo apt install libnss3
</pre>

Now open Kodi and go to the add-on browser, choose _Install from zip file_, navigate to USB flash drive/memory card folder and install: repository.castagnait-1.0.1.zip

Then choose _Install from repository_, select CastagnaIT repository and Netflix addon.
