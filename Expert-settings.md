## Explanation of Expert setting category
Here there are only some of them referred to the addon for Kodi v19 or above.

### Run add-on configuration wizard
Performs self-configuration of the add-on. This include configuration of profiles, InputStream Adaptive, and some Kodi settings.

Useful to restore the settings after a wrong configuration.

### Limit video stream resolution to
Force limit the stream resolutions. This runs at a very low level, so will affect InputStream Adaptive addon functionalities.
If possible you suggest to avoid use this setting and limit resolutions by using InputStream Adaptive settings.

### Enable Dolby Digital Plus
When enabled enable Dolby Digital Plus, Dolby Digital Plus with high bitrate on standard/premium account, and Dolby Digital Atmos on premium account.
When disabled allow only 2.0 audio tracks.

### Enable VP9 profiles
Allow to get video streams with VP9 codec. If your device does not have full support for this codec, the video startup may crash or cause display problems.

### Enable HEVC profiles
Allow to get video streams with HEVC codec. If your device does not have full support for this codec, the video startup may crash or cause display problems. (Available on Android only).

### Disable WebVTT subtitle support
Can be used only in case of display problems with subtitles on Kodi v18 or v19.

### Force HCDP 2.2 video streams
For testing purposes only.

The HDCP 2.2 streams are automatically enabled when a device have Widevine certification with a 4K certified display, see Readme.

### ESN / Widevine settings
Open a window to show and change ESN and Widevine settings.

- Change ESN<br/>
Allow you to change ESN by specifing the ESN of your certified device. Can be useful for some problematic android devices.
Do not change it if not really needed.

- Reset<br/>
Reset the current ESN, useful if you have previously changed ESN or settings.

- Save system info<br/>
Save your device system info in to a file, to allow developers investigate on problems.

- Widevine - Force security level<br/>
Allow to force Widevine L3 on a declared L1 device. This may be useful for non-certified devices, that cause impossibility to playback videos, so with no pictures or when there is an error raised as `Request failed validation during key exchange` or `This title is not available to watch instantly`.<br/>
When you enable it:
  - If you get this error `Request failed validation during key exchange` again, means that _you can not use your device with Netflix add-on_.
  - And you can play videos, you will be limited to _SD quality_ only, so there is no way to get 1080p or 4k.

### Enable debug logging
Allow the addon to print to Kodi log file all information to help developers investigate on problems.
If not needed keep it disabled to save device performances.

### Enable execution timing
For debug purposes only.
Enables the collection of execution time statistics of the source code, concerning the methods executed.

### Force MSL with idtoken authentication
For Android only, this setting can be used to try solve MSL error: `User authentication data does not match entity identity`
that could happens on some Android devices. _If enabled, this will limit the capability to play videos only from the main profile_, this is due to recent changes on website to which there is currently no solution.

### MSL manifest version
Allow to use an old MSL manifest request version. This was used in the past as workaround to get 1080p resolution on ARM linux devices (e.g. RPI).
Change it may break playback and raise different type of errors.

### Open Connect CDN
To be used with caution. This parameter allows you to select a CDN server for streaming.
It may help in some cases of stream instability, causing video interruptions or the failure to play some videos.

Then, use only if:
- You have streaming errors in log like this:
<pre>
CCurlFile::FillBuffer - Failed: Timeout was reached(x)
CCurlFile::Open failed with code 0 for https://ipv4....
CVideoPlayer::OpenInputStream - error opening
</pre>
- You have ISP network issue

The CDN server with a lower index (rank) is the most reliable one and with the fastest connection which is the server that is usually used.

Therefore the CDN `Server 1` is the default choice, try to change only for the problems described above.

### Enable IPC over HTTP
The IPC allows the communication between different processes of the add-on, not to be confused with internet communication.

If enabled (by default) you will use _IPC over HTTP_, so localhost routing data communication.
If disabled you will use IPC over AddonSignals_ plugin, Kodi will route the data internally without use localhost.

Change this setting may be useful in case of timeout errors.

Due to a internal Kodi bug AddonSignals IPC has memory leak problems, if the device remains switched on 24 hours a day, it is recommended not to disable this setting.

### Results per page

You can choose how many results have per page (works only to paginated menus).

Note to slow devices and/or slow internet connection:
- A lower value could solve timeouts errors
- An higher value could make a slow loading and cause timeouts errors

