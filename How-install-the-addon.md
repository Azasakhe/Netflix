### Prerequisites
* A devices compatible with Kodi (Apple iOS/tvOS are not supported)
* _Suggested_ Kodi 19 or above (for Kodi 18 read below)
* InputStream Adaptive add-on *1 *2
* Pycryptodome python library *1 *2
* InputStream Helper add-on *2
* Widevine CDM library *2
* For Linux operative systems, Python version 3.7 or higher is required (warning python 3.10.3 / 3.10.4 is bugged)

<sup>
*1 On some linux systems a manual installation is required<br/>
*2 Automatically installed
</sup>

### To read before install

#### The login could cause "Incorrect password" error
Due to some changes in the website (about new anti-bot protections) the login with E-Mail/Password could cause "Incorrect password" error, even when the credentials are correct. We provide an alternative to the standard login, please read [[Login with Authentication key]] page.

#### Mobile plan
This add-on **not** support Mobile plan.

#### Add-on for Kodi 18

**Kodi 18 is EOL. This add-on is compatible but will only receive _maintenance fixes_, no support will be provided. Due to recent Netflix changes the Kodi 18 version _may no longer support 1080P and 4K and this cannot be fixed_**, we highly recommend the upgrade to Kodi 19 or above.

#### Android
This add-on works with most _Netflix certified_ android devices, but video playback is not guaranteed on all models of android devices, causing playback errors.

#### Ubuntu (linux) use Kodi version from Ubuntu Software Center
This add-on is not full compatible with the Kodi version from _Ubuntu Software Center_ (can be identified from the Kodi main screen by the logo `Kodi from debian`), please uninstall it and follow the official Kodi install instructions on Kodi website.

---

<details>
<summary><b>How to installing on: Windows / MacOS / Android / LibreELEC / CoreELEC</b><sup> [click to expand]</sup></summary>
<p>

Download the Repository zip file `repository.castagnait-2.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

If you are using an external device: copy this file to an USB flash drive or memory card and connect it to the device

* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home/downloads folder (or USB flash drive/memory card if you use an external device)<br/>
then install the repository file `repository.castagnait-2.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>



<details>
<summary><b>How to installing on: Linux distributions</b><sup> [click to expand]</sup></summary>
<p>

Download the Repository zip file `repository.castagnait-2.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

If you are using an external device: copy this file to an USB flash drive or memory card and connect it to the device

* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home/downloads folder (or USB flash drive/memory card if you use an external device)<br/>
then install the repository file `repository.castagnait-2.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

On some linux distributions additional libraries are needed (On Ubuntu and flavors are already installed)

In the terminal run these commands:

<pre>
FOR KODI 18 LEIA and 19 MATRIX:
sudo apt install build-essential python-pip
pip install --user pycryptodomex

NOTE FOR KODI 19:
If your linux distribution have installed Python 2 and 3 at same time, you will have to run these:
sudo apt install build-essential python-pip3
pip3 install --user pycryptodomex
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
FOR KODI 18 LEIA:
sudo apt-get update
sudo apt-get install build-essential python-pip python-crypto libnss3
sudo pip install pycryptodomex

FOR KODI 19 MATRIX:
sudo apt-get update
sudo apt-get install build-essential python3-pip python3-crypto libnss3
sudo pip3 install setuptools wheel
sudo pip3 install pycryptodomex
</pre>
* In the terminal run these commands to download the Repository zip:
<pre>
wget https://github.com/castagnait/repository.castagnait/raw/kodi/repository.castagnait-2.0.0.zip
</pre>
* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home folder<br/>
then install the repository file `repository.castagnait-2.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>



<details>
<summary><b>How to installing on: Raspbian (Raspberry system)</b><sup> [click to expand]</sup></summary>
<p>

Download the Repository zip file `repository.castagnait-2.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

* Open Raspberry Terminal app and run these commands:
<pre>
FOR KODI 18 LEIA:
sudo apt update
sudo apt install build-essential python-pip libnss3 kodi-inputstream-adaptive
sudo pip install pycryptodomex

FOR KODI 19 MATRIX:
sudo apt update
sudo apt install build-essential python3-pip libnss3 kodi-inputstream-adaptive
sudo pip3 install pycryptodomex
</pre>
* Now open Kodi and follow the menu: `Add-ons browser` > `My add-ons` > `VideoPlayer InputStream`<br/>
so click on `InpuStream Adaptive` and enable it.
* Return to the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home/downloads folder<br/>
then install the repository file `repository.castagnait-2.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>



<details>
<summary><b>How to installing on: RetroPie (Raspberry system)</b><sup> [click to expand]</sup></summary>
<p>

Download the Repository zip file `repository.castagnait-2.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

Copy this file to an USB flash drive or memory card and connect it to the device

* Open RetroPie shell and run these commands:
<pre>
FOR KODI 18 LEIA:
sudo apt update
sudo apt install build-essential python-setuptools python-pip libnss3
sudo pip install wheel pycryptodomex
</pre>
* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the USB flash drive/memory card<br/>
then install the repository file `repository.castagnait-2.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>


<details>
<summary><b>How to installing on: QNAP - HD Station</b><sup> [click to expand]</sup></summary>
<p>

<ins>**NOTICE: THIS GUIDE IS INTENDED FOR THE EXCLUSIVE USE OF KODI 18.x**</ins>

**PREREQUISITE:** Mandatory HD Station app installed

* Connect to QNAP with a terminal (ssh or telnet) as admin<br/>
Instructions: https://www.qnap.com/en/how-to/knowledge-base/article/how-to-access-qnap-nas-by-ssh

* In the terminal run the following commands

Run this to locate the root OS folder

`getcfg SHARE_DEF defVolMP -f /etc/config/def_share.info`

Will be shown a path e.g.: /share/CACHEDEV1_DATA
(depending on the model and OS version the path may be different)

Now open the path on screen like:

`cd /share/CACHEDEV1_DATA`

and then open this sub-folder:

`cd /.qpkg/HD_Station`

Now that you are in the _HD_Station_ folder, run:

<pre>
chroot .
apt install python-pycryptodome
</pre>

Download the Repository zip file `repository.castagnait-2.0.x.zip` from the [GitHub Readme](https://github.com/CastagnaIT/plugin.video.netflix#quick-download-links)

Copy this file to an USB flash drive or memory card and connect it to the device

* Now open Kodi and in the Add-ons browser, choose _Install from zip file_
* Navigate in to the Home folder<br/>
then install the repository file `repository.castagnait-2.0.x.zip`
* Return to the add-ons browser and choose _Install from repository_<br/>
then select CastagnaIT repository and install Netflix add-on

</p>
</details>