Due to some changes in the website (we think about new anti-bot protections)
login with E-Mail/Password could cause "Incorrect password" error, even when the credentials are correct.

Then to avoid this problem a new login method has been added, the _Authentication key_.

The Authentication key is a file created by a software (or script).
This software will open the web browser in your computer, and will ask you to login in to Netflix web page.

After the login in the web page, the software will create the Authentication key file, and provide you of a PIN.<br/>
With this file+PIN (the password will be still required) you can login on any device (or system) where you have installed Kodi with Netflix add-on and so bypass the problem of "Incorrect password" error.

## How to get the file NFAuthentication.key and the PIN

To create this file and get the PIN, you need to use one of the following software.

You can create this file from any _Personal Computer (desktop / laptop)_, no matter what operating system you use (and Kodi is not needed).

<details>
<summary><b>For Windows</b><sup> [click to expand]</sup></summary>
<p>

**PREREQUISITE**: Chrome browser installed

**INSTRUCTIONS**: Download the zip and extract the folder, then run the software and follow the instructions on screen. After you have created the file, you have to open it, with Netflix add-on by choosing the login with "Authentication key". Remember to delete the Authentication key file after login.

**DOWNLOAD**: [NFAuthenticationKey_Windows.zip](https://www.dropbox.com/sh/80zv4umiiyx8ok1/AAABi-vk9CKNNXvpmzkCRTiIa?dl=0) (Google may report incorrectly as malware, press continue and ignore it)

</p>
</details>

<details>
<summary><b>For Linux and MacOS</b><sup> [click to expand]</sup></summary>
<p>

**PREREQUISITE**: A web browser is required, supported browsers: _Chrome, Chromium, Brave Browser_

**INSTRUCTIONS**: Download the zip, extract the folder and open this folder with the Terminal/Console. Then run the following commands.

Install these python packages:<br/>
`pip install pycryptodomex` (or pip3)<br/>
`pip install websocket-client` (or pip3)

After run the script:<br/>
`python NFAuthenticationKey.py` (or python3)<br/>
Follow the instructions on screen, after you have created the file, you have to open it with Netflix add-on by choosing the login with "Authentication key". Remember to delete the Authentication key file after login.

**DOWNLOAD**: [NFAuthenticationKey_Linux.zip](https://www.dropbox.com/sh/ls3veptflvneub1/AABz9Tt3EqKUb90PQXNarNxga?dl=0)

</p>
</details>

#### Disclaimer
All the Software, Script and source code available on GitHub are provided "as is" without warranty of any kind, either express or implied. Use at your own risk. The use of the software is done at your own discretion and risk with the agreement that you will be solely responsible for any damage resulting from such activities and you are solely responsible for adequate data protection.

### Links reported as malware/phishing problem

For details read here: https://github.com/CastagnaIT/plugin.video.netflix/issues/917