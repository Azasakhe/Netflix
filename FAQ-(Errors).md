Add-on errors:
* [Email or password is incorrect](#email-or-password-is-incorrect)
* [MSL Error: This title is not available to watch instantly](#msl-error-This-title-is-not-available-to-watch-instantly)
* [MSL Error: Request failed validation during key exchange](#msl-error-Request-failed-validation-during-key-exchange)
* [MSL Error: Entity used incorrect key exchange data type](#msl-error-Entity-used-incorrect-key-exchange-data-type)
* [MSL Error: Entity used incorrect user authentication data type](#msl-error-Entity-used-incorrect-user-authentication-data-type)
* [MSL Error: Email or password is incorrect](#msl-error-email-or-password-is-incorrect)
* [MSL Error: User must login again](#msl-error-user-must-login-again)
* [HTTPError: 403 Client Error: Forbidden for url ...](#httperror-403-client-error-forbidden-for-url-)
* [HTTPError: 500 Server Error](#httperror-500-server-error)
* [HTTPError: 504 Server Error](#httperror-504-server-error)
* [Exception: Connection error](#exception-connection-error)
* [MSL Error: Request blacklisted by key exchange service](#msl-error-request-blacklisted-by-key-exchange-service)
* [Addon Signals call timeout](#addon-signals-call-timeout)
* [It was not possible to get the data from Widevine CryptoSession](#it-was-not-possible-to-get-the-data-from-widevine-cryptosession)

## Add-on errors

### Email or password is incorrect

There are several reasons because this problem is presented, the known cases are:

- Due to new Netflix anti-bot protection<br/>
For more info read [Login with Authentication key](https://github.com/CastagnaIT/plugin.video.netflix/wiki/Login-with-Authentication-key) page

- Netflix has automatically reset your password for suspicious activity (notice by e-mail), or you have changed the password while Kodi was still running<br/>
You can try solve with these steps:
1) Try to change your password (again or try skip this step)
2) Reboot Kodi
3) Open Netflix add-on, should be asked to enter the new credentials, if no credential are asked open add-on settings and Logout

### MSL Error: This title is not available to watch instantly

In this case Netflix says to log out https://help.netflix.com/en/node/109329.<br/>
Open add-on settings and choose `Logout`.

If the problem persists:

#### On Android:

Check if the ESN is equal to the official Netflix app, click on `Show ESN` in add-on `Expert` setting and compare with the ESN in android Netflix app settings. Only the first part of the code is important, last missing part ignore it.

If the ESN is different:

* On Kodi v18:<br/>
Try to set `Widevine L3` on add-on `Expert` settings and try to play a video,
if this not works try type the correct ESN in `Manual ESN` field of add-on `Expert` setting.

* On Kodi v19 or above:<br/>
From add-on `Expert` settings select `ESN / Widevine settings`,
On Widevine section select `Force L3`, press OK button and try to play a video,
if this not works try type the correct ESN by selecting `Change ESN` button of the same window.

#### On all other systems:

Try reinstall Widevine CDM:<br/>
Open add-on settings (by context menu on the add-on icon), then go to `Expert` page and choose `InputStream Helper settings`, a new window will be opened, then choose `(Re)install Widevine CDM`. When done reboot Kodi or the device.

#### Are you trying to play videos exported to the Kodi library?

In this case, you may be playing videos exported from a different Netflix profile than the one selected to play the video. Then select the correct Netflix profile.

_**If these solutions do not work, please do not open an Issue, there are no other known solutions to get around this message.**_

### MSL Error: Request failed validation during key exchange

This generally happens on Android devices, most of the time it can be one of these cases:
- Your device model is not Netflix certified ([how to check](https://github.com/CastagnaIT/plugin.video.netflix/wiki/FAQ-(Audio,-Video,-Subtitle,-Other)#how-to-check-if-an-android-device-passes-netflix-certification)), you can only try to force `Widevine L3` on add-on `Expert` settings.

- The ESN used is wrong or incorrectly generated<br/>
In this case you can try to solve the problem by using the ESN prodived from your device. In some cases you can read the ESN in the system information of the operative system, alternatively you can read the ESN by opening the official Netflix app settings. Then copy it in full lenght, in to `Manual ESN` option in the Netflix add-on expert settings.<br/>
Probably future changes by developers will be necessary.

- Netflix has implemented some changes, so changes will need to be made by the developers of the add-on.

### MSL Error: Entity used incorrect user authentication data type

It happens very rarely, so it is difficult to find a solution, it is usually a temporary problem that solves itself in a day or two without doing anything.

### MSL Error: Entity used incorrect key exchange data type

It happens very rarely, so it is difficult to find a solution, it is usually a temporary problem that solves itself in a day or two without doing anything.

### MSL Error: Email or password is incorrect

Known use cases when this error can be raised are:
- You have changed account password
- Netflix has resetted your password

The only solution known is do Logout from addon settings.
After that login again, if you had used Auth Key method you will need to generate a new Auth Key.

### MSL Error: User must login again

This error could happens when you have done "Sign out of all devices" from website account.

When you do "Sign out of all devices" from website, you need to do also Logout from the add-on settings.
After that it is important **waiting about 10 minutes before login again** (if you had used Auth Key method you will need to generate a new Auth Key), otherwise same error will be shown again.

### HTTPError: 403 Client Error: Forbidden for url ...

This situation may indicate a network problem, Netflix say: _It typically indicates that your computer's DNS setting is not routing to Netflix properly._
[Read the Netflix documentation](https://help.netflix.com/en/node/26493)

### HTTPError: 500 Server Error

There is a problem with the netflix server. This should be fixed by them.
Some users were able to solve the problem by changing their profile language.

### HTTPError: 504 Server Error

This error could happen when:
- Temporary server issue
- There are some problems with your network DNS
- Your Proxy or VPN prevent correct communication (if used)
- A firewall is blocking the communication
- There are some changes to the website API endpoints (e.g. MSL) this rarely happens then the add-on need to be checked

### Exception: Connection error

This error has many meanings and depends on the details of this error,
is usually due to something that prevents good internet communication.
You can try to solve the problem by making these tests:
- Check your connection if it is stable or try use another connection
- Try change your DNS (on the router or in Kodi settings if you use a Kodi OS)
- If you use Proxy/VPN try disable it

### MSL Error: Request blacklisted by key exchange service

As far as we know in the case of android devices, may indicate compatibility problems with the device firmware (needs updating), or there is the possibility that the model of the android device in use is on the black list of devices not authorized by Netflix.

### Addon Signals call timeout

This can happen most of the times when:
- Could be a problem of conflicts with other add-ons who are performing other operations at the same time with AddonSignals add-on.<br/>
The only solution is try to enable IPC over HTTP: In add-on expert settings, turn on `Enable IPC over HTTP`.
- Your connection/ISP is not working optimally or Netflix server fails<br/>
Not solvable here.
- Your device uses a memory card or disk that is too slow.
- In rare cases it may represent an internal error of the addon.

### It was not possible to get the data from Widevine CryptoSession

Means that Kodi cannot communicate with the Widevine library on your device.
Possible causes can be:
- Your device has a custom ROM with broken/modified Widevine library
- It's a cheap device (like Chinese products) with a fake widevine certification
- Your device has a too old Android system version (versions prior Android 7.0 may not be fully compatible)
