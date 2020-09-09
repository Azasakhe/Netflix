Due to some changes in the website (we think about new anti-bot protections)
login with E-Mail/Password could cause "Incorrect password" error, even when the credentials are correct.

The login with Authentication key is a method that allow you to login in to your account by using:<br/>
NFAuthentication.key file + PIN + Account password<br/>
and so "bypass" these restrictions.

## How to get the file NFAuthentication.key and the PIN

To create this file and get the PIN, you need to use one of the following software.

The file created cointains part of your account data that will be encrypted, and can be used to login on all type of devices/systems where the Netflix add-on is installed.

The file will become no more valid after 5 days, remember to delete it after his use.

<details>
<summary><b>For Windows</b><sup> [click to expand]</sup></summary>
<p>

**PREREQUISITE**: Chrome browser installed

**INSTRUCTIONS**: Download the zip and extract the folder, then run the software and follow the instructions on screen. After you have created the file, you have to open it, with Netflix add-on by choosing the login with "Authentication key".

**DOWNLOAD**: [NFAuthenticationKey_1.0.1.0.zip](https://www.dropbox.com/s/3oi2j5grvwxn29q/NFAuthenticationKey_1.0.1.0.zip?dl=0)

</p>
</details>

<details>
<summary><b>For Linux</b><sup> [click to expand]</sup></summary>
<p>

**PREREQUISITE**: Chrome or Chronium browser installed

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
Follow the instructions on screen, after you have created the file, you have to open it with Netflix add-on by choosing the login with "Authentication key".

**DOWNLOAD**: [NFAuthenticationKeyLinux_1.0.0.zip](https://www.dropbox.com/s/qkoe0n3a2rx10go/NFAuthenticationKeyLinux_1.0.0.zip?dl=0)

</p>
</details>

#### Disclaimer
All the Software, Script and source code available on GitHub are provided "as is" without warranty of any kind, either express or implied. Use at your own risk. The use of the software is done at your own discretion and risk with the agreement that you will be solely responsible for any damage resulting from such activities and you are solely responsible for adequate data protection.
