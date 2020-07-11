### Prerequisites
* A devices compatible with Kodi (Apple iOS/tvOS are not supported)
* Kodi 18 or higher version
* InputStream Adaptive add-on *1 *2
* Pycryptodome python library *1 *2
* InputStream Helper add-on *2
* Widevine CDM library *2

<sup>
*1 On some linux systems manual installation is required<br/>
*2 Automatically installed
</sup>

### Notice

Android:
This add-on works with most _Netflix certified_ android devices, but video playback is not guaranteed on all models of android devices.

Fedora Linux:
The add-on can not be run on Kodi 18.x with Fedora 32 or higher (Python 2 is partially working [Retire Python 2](https://fedoraproject.org/wiki/Changes/RetirePython2)), then is mandatory install and use Kodi 19.

---

<details>
<summary><b>How to installing on: Windows / MacOS / Android / LibreELEC / CoreELEC</b><sup> [click to expand]</sup></summary>
<p>

Download the Repository zip file `repository.castagnait-1.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

If you are using an external device: copy this file to an USB flash drive or memory card and connect it to the device

* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home/downloads folder (or USB flash drive/memory card if you use an external device)<br/>
then install the repository file `repository.castagnait-1.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>



<details>
<summary><b>How to installing on: Linux distributions</b><sup> [click to expand]</sup></summary>
<p>

Download the Repository zip file `repository.castagnait-1.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

If you are using an external device: copy this file to an USB flash drive or memory card and connect it to the device

* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home/downloads folder (or USB flash drive/memory card if you use an external device)<br/>
then install the repository file `repository.castagnait-1.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

On some linux distributions additional libraries are needed (On Ubuntu and flavors are already installed)

In the terminal run these commands:

<pre>
sudo apt install build-essential python-dev python-pip python-setuptools
pip install --user pycryptodomex
</pre>

</p>
</details>



<details>
<summary><b>How to installing on: OSMC</b><sup> [click to expand]</sup></summary>
<p>

After installing OSMC and completing the configuration of the first boot, you must connect from the computer with a terminal software that support SSH connection type.

On MacOS you can use Terminal app, on Windows [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), on Linux use the “ssh” command.

You can find some detailed instruction on [OSMC WIKI](https://osmc.tv/wiki/general/accessing-the-command-line/)
To connect to OSMC, you need the IP address of device and user/password (default credentials on OSMC WIKI)

After establishing the connection with a terminal:

* In the terminal run these commands:
<pre>
sudo apt-get update
sudo apt-get dist-upgrade
sudo apt-get install python-crypto
sudo apt-get install build-essential python-pip
sudo pip install -U setuptools
sudo pip install wheel
sudo pip install pycryptodomex
</pre>
* In the terminal run these commands to download the Repository zip:
<pre>
USE THIS FOR KODI 18 LEIA:
wget https://github.com/castagnait/repository.castagnait/raw/master/repository.castagnait-1.0.1.zip
USE THIS FOR KODI 19 MATRIX:
wget https://github.com/castagnait/repository.castagnait/raw/matrix/repository.castagnait-1.0.0.zip
</pre>
* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home folder<br/>
then install the repository file `repository.castagnait-1.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>



<details>
<summary><b>How to installing on: Raspbian (Raspberry system)</b><sup> [click to expand]</sup></summary>
<p>

Download the Repository zip file `repository.castagnait-1.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

* Open Raspberry Terminal app and run these commands:
<pre>
sudo apt update
sudo apt install build-essential python-pip
sudo apt install python-setuptools
sudo pip install wheel
pip install pycryptodomex
sudo apt install kodi-inputstream-adaptive
</pre>
* Now open Kodi and follow the menu: `Add-ons browser` > `My add-ons` > `VideoPlayer InputStream`<br/>
so click on `InpuStream Adaptive` and enable it.
* Return to the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home/downloads folder<br/>
then install the repository file `repository.castagnait-1.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>



<details>
<summary><b>How to installing on: RetroPie (Raspberry system)</b><sup> [click to expand]</sup></summary>
<p>

Download the Repository zip file `repository.castagnait-1.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

Copy this file to an USB flash drive or memory card and connect it to the device

* Open RetroPie shell and run these commands:
<pre>
sudo apt update
sudo apt install build-essential python-setuptools python-pip
sudo pip install wheel pycryptodomex
sudo apt install libnss3
</pre>
* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the USB flash drive/memory card<br/>
then install the repository file `repository.castagnait-1.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>
