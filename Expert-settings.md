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

- Change ESN: allow to change ESN for some Android problematic devices.
- Save system info: Save device system infos to a file to allow developers investigate on problems.
- Force security level: On Android L1 device, this allow to force Widevine L3. Usually useful for non-certificated devices.

### Enable debug logging
Allow the addon to print to Kodi log file all information to help developers investigate on problems.
If not needed keep it disabled to save device performances.

### Enable execution timing
For debug purposes only.
Enables the collection of execution time statistics of the source code, concerning the methods executed.

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

### Force Widevine security level L3 (Android only)

Some devices are declared as Widevine security level L1, but they have a broken/wrong implementation of Widevine or MediaCodec API, that will cause impossibility to playback videos, so with no pictures or with an error raised as `Request failed validation during key exchange` or in others cases `This title is not available to watch instantly`.

The only way to have a possibility to playback videos with this devices, are:
- Try request/do a firmware update of device to the manufacturer
- Try to enable this option

When you enable this option:
- If you get this error `Request failed validation during key exchange`, means that _you can not use your device with Netflix add-on_.
- If you can play videos, you can only see them only at _SD quality_.

### Results per page

You can choose how many results have per page (works only to paginated menus).

Note to slow devices and/or slow internet connection:
- A lower value could solve timeouts errors
- A high value could cause timeouts errors

### Manual ESN
Allows you to specify the use of an ESN of your certified device, by excluding the automatically generated ESN.

To be inserted only and exclusively in case of problems.

### Reset ESN
Reset any settings and ESN data stored in the database, and generates a new ESN.
