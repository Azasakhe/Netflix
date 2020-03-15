Add-on errors:
* [The error - This title is not available to watch instantly](#The-error---This-title-is-not-available-to-watch-instantly)
* [The error - Request failed validation during key exchange](#The-error---Request-failed-validation-during-key-exchange)
* [The error - Entity used incorrect key exchange data type](#The-error---Entity-used-incorrect-key-exchange-data-type)
* [The error - Entity used incorrect user authentication data type](#The-error---Entity-used-incorrect-user-authentication-data-type)

Video:
* [When you playback a video on Raspberry Pi there is no audio and video](#When-you-playback-a-video-on-Raspberry-Pi-there-is-no-audio-and-video)
* [When you playback a video on Android there is no video](#When-you-playback-a-video-on-Android-there-is-no-video)

Audio:
* [How is it possible to have only 2.0 audio tracks?](#How-is-it-possible-to-have-only-20-audio-tracks)
* [When you resume a previous playback it do not keep the language of your choice](#When-you-resume-a-previous-playback-it-do-not-keep-the-language-of-your-choice)

Other:
* [Sometimes blank boxes are shown instead of characters of descriptions and titles](#Sometimes-blank-boxes-are-shown-instead-of-characters-of-descriptions-and-titles)

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

## Video

### When you playback a video on Raspberry Pi there is no audio and video

It is possible that OMXPlayer is enabled, so you need to disable it.<br/>
Go to Kodi settings, go to `Player` settings, then disable OMXPlayer.

### When you playback a video on Android there is no video

First make sure that android video hardware acceleration is enabled.<br/>
Go to Kodi settings, go to `Player` settings, then enable:<br/>
`Allow hardware acceleration - MediaCodec (Surface)` and `Allow hardware acceleration - MediaCodec`

If it still does not work, it may be that one of the enabled video profiles are not compatible with your device.
Then go to Add-on Expert settings, and try to disable VP9 and/or HEVC profile.

## Audio

### How is it possible to have only 2.0 audio tracks?

Netflix provide all 2.0 audio tracks at same bitrate quality so there is no difference between format type (DolbyDigital, AAC).
Then to get 2.0 traces only, go to in the `Expert` add-on settings, and turn off `Enable Dolby Digital Plus`.

### When you resume a previous playback it do not keep the language of your choice

On Kodi 18.x is a known bug, the Kodi 18.x framework does not allow to fix this problem. Then can't be solved in any way.
If you prefer you can try to disable `Remember audio / subtitle preferences` in the addon Playback settings,
in this way leaves the choice of language to Kodi, so you will need to manually select the exact audio language.

## Other

### Sometimes blank boxes are shown instead of characters of descriptions and titles

The blank boxes are commonly known as tofu, is displayed when a certain character is missing in the font used.<br/>
This is a limitation of the fonts used in Kodi 18.x and Kodi 19.x, the only way to try and trick this problem is to set the Arial font to the Skin in use.
