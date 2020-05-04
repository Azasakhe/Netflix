## Explanation of the functions in the Expert settings

### Run add-on configuration wizard
Performs self-configuration of the add-on. This include configuration of profiles, InputStream Adaptive, and some Kodi settings.

Useful to restore the settings after a wrong configuration.

### Enable Dolby Digital Plus
When enabled enable DDPlus and DDPlus HQ and DDAtmos on premium accounts.
When disabled allow only 2.0 audio tracks.

### Enable VP9 profiles
Allow get VP9 video streams. If your device does not have full support for this codec, the video startup may crash or cause display problems.

### Enable HEVC profiles
Allow get HEVC video streams. If your device does not have full support for this codec, the video startup may crash or cause display problems.
(may not work on systems other than Android or MacOS).

### Disable WebVTT subtitle support
To be used only in case of display problems with subtitles.

### Force HCDP 2.2 video streams
For testing purposes only.

The HDCP 2.2 streams are automatically enabled when a device have Widevine certification with a 4K certified display, see Readme.

### Debug logging level
- Disabled - Logging info completely disabled (save CPU resources)
- Info - Basic logging info
- Verbose - Detailed logging info (allow to analyze issues)

### Enable execution timing
For debug purposes only.
Enables the collection of execution time statistics of the source code, concerning the methods executed.

### Limit video stream resolution to
Force a maximum resolution limit. This runs at a low level, it limits the video streams sent to InputStreamAdaptive/Kodi.

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
The IPC allows the communication between different processes of the add-on, not to be confused with internet communication. By default IPC communication is done by using the AddonSignals plugin.

In some cases the use of this plugin by many add-ons could cause timeout problems, so you can activate the _IPC over HTTP_ to exclude _IPC over AddonSignals_.

### Manual ESN
Allows you to specify the use of an ESN of your certified device, by excluding the automatically generated ESN.

To be inserted only and exclusively in case of problems.

### Reset ESN
Reset any settings and ESN data stored in the database, and generates a new ESN.
