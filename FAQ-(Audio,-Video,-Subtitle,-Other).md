Video:
* [My android device supports 4K but does not playback at 4K](#my-android-device-supports-4k-but-does-not-playback-at-4k)
* [Video playback problems like frame drops, slowdown, stuttering](#video-playback-problems-like-frame-drops-slowdown-stuttering)
* [How to enable HDR and Dolby Vision](#how-to-enable-hdr-and-dolby-vision)
* [When you playback a video on Android there is no video](#When-you-playback-a-video-on-Android-there-is-no-video)
* [Missing video resolutions](#missing-video-resolutions)

Audio:
* [How to enable Dolby Atmos](#how-to-enable-dolby-atmos)
* [How is it possible to have only 2.0 audio tracks?](#How-is-it-possible-to-have-only-20-audio-tracks)
* [When you resume a previous playback it do not keep the language of your choice](#When-you-resume-a-previous-playback-it-do-not-keep-the-language-of-your-choice)

Other:
* [How to set the automatic selection of a profile](#how-to-set-the-automatic-selection-of-a-profile)
* [Subtitles - blank boxes are shown with asian subtitles (Hebrew, Arabic, Thai...)](#subtitles---blank-boxes-are-shown-with-asian-subtitles-hebrew-arabic-thai)
* [Subtitles - i always see subtitles in every video](#subtitles---i-always-see-subtitles-in-every-video)
* [Subtitles - don't always keep the language of your choice](#subtitles---dont-always-keep-the-language-of-your-choice)
* [Sometimes blank boxes are shown instead of characters of descriptions and titles](#Sometimes-blank-boxes-are-shown-instead-of-characters-of-descriptions-and-titles)
* [Skin Widgets - problems and limits](#skin-widgets---problems-and-limits)
* [Kodi - Favourites](#kodi---favourites)
* [Exports to Kodi library - The video lists do not have video/audio stream info (media-flags)](#exports-to-kodi-library---the-video-exported-do-not-have-videoaudio-stream-info-media-flags)
* [Exports to Kodi library - Some exported TV Shows/Movies are missing in kodi library](#exports-to-kodi-library---some-exported-tv-showsmovies-are-missing-in-kodi-library)
* [Exports to Kodi library - Some Tv Shows are not updated automatically](#exports-to-kodi-library---some-tv-shows-are-not-updated-automatically)
* [Some lists have missing titles, seasons or episodes](#some-lists-have-missing-titles-seasons-or-episodes)
* [Views setting](#views-setting)

## Video

### My android device supports 4K but does not playback at 4K

Before asking for help, please perform the following checks:
- Verify that your device support Widevine Security Level L1 (use an app like: DRM Info)
- Verify that your device is connected to a display and/or amplifier with HDCP 2.2 or higher
- Verify that on the Netflix website, in the Playback Settings for the profiles to be used, they have the Data usage per screen, set to Auto or High
- If possible change Kodi display resolution to 4K. If it is not possible, open InputStream Adaptive settings and set `Ignore Display Resolution` to ON
- Verify that in the addon settings these settings (in the Expert page) are set correctly:
`Enable VP9 profiles` to OFF
`Enable HEVC profiles` to ON
- Verify that in the InputStream Adaptive add-on these settings are set correctly:
`Override HDCP status` to ON
`Stream selection` to Auto

If again you don't get 4k resolution, take note of the ESN of your device, or get it from Netflix App (can be found under Settings => About) and write it down on Expert page, Manual ESN.

If again you don't get 4k resolution, open InputStream Adaptive settings and try to set:
`Ignore Display Resolution` to ON
`Min Bandwidth` to 18.000.000

### Video playback problems like frame drops, slowdown, stuttering

Usually happens to those devices where hardware video decoding is not available (due to Widevine limitations) and the CPU fails to process the video stream properly due to the high load.
All devices with software video decoding are affected by this problem (see *Reference table of high resolutions*) like personal computers, raspberry, android boxes (with Widevine sec. lev. L3), etc..

So to get a smooth reproduction **you will need a CPU that can handle the load of software decoding 1080p video** otherwise you will have the result of stuttering video playback.

You can try to solve this problem by trying one of these solutions:
- Limit the resolution to 720p<br/>
From add-on settings go to `Expert` page and change `Limit video stream resolution to` value to 720p.
- Limit InputStream Adaptive max bandwidth<br/>
From add-on settings go to `Expert` page open `InputStream Adaptive settings` and try to set `Max Bandwidth` between 2.500.000 and 4.000.000

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

To have more chances to get high resolutions use a device with Android certified Netflix or Windows (x86/x64) system.

All other Linux devices are subject to major restrictions.
See also _Reference table of high resolutions_ in the Readme.

## Audio

### How to enable Dolby Atmos

It's enabled by default, when option `Enable Dolby Digital Plus` is enabled.
But only some films/TV shows have Atmos streams.

- On Kodi 18.x they can be distinguished only from the skin media-flag "Dolby-HD".
- On Koki 19.x they can be distinguished also from the label "Atmos" in the audio language list

A premium netflix account is required.

### How is it possible to have only 2.0 audio tracks?

Netflix provide all 2.0 audio tracks at same bitrate quality so there is no difference between format type (DolbyDigital, AAC).
Then to get 2.0 traces only, go to in the `Expert` add-on settings, and turn off `Enable Dolby Digital Plus`.

### When you resume a previous playback it do not keep the language of your choice

On Kodi 18.x is a known bug, the Kodi 18.x framework does not allow to fix this problem. Then can't be solved in any way.
If you prefer you can try to disable `Remember audio / subtitle preferences` in the addon Playback settings,
in this way leaves the choice of language to Kodi, so you will need to manually select the exact audio language.

## Other

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
This is a limitation of the fonts used in Kodi 18.x and Kodi 19.x, the only way to try and trick this problem is to set the Arial font to the Skin in use, and in the Kodi subtitles settings.
It may not work with all kinds of Asian languages, the best thing is to get/ask information through the forum of Kodi.

### Subtitles - I always see subtitles in every video

Just change how Kodi handles subtitles by choosing *forced only*.
In Kodi Settings -> Player -> Language
set: `Preferred subtitle language` to `Forced only`

### Subtitles - don't always keep the language of your choice

The Kodi 18.x framework does not allow to fix this problem. So there is no solution.<br/>
If you prefer you can disable `Remember audio / subtitle preferences` in the addon Playback settings, so in each video you will manually enable the subtitles.

### Sometimes blank boxes are shown instead of characters of descriptions and titles

The blank boxes are commonly known as tofu, is displayed when a certain character is missing in the font used.<br/>
This is a limitation of the fonts used in Kodi 18.x and Kodi 19.x, the only way to try and trick this problem is to set the Arial font to the Skin in use.

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
It may happen that between the official app and the add-on are missing titles, seasons or episodes,
(we are talking about missing titles inside add-on lists, NOT Kodi library).

Before opening an Issue thread check these things:
- Check if you are using the same profile on all devices
- Check that the missing titles actually exist on the website (from a computer)

Only if the titles exist in the website but not in the add-on then open an Issue, otherwise it is their problem.

### Views setting

The views are type of view to show list contents, for example to Estuary skin there are InfoWall/Poster/WideList/Wall etc.
Each of this views has its own ID (related with skin used).

An example to Estuary skin: InfoWall is ID 54, Wall is ID 500

These settings allow you to override the default views used by skin for a type of content.
When enabling a custom view on a list type, you must enter the ID (number) of the view to be used.

The ID's must be provided by the skins readme, have no relation with the add-on.
