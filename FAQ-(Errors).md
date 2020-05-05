Add-on errors:
* [Email or password is incorrect](#email-or-password-is-incorrect)
* [This title is not available to watch instantly](#This-title-is-not-available-to-watch-instantly)
* [Request failed validation during key exchange](#Request-failed-validation-during-key-exchange)
* [Entity used incorrect key exchange data type](#Entity-used-incorrect-key-exchange-data-type)
* [Entity used incorrect user authentication data type](#Entity-used-incorrect-user-authentication-data-type)
* [HTTPError: 403 Client Error: Forbidden for url ...](#httperror-403-client-error-forbidden-for-url-)
* [Request blacklisted by key exchange service](#request-blacklisted-by-key-exchange-service)
* [Addon Signals call timeout](#addon-signals-call-timeout)

## Add-on errors

### Email or password is incorrect

There are several reasons because this problem is presented, the known cases are:

- Netflix automatically reset your password for suspicious activity (notice by e-mail)
- You have changed the password while Kodi was still running

The only solutions is:
1) Try to change your password
2) Reboot Kodi
3) Open Netflix add-on, should be asked to enter the new credentials (if no credential are asked try to open add-on settings and Logout)

You can find other info on the page: [[My credentials are safe?]]

### This title is not available to watch instantly

In this case Netflix says to log out https://help.netflix.com/en/node/109329.<br/>
Open add-on settings and choose `Logout`.

If the problem persists, reinstall Widevine CDM (not applicable on Android):<br/>
Open add-on settings (by context menu on the add-on icon), then go to `Expert` page and choose `InputStream Helper settings`, a new window will be opened, then choose `(Re)install Widevine CDM`.

### Request failed validation during key exchange

This generally happens on Android devices, most of the time it can mean two things:
- The ESN used is wrong, no more compatible or incorrectly generated<br/>
In this case you can try to solve the problem by using the original ESN of your device. In some cases you can read the ESN in the system information of the operative system, alternatively you can read the ESN by opening the official Netflix app settings. Then copy it in full lenght, in to `Manual ESN` option in the Netflix add-on expert settings.<br/>
Probably future changes by developers will be necessary.

- Netflix has implemented some changes, so changes will need to be made by the developers of the add-on.

### Entity used incorrect user authentication data type

It happens very rarely, so it is difficult to find a solution, it is usually a temporary problem that solves itself in a day or two without doing anything.

### Entity used incorrect key exchange data type

It happens very rarely, so it is difficult to find a solution, it is usually a temporary problem that solves itself in a day or two without doing anything.

### HTTPError: 403 Client Error: Forbidden for url ...

This situation may indicate a network problem, Netflix say: _It typically indicates that your computer's DNS setting is not routing to Netflix properly._
[Read the Netflix documentation](https://help.netflix.com/en/node/26493)

### Request blacklisted by key exchange service

As far as we know in the case of android devices, may indicate compatibility problems with the device firmware (needs updating), or there is the possibility that the model of the android device in use is on the black list of devices not authorized by Netflix.

### Addon Signals call timeout

Could be a problem with Kodi or conflicts with other add-ons who are performing other operations at the same time.
In rare cases it may represent an internal error of the addon.

One solution might be to enable IPC over HTTP: In add-on expert settings, turn on `Enable IPC over HTTP`
