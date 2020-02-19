# Development documentation

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

CDN selection strategy to deliver video content and to use the best quality for used connection:<br/>
[Measurement Study of Netflix, Hulu, and a Tale of Three CDNs](https://www.moritzsteiner.de/papers/netflix-hulu.pdf)<br/>
[Another one like above](https://www.cs.rutgers.edu/~badri/552dir/notes/W11-four.pdf)<br/>
[The currently Netflix Open Connect](https://openconnect.netflix.com/)

Netflix player shortcuts:<br/>
[Ctrl+Shift+Alt+D] Display A/V Stats on-screen<br/>
[Ctrl+Shift+Alt+L] Logging window

### The addon structure

#### Files and folders

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

#### The databases

The DBMS used in this add-on are SQLite for the local databases and MySQL for the (optional) shared library database.
SQLite imposes many limitations on database management (e.g. multiple read/write, connections, threads), so to better manage these limits and to make it easier to transition to MySQL, has been chosen to create two local databases.

_Database nf_local_ - Used to store any kind of data except those of the library

| Table name        | Description                 |
| ----------------- | --------------------------- |
| app_config        | Contains data for the addon (excluded for library) |
| menu_data         | Contains _temporary_ data for the management of the various menus/sub-menus of lists |
| profiles          | Contains the parsed Netflix profiles list *1 |
| profiles_config   | Contains the parsed Netflix settings of the profiles *1 |
| session           | Contains data for the currently opened Netflix session |
| settings_monitor  | Used only by settings_monitor.py the only way to distinguish which settings are changed by the user |

_Database nf_shared_ - Used to store the data for library only, the MySQL side reflects the same scheme

| Table name         | Description                 |
| ------------------ | --------------------------- |
| profiles           | A copy of profiles table of the local database *1 |
| shared_app_config  | Contains the settings for the library |
| stream_continuity  | Contains data to remember user-selected settings for audio/subtitles of each tv show/movie |
| video_lib_episodes | Contains the data of exported episodes |
| video_lib_movies   | Contains the data of exported movies |
| video_lib_seasons  | Contains the data of exported seasons |
| video_lib_tvshows  | Contains the data of exported tv shows |

*1 Tables with frequently updated data, therefore these tables must never be used to save other data otherwise they will be deleted.


### Apple iOS tvOS limits Python compatibility

Unlike linux, iOS/tvOS does not implement or allow the use of some features, creating problems in executing of the source code

These are some known limitations (on Python 2.7, later versions are to be tested):
- There is no "fork", "exec" support for the processes, this breaks the `subprocess` module
- Due to missing "fork" there is no full cleanup of process resources (memory, threads, file handles, ...)
- Due to no cleanup of processes can breaks some functionality of module `platform` e.g. `machine`, `system`, `node`
- There is no file access outside of application directory
- There is no currently support multi-processing
