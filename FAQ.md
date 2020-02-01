Add-on errors:
* [The error - This title is not available to watch instantly](#The-error---This-title-is-not-available-to-watch-instantly)
* [The error - Request failed validation during key exchange](#The-error---Request-failed-validation-during-key-exchange)

Audio:
* [How is it possible to have only 2.0 audio tracks?](#How-is-it-possible-to-have-only-2.0-audio-tracks?)
* [When you resume a previous playback it don't keep the language of your choice](#When-you-resume-a-previous-playback-it-don't-keep-the-language-of-your-choice)

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

### How is it possible to have only 2.0 audio tracks?

Netflix provide all 2.0 audio tracks at same bitrate quality so there is no difference between format type (DolbyDigital, AAC).
Then to get 2.0 traces only, go to in the `Expert` add-on settings, and turn off `Enable Dolby Digital Plus`.

### When you resume a previous playback it don't keep the language of your choice

On Kodi 18.x is a known bug, the Kodi 18.x framework does not allow to fix this problem. Then can't be solved in any way.
If you prefer you can try to disable `Remember audio / subtitle preferences` in the addon Playback settings,
in this way leaves the choice of language to Kodi, so you will need to manually select the exact audio language.
