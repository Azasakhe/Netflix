Due to some changes in the website (we think about new anti-bot protections)
login with E-Mail/Password could cause "Incorrect password" error, even when the credentials are correct.

Then to avoid this problem a new login method has been added, the _Authentication key_.

The Authentication key is a file created by a software (or script).
This software will open the web browser in your computer, and will ask you to login in to Netflix web page.

After the login in the web page, the software will create the Authentication key file, and provide you of a PIN.<br/>
You can use this file+PIN to login with the add-on and so bypass the problem of "Incorrect password" error.

## How to get the file NFAuthentication.key and the PIN

To create this file and get the PIN, you need to use one of the following software.

You can create this file from any _Personal Computer_, no matter what operating system you use.

The file created can be used to login on all type of devices/systems where the Netflix add-on is installed.

<details>
<summary><b>For Windows</b><sup> [click to expand]</sup></summary>
<p>

**PREREQUISITE**: Chrome browser installed

**INSTRUCTIONS**: Download the zip and extract the folder, then run the software and follow the instructions on screen. After you have created the file, you have to open it, with Netflix add-on by choosing the login with "Authentication key". Remember to delete the Authentication key file after login.

**DOWNLOAD**: [NFAuthenticationKey_Windows.zip](https://www.dropbox.com/sh/80zv4umiiyx8ok1/AAABi-vk9CKNNXvpmzkCRTiIa?dl=0)

</p>
</details>

<details>
<summary><b>For Linux</b><sup> [click to expand]</sup></summary>
<p>

**PREREQUISITE**: Chrome or Chromium browser installed

**INSTRUCTIONS**: Download the zip, extract the folder and open this folder with the Terminal/Console. Then run the following commands.

Install these python packages:
<pre>
pip install pycryptodomex
pip install websocket-client
</pre>

After run the script:
<pre>
python NFAuthenticationKey.py
or
python3 NFAuthenticationKey.py
</pre>
Follow the instructions on screen, after you have created the file, you have to open it with Netflix add-on by choosing the login with "Authentication key". Remember to delete the Authentication key file after login.

**DOWNLOAD**: [NFAuthenticationKey_Linux.zip](https://www.dropbox.com/sh/ls3veptflvneub1/AABz9Tt3EqKUb90PQXNarNxga?dl=0)

</p>
</details>

#### Disclaimer
All the Software, Script and source code available on GitHub are provided "as is" without warranty of any kind, either express or implied. Use at your own risk. The use of the software is done at your own discretion and risk with the agreement that you will be solely responsible for any damage resulting from such activities and you are solely responsible for adequate data protection.
