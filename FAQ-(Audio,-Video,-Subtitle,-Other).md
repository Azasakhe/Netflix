Video:
* [My android device supports 4K but does not playback at 4K](#my-android-device-supports-4k-but-does-not-playback-at-4k)
* [Video playback problems like frame drops, slowdown, stuttering](#video-playback-problems-like-frame-drops-slowdown-stuttering)
* [How to enable HDR and Dolby Vision](#how-to-enable-hdr-and-dolby-vision)
* [When you playback a video on Android there is no video](#When-you-playback-a-video-on-Android-there-is-no-video)
* [Missing video resolutions](#missing-video-resolutions)
* [Video Stream only at 540P (SD) on ARM device (linux/Kodi OS)](#video-stream-only-at-540p-sd-on-arm-device-linuxkodi-os)
* [Video Stream only at 540P (SD) on Android device](#video-stream-only-at-540p-sd-on-android-device)
* [Videos at 23/25fps are not played at double display frequency (hz)](#videos-at-2325fps-are-not-played-at-double-display-frequency-hz)

Audio:
* [How to automatically use the audio language of the Netflix profile used](#how-to-automatically-use-the-audio-language-of-the-netflix-profile-used)
* [How to enable Dolby Atmos](#how-to-enable-dolby-atmos)
* [How is it possible to have only 2.0 audio tracks?](#How-is-it-possible-to-have-only-20-audio-tracks)
* [When you resume a previous playback it do not keep the language of your choice](#When-you-resume-a-previous-playback-it-do-not-keep-the-language-of-your-choice)
* [The ATMOS stream info (media-flags) does not appear](#the-atmos-stream-info-media-flags-does-not-appear)

Other:
* [How to try solve the problem with loading screen video buffering](#how-to-try-solve-the-problem-with-loading-screen-video-buffering)
* [How to set the automatic selection of a profile](#how-to-set-the-automatic-selection-of-a-profile)
* [Subtitles - blank boxes are shown with asian subtitles (Hebrew, Arabic, Thai...)](#subtitles---blank-boxes-are-shown-with-asian-subtitles-hebrew-arabic-thai)
* [Subtitles - i always see subtitles in every video](#subtitles---i-always-see-subtitles-in-every-video)
* [Subtitles - don't always keep the language of your choice (Kodi 18)](#subtitles---dont-always-keep-the-language-of-your-choice-Kodi-18)
* [Sometimes blank boxes are shown instead of characters of descriptions and titles](#Sometimes-blank-boxes-are-shown-instead-of-characters-of-descriptions-and-titles)
* [Skin - wrong video media-flags info (resolution, format audio-video)](#skin---wrong-video-media-flags-info-resolution-format-audio-video)
* [Skin Widgets - problems and limits](#skin-widgets---problems-and-limits)
* [Kodi - Favourites](#kodi---favourites)
* [Exports to Kodi library - The video lists do not have video/audio stream info (media-flags)](#exports-to-kodi-library---the-video-exported-do-not-have-videoaudio-stream-info-media-flags)
* [Exports to Kodi library - Some exported TV Shows/Movies are missing in kodi library](#exports-to-kodi-library---some-exported-tv-showsmovies-are-missing-in-kodi-library)
* [Exports to Kodi library - Some Tv Shows are not updated automatically](#exports-to-kodi-library---some-tv-shows-are-not-updated-automatically)
* [Some lists have missing titles, seasons or episodes](#some-lists-have-missing-titles-seasons-or-episodes)
* [Skin viewtypes (Views) settings](#skin-viewtypes-views-settings)
* [How to check if an android device passes Netflix certification](#how-to-check-if-an-android-device-passes-netflix-certification)
* [How i can use JSON-RPC calls?](#how-i-can-use-json-rpc-calls)
* [How i can use JSON-RPC call to make a search?](#how-i-can-use-json-rpc-call-to-make-a-search)
* [How to try run the addon with Python 3.5 or 3.6](#how-to-try-run-the-addon-with-python-35-or-36)

## Video

### My android device supports 4K but does not playback at 4K

Before asking for help, please perform the following checks:
- You must have a 4k Netflix account plan.
- Verify that your device support Widevine Security Level L1 (use an app like: DRM Info).
- Verify that your device is connected to a display and/or amplifier with HDCP 2.2 or higher.
- Verify that on the Netflix website, in the Playback Settings for the profiles to be used, they have the Data usage per screen, set to Auto or High.
- Verify that Kodi can reach until to 4K resolution, Go to Kodi settings -> `System` -> `Display` check that there is the 4K resolution. If there is no 4K resolution available you have some kind of problem with your device or display.

_If you are using KODI v19_ try follow also these steps:
- Set Kodi display resolution to 4K. If instead you want keep a lower Kodi GUI resolution, then open InputStream Adaptive settings and set `Ignore Display Resolution` to ON.
- Verify that in the Netflix addon `Expert` settings, `Enable HEVC profiles` is set to ON.
- Verify that in the InputStream Adaptive add-on settings, `Override HDCP status` is set to ON, and, `Stream selection` to "Automatically select streams".

_If you are using KODI v20_ try follow also these steps:
- Verify that in the InputStream Adaptive add-on settings, `Stream selection type` is set to "Adaptive", or else you can try set "Ask quality" to be able to see if 4K video resolution exists in the list of available video resolutions when playback starts.

If again you don't get 4k resolution, take note of the ESN of your device from device settings or get it from original Netflix app (can be found under Settings => About) then open `ESN / Widevine settings` on add-on `Expert` settings, press `Change ESN` button and copy the original ESN.

### Video playback problems like frame drops, slowdown, stuttering

Usually happens to those devices where hardware video decoding is not available (due to Widevine limitations) and the CPU fails to process the video stream properly due to the high load.
All devices with software video decoding are affected by this problem (see *Reference table of high resolutions*) like personal computers, raspberry, android boxes (with Widevine sec. lev. L3), etc..

So to get a smooth reproduction **you will need a CPU that can handle the load of software decoding 1080p video** otherwise you will have the result of stuttering video playback.

You can try to solve this problem by trying one of these solutions:
- Limit the resolution to 720p<br/>
From add-on settings go to `Expert` page and change `Limit video stream resolution to` value to 720p.
- Limit InputStream Adaptive max bandwidth<br/>
From add-on settings go to `Expert` page open `InputStream Adaptive settings` and try to set `Max Bandwidth` between 2.500.000 and 4.000.000
- On Raspberry system try increase the RAM dedicated to the GPU the best value depends on the model type in use, to know it try to search in the RPI forum.

### How to enable HDR and Dolby Vision

If 4K prerequisites are met (see Readme), you must enabled HDR and/or DolbyVision profiles in addon settings.

- In the addon settings go to Expert page and set:
`Enable HEVC profiles` to ON
`Enable HDR profiles` to ON and/or `Enable DolbyVision profiles` to ON

Remember also to enable HDR feature also in the Kodi display settings.

Depending on your setup, there may be some tinkering required to get HDR to work. This depends on your TV,
if you are using an AV-Receiver, which device Kodi is running on, etc. Please make sure to search the issues and available forum threads for a solution before opening an issue!

### When you playback a video on Android there is no video

First make sure that android video hardware acceleration is enabled.<br/>
Go to Kodi settings, go to `Player` settings, then enable:<br/>
`Allow hardware acceleration - MediaCodec (Surface)` and `Allow hardware acceleration - MediaCodec`

If it still does not work, it may be that one of the enabled video profiles are not compatible with your device.
Then go to Add-on Expert settings, and try to disable VP9 and/or HEVC profile.

### Missing video resolutions

Netflix does _not provide the same resolutions_ (even of the same TV shows or movies) on all models of devices.
Most of the time it is closely related to the type of CPU architecture used.

See _Reference table of high resolutions_ in the Readme to have more info.

### Video Stream only at 540P (SD) on ARM device (linux/Kodi OS)

On ARM devices such as RaspberryPI that runs Kodi OS like CoreELEC, LibreELEC, etc...
Netflix does not provide HD content for every video.

First thing to do is verify that on the Netflix website, in the `Playback Settings` for the profiles to be used, they have the `Data usage per screen`, set to `Auto` or `High`.

Do you think that the missing HD resolutions are an add-on problem?
**Before opening an issue thread, please check that your information are accurate.**

How to do a check, an example with RPI:
1. Run RPI operative system
2. Open Netflix website with RPI Chromium browser
3. Play a video title that for you have HD resolutions at fullscreen
4. Now press keys CTRL + ALT + SHIFT + D, will be shown the info about current video resolution
5. If the info shown 1080P resolution and same title in the addon is at 540P, in this case it is an add-on problem to be reported

### Video Stream only at 540P (SD) on Android device

First thing to do is verify that on the Netflix website, in the `Playback Settings` for the profiles to be used, they have the `Data usage per screen`, set to `Auto` or `High`. If this is not the case, the lack of HD resolutions most of the cases is due to a uncertified device or due to a needed operative system update.

Before asking for help make these steps.

**First step, check if device is still HD certified:**

1. Install official Netflix app from PlayStore,
If the app is not available on PlayStore, you will not be able to have HD resolutions.
2. Open the `Settings` of official Netflix app, and go to `Playback specification` page<br/>
If say maximum resolution SD, the device is not certified.<br/>
If say maximum resolution HD, then could be an ESN problem.

**Second step, check the ESN:**

Open add-on expert settings, do a _Reset ESN_.<br/>
If still not works, try compare the ESN code shown in the settings of official app with the add-on ESN (expert settings->Show ESN).
if you see that the code starts differently, you can try manually insert the ESN in the add-on, or ask for help.

**Third step, how to ask for help:**

If you have not solved the problem or you still want to report the problem, you must attach the following info otherwise we cannot analyze and solve the problem.

In your Issue thread you have to attach:
- A screenshot of ESN of the official Netflix app (by censuring last chars)
- The device system info, how to do:

1. Open `ESN / Widevine settings` from add-on `Expert` settings
2. Press the button `Save system info` to save the system info in to a file
3. Attach the file in your Issue thread

### Videos at 23/25fps are not played at double display frequency (hz)

_For Windows system only:_<br/>
The double frequencies are no longer switched automatically.
This can happen when your display not support 23/25hz, Kodi 18.x in this case switch automatically (e.g. to 50hz),
but from Kodi v19 this not happen by default anymore.

To enable this Kodi feature:<br/>
Open Kodi `System` settings, switch the settings page to `Expert` (below).
On `Dislay` page, select `Whitelist`, select all the higher resolutions with differents hz (usually all 1080p or 4k),
then enable `Allow double refresh rates`.

## Audio

### How to automatically use the audio language of the Netflix profile used

In Kodi Settings -> Player -> Language set: `Preferred audio language` to `Media default`.

In this way the audio language that will be automatically selected will match the language of the currently active Netflix profile.

### How to enable Dolby Atmos

The ATMOS feature is enabled by default, when the option `Enable Dolby Digital Plus` on Expert settings is enabled.
To use it a Premium account is required.

If the Atmos audio output does not work:
1. Open Kodi settings `System` -> `Audio` and switch to `Advanced` settings
2. Enable `Allow passthrough` setting
3. On `Passthrough output device` if possible select `RAW` mode or `WASAPI` or if previous options are not available select `HDMI`
4. Enable `Dolby Digital Plus capable receiver` setting

If Atmos still not working you have to check your hardware/software for a possible wrong setup

Read also [The ATMOS stream info (media-flags) does not appear](#the-atmos-stream-info-media-flags-does-not-appear) to more info.

### How is it possible to have only 2.0 audio tracks?

To get 2.0 tracks only, go to in the `Expert` add-on settings, and turn off `Enable Dolby Digital Plus`.
Instead if you prefer stereo tracks to be selected automatically without turn off Dolby Digital then,
go to in the `Playback` add-on settings, and turn on `Prefer stereo audio tracks by default`.

### When you resume a previous playback it do not keep the language of your choice

On Kodi 18.x is a known bug, the Kodi 18.x framework does not allow to fix this problem. Then can't be solved in any way.
If you prefer you can try to disable `Remember audio / subtitle preferences` in the addon Playback settings,
in this way leaves the choice of language to Kodi, so you will need to manually select the exact audio language.

### The ATMOS stream info (media-flags) does not appear

First of all make sure that:
- You have a Premium Netflix subcription
- Check that a video have the ATMOS track from another device
- In add-on Expert settings, `Enable Dolby Digital Plus` is turned ON
- In add-on Expert settings, try `Clear in-memory and on-disk cache`, and reload the list of videos

Kodi does not support the ATMOS name as a track description, therefore is replaced by [DOLBY-HD], so:

- On Kodi v18 ATMOS tracks can be distinguished only from the skin media-flag [DOLBY-HD].
- On Koki v19 or above ATMOS tracks can be distinguished also from the label ATMOS in the audio language list.

## Other

### How to try solve the problem with loading screen video buffering

Usually this problem is related to:
- Instability of Netflix servers
- Not enough bandwidth to support playback
- There is a unstable connection

In addition the component used for playback the videos InputStream Adaptive add-on,
currently has not implemented a stream buffering to compensate or eliminate these problems.

Therefore possible solutions affect the quality of the image:

- Limit the video resolution<br/>
Open `Expert` settings, and on `Limit video stream resolution to` set 720P or lower
- Lower the bitrate (can affect also the video resolution)<br/>
Open InputStream Adaptive settings and set `Max. Bandwidth` to like 1000000/800000 or lower (could affect also the other add-ons)
- Use a better Wi-Fi channel or change it to a wired connection (sometimes a simple reboot of the Router might solve the problem)
- Try use a H.265 codec this codec use a lower bandwidth but is not available on all videos.<br/>
Open `Expert` settings and enable VP9 (and/or HEVC profile if Android device)<br/>
**WARNING! if the codec is not supported this could cause side effects like stuck Kodi or black screen etc.**
- Only as last resort: Open `Expert` settings and try change `Open Connect CDN` server, if no improvement restore the `Server 1`.


### How to set the automatic selection of a profile

Open the list of profiles, then open the context menu on a chosen profile:

- Set for auto-selection<br/>
If set, the chosen profile will be selected automatically at every add-on start.
- Set for library playback<br/>
If set, the chosen profile will used to play the videos from Kodi library.<br/>
Note: if no profile has been set every time a video is played you will be asked to select a profile.

To remove the setting perform the action again.

### Subtitles - blank boxes are shown with asian subtitles (Hebrew, Arabic, Thai...)

The blank boxes are commonly known as tofu, is displayed when a certain character is missing in the font used.<br/>
This is a limitation of the fonts used Kodi, the only way to try and trick this problem is to set the Arial font to the Skin in use, and in the Kodi subtitles settings.
It may not work with all kinds of Asian languages, the best thing is to get/ask information through the forum of Kodi.

### Subtitles - I always see subtitles in every video

Just change how Kodi handles subtitles by choosing *forced only*.
In Kodi Settings -> Player -> Language
set: `Preferred subtitle language` to `Forced only`

### Subtitles - don't always keep the language of your choice (Kodi 18)

Kodi v18.x framework does not allow to fix this problem. So there is no solution.<br/>
If you prefer you can disable `Remember audio / subtitle preferences` in the addon Playback settings, so in each video you will manually enable the subtitles.

### Sometimes blank boxes are shown instead of characters of descriptions and titles

The blank boxes are commonly known as tofu, is displayed when a certain character is missing in the font used.<br/>
This is a limitation of the fonts used in Kodi 18.x and Kodi 19.x, the only way to try and trick this problem is to set the Arial font to the Skin in use.

### Skin - wrong video media-flags info (resolution, format audio-video)

Due to the great fragmentation of operating systems and the different support of audio/video format types and resolutions of each type of device, 
we can not get all the right skin media-flags info in to the videos.

The information are therefore general and may not conform to what you might get in reality when you play the video.

Media-flag info descriptions like HDR, DOLBY VISION and DOLBY ATMOS are not supported in Kodi.
For DOLBY ATMOS case, will be replaced by DOLBY-HD description.

### Skin Widgets - problems and limits

Let's start by saying that _this add-on is not fully compatible with Skins Widgets_ due to unmanageability and poor integration provided by Widgets themselves.

Therefore requests for help for problems caused by widgets will not be accepted.

Some know Widgets limitations and problems:
- When you add a Widget, it will have access to the data of the last selected netflix profile, which is the profile you selected to open the add-on last time.
- The videos played from a Widget, will be played by using the last selected netflix profile, which is the profile you selected to open the add-on last time.
- Widgets created by some type of list may cause unexpected errors when you select another Netflix profile different from which the Widget was created, by displaying error messages or other.
- Add many Widgets could stuck the Netflix service with unexpected errors.

### Kodi - Favourites
The Kodi Favourites menu play the videos with the last selected netflix profile, which is the profile you selected to open the add-on last time.

### Exports to Kodi library - The video exported do not have video/audio stream info (media-flags)

This is a limitation, it is not possible to add information regarding the details of the audio/video tracks (media-flags), because the information are not available in the metadata requested to Netflix service.

You can still add the length of the videos, by enable the option `Enable NFO files export` in the `Libray` settings of the add-on.

### Exports to Kodi library - Some exported TV Shows/Movies are missing in kodi library

It may happen that the screaper set in the exported files folder (in Kodi's library) does not recognize the exported TV Shows/Movies, so it excludes them from the list.

So to view titles not recognized by the Kodi screaper, you must enable export of NFO files:
- Open the add-on settings
- Go to `Library` section
- Turn on `Enable NFO files export`
- Then, turn on also `Include all information in NFO files`

Now export again the missing titles.

### Exports to Kodi library - Some Tv Shows are not updated automatically
If some Tv Show are not updated automatically, you should have this situation: More profiles with different languages.

This could lead to fails to get the tv show data, because some titles are not available on other profiles languages.
This is not solvable due to the working design of netflix itself. How to solve it?

- If happen with auto sync with My list:
Means that last time you have browsed the add-on with a profile different than set for the auto sync.
Then open again the add-on with the same profile set for the auto sync, and do not change profile until the next scheduled update.

- If happen with auto update:
Means that you have exported a tv show from a profile where in another profile language is not available.
Then browse the add-on with the right profile, select the tv show, open the context menu and select `Export new episodes`.

### Some lists have missing titles, seasons or episodes
It may happen that between the official app/website and the add-on there are missing titles, seasons or episodes,
(we are talking about missing titles inside add-on lists, NOT in Kodi library).

It is essential to make these preliminary checks:
- Check if you are using the same profile on all devices/apps/website
- Check that the missing titles actually exist on the website (from a computer)
- Check if you are using a VPN or Proxy:<br/>
  Then disable or/and uninstall the VPN/Proxy, after open the add-on `Expert` settings, and select `Clear in-memory and on-disk cache`

If after these checks, there are still missing titles, seasons or episodes then try to open a Bug request Issue.

### Skin viewtypes (Views) settings

The views are type of view to show list contents, for example to Estuary skin there are InfoWall/Poster/WideList/Wall etc.
Each of this views has its own ID (related with skin used).

An example to Estuary skin: InfoWall is ID 54, Wall is ID 500

These settings allow you to override the default views used by skin for a type of content.
When enabling a custom view on a list type, you must enter the ID (number) of the view to be used.

The ID's must be provided by the skins readme, have no relation with the add-on.

### How to check if an android device passes Netflix certification

Verification steps:
1) The official Netflix app must be available on PlayStore, if it is not listed your device is not Netflix certified
2) You can try install SafetyNet Test app, to check if `PASS` all google tests
3) You can try check in the PlayStore settings if `Play Protect certification` is marked as certified

### How i can use JSON-RPC calls?

This add-on has not been designed to be used with JSON-RPC calls, so help requests for malfunctions caused by these calls or wrong data in the responses will not be accepted.

### How i can use JSON-RPC call to make a search?

There is a specific support to allow searches through skins and/or JSON-RPC calls,
this because use the default add-on path of add-on search menu could be complex to use.

The endpoint to use is: `plugin://plugin.video.netflix/directory/search/search/?query=something`

Please note that searches made from this endpoint will not be stored in the add-on database.

### How to try run the addon with Python 3.5 or 3.6

This addon requires Python 3.7 libraries, so force using this addon with older Python libraries may cause unexpected errors, for which no support will be provided.
If you are experienced enough and have a Linux operating system, there is an alternative that allows you to run the addon on Python 3.5 and 3.6. This is the guide:

Open the terminal and install these packages:
```
apt install python3-pip
pip3 install contextvars
pip3 install async_generator
```
Now you can try run the addon, please note that it may still not work and does not guarantee correct functioning of the addon.
