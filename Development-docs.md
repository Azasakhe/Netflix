### List of useful information about the Netflix infastructure and DRM

A big thanks to Sebastian Golasch for his conference, very useful to every developer:<br/>
[Sebastian Golasch — EME? CDM? DRM? CENC? IDK!](https://www.youtube.com/watch?time_continue=2414&v=3Y3R_snaDDc&feature=emb_logo)

The conference report:<br/>
[Eme? CDM? DRM? CENC? IDK! What you need to make your own video player in the browser](https://sudonull.com/posts/3283-Eme-CDM-DRM-CENC-IDK-What-you-need-to-make-your-own-video-player-in-the-browser)

The Netflix security addition to the DRM, the Message Security Layer (MSL):<br/>
[Official MSL Wiki](https://github.com/Netflix/msl/wiki)

The proprietary Netflix JSON:<br/>
[Official Netflix JSON Docs](https://netflix.github.io/falcor/documentation/jsongraph.html)

The bridge used between Kodi and DRM Systems (like Widevine):<br/>
[InputStream Adaptive Add-on](https://github.com/peak3d/inputstream.adaptive/)

A little reverse engineering of Shakti API:<br/>
[HowardStark - Shakti API](https://github.com/HowardStark/shakti)

Useful information for implementing video interactivity, like in Bandersnatch movie:<br/>
[Back-end infrastructure used to deliver Netflix’s interactive title](https://engelsjk.com/posts/through-the-looking-glass-at-netflix/)

### The addon structure

| Files | Description  |
| ----------------- | --------------------------- |
| /addon.py         | Entry points for Kodi, run an addon instance (more than one instance could also be initiated) |
| /service.py       | Entry points for Kodi, run the addon service (only one instance of the service) |
| /lib/globals.py   | Used by both entry points, initializes global variables |

| Addon folder structure under 'resources' | Description  |
| ----------------- | --------------------------- |
| /language         | .po files of the languages supported by the addon GUI |
| /lib/api          | Shakti and website |
| /lib/common       | Various utility [can be used at same time in Addon instance and Addon service instance] |
| /lib/database         | SQLite, MySQL database management |
| /lib/kodi             | Methods for interact with Kodi mainly used for context menus and library |
| /lib/kodi/ui          | Classes and methods to handle standard and custom Kodi window dialogs |
| /lib/navigation       | Handle route navigation between menus, context menu actions, settings actions, play titles |
| /lib/services         | Contains code used only by the service instance |
| /lib/services/msl     | Handle MSL Request/Response, Manifest, License, MPD for InputStream |
| /lib/services/nfsession | Handle the Netflix web session, path request/response |
| /lib/services/playback  | Handle everything that is related to the Kodi player info in real time like Skip button dialog, stream continuity, etc... |
| /media            | Images used by addon itself and for directory items |
| /skins            | Images and XML used for custom window dialogs |
