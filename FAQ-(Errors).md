Add-on errors:
* [The error - This title is not available to watch instantly](#The-error---This-title-is-not-available-to-watch-instantly)
* [The error - Request failed validation during key exchange](#The-error---Request-failed-validation-during-key-exchange)
* [The error - Entity used incorrect key exchange data type](#The-error---Entity-used-incorrect-key-exchange-data-type)
* [The error - Entity used incorrect user authentication data type](#The-error---Entity-used-incorrect-user-authentication-data-type)
* [The error - HTTPError: 403 Client Error: Forbidden for url ...](#the-error---httperror-403-client-error-forbidden-for-url-)
* [The error - Request blacklisted by key exchange service](#the-error---request-blacklisted-by-key-exchange-service)
* [The error - Addon Signals call timeout](#the-error---addon-signals-call-timeout)

## Add-on errors

### The error - This title is not available to watch instantly

In this case Netflix says to log out https://help.netflix.com/en/node/109329.<br/>
Open add-on settings and choose `Logout`.

If the problem persists, reinstall Widevine CDM (not applicable on Android):<br/>
Open add-on settings (by context menu on the add-on icon), then go to `Expert` page and choose `InputStream Helper settings`, a new window will be opened, then choose `(Re)install Widevine CDM`.

### The error - Request failed validation during key exchange

This generally happens on Android devices, most of the time it can mean two things:
- The ESN used is wrong, no more compatible or incorrectly generated<br/>
In this case you can try to solve the problem by using the original ESN of your device. In some cases you can read the ESN in the system information of the operative system, alternatively you can read the ESN by opening the official Netflix app settings. Then copy it in full lenght, in to `Manual ESN` option in the Netflix add-on expert settings.<br/>
Probably future changes by developers will be necessary.

- Netflix has implemented some changes, so changes will need to be made by the developers of the add-on.

### The error - Entity used incorrect user authentication data type

It happens very rarely, so it is difficult to find a solution, it is usually a temporary problem that solves itself in a day or two without doing anything.

### The error - Entity used incorrect key exchange data type

It happens very rarely, so it is difficult to find a solution, it is usually a temporary problem that solves itself in a day or two without doing anything.

### The error - HTTPError: 403 Client Error: Forbidden for url ...

This situation may indicate a network problem, Netflix say: _It typically indicates that your computer's DNS setting is not routing to Netflix properly._
[Read the Netflix documentation](https://help.netflix.com/en/node/26493)

### The error - Request blacklisted by key exchange service

As far as we know in the case of android devices, may indicate compatibility problems with the device firmware (needs updating), or there is the possibility that the model of the android device in use is on the black list of devices not authorized by Netflix.

### The error - Addon Signals call timeout

Could be a problem with Kodi or conflicts with other add-ons who are performing other operations at the same time.
In rare cases it may represent an internal error of the addon.

One solution might be to enable IPC over HTTP: In add-on expert settings, turn on `Enable IPC over HTTP`
