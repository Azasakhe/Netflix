This document provides some information to start understanding the operating environment of this project.

Being a large project which also makes use of undocumented technologies, it is not possible to compile a complete documentation of every part of it, so i will add some technical information.

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
| /lib/services/cache   | The cache management (sharable with multiple plugin instances) |
| /lib/services/directorybuilder | Prepare the data to build a directory of xbmcgui.ListItem |
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
| watched_status_override | Contains the watched status manually set by the user (when is enabled the sync with nf) |

*1 Tables with frequently updated data, therefore these tables must never be used to save other data otherwise they will be deleted.

### Apple iOS tvOS limits Python compatibility

Unlike linux, iOS/tvOS does not implement or allow the use of some features, creating problems in executing of the source code

These are some known limitations (on Python 2.7, later versions are to be tested):
- There is no "fork", "exec" support for the processes, this breaks the `subprocess` module
- Due to missing "fork" there is no full cleanup of process resources (memory, threads, file handles, ...)
- Due to no cleanup of processes can breaks some functionality of module `platform` e.g. `machine`, `system`, `node`
- There is no file access outside of application directory
- There is no currently support multi-processing

Why is it currently specified that on iOS/tvOS the add-on is not compatible?
Currently the add-on is executable on iOS, but due to the lack of Widevine library, the videos can not be played.

### How to send / receive Netflix data

This add-on relies on the website API, so it must be adapted to any changes to the website.

To understand how it sends and obtains data, you must first consider how the website works.
A simple start is to start studying the network flow with the browser in debug mode,
by analyzing the requests/responses on the pathEvaluator endpoint.
The data is freely accessible and complies with the [JSONGraph](https://netflix.github.io/falcor/documentation/jsongraph.html) standard.

This API is also called Shakti is the basis on how the add-on makes requests and receives responses.

In addition to this, the website also relies on important parts in javascript. (which i cannot mention to avoid legal problems).

### The log-in system

The login system is reproduced via code the one performed by the website.

The security is also taken into account by the add-on, therefore on the net credentials travel encrypted according to the SSL standard, while locally user credentials are stored with AES encryption with an UUID key based on hardware information, therefore related to the hardware in use.

On android the add-on login in the same way,
but it would not be correct because the login should be through dedicated API for android.
In fact because of this there are some side effects (see workaround for media-flag 4K).
These APIs have not been implemented because they require further huge separate study and development.

### Working with the profiles

Considering that there are no documents on which to base ourselves, i will try to explain in short what i currently understand.

There are two ways to work with Netflix profiles, one with the APIs used in "NFSession" (e.g. Shakti) and the other with the MSL APIs. In both cases to be able to activate a profile (therefore to be able to send/receive data with it) we talk about "profile switch".

#### NFSession APIs

There are two ways to perform the profile switch the NFSession side, by using:
- Endpoint /SwitchProfile (this allows you to obtain also the profile cookies)
- Endpoint /profiles/switch

In both cases, after making the switch, you must obtain the authURL value.
The authURL is required to have access rights to make http requests with the specified profile.
The new authURL obtained will need to use for all future NFSession requests.

#### MSL APIs

Here Netflix has implemented a custom MSL user-authentication scheme, (MSL references [User Authentication (Configuration)](https://github.com/Netflix/msl/wiki/User-Authentication-%28Configuration%29), [User Authentication](https://github.com/Netflix/msl/wiki/User-Authentication)) called `SWITCH_PROFILE`.

This authentication method, in addition to attaching the user authentication data to the MSL request, instructs the service to activate the specified profile.

Ref PR: [The MSL switch profile](https://github.com/CastagnaIT/plugin.video.netflix/pull/484)

This user-authentication scheme works only combined with an user-id-token and can not be used with all endpoints, after use it you will get in the response an user-id-token of the profile specified, that you will need to use for all future MSL requests.

### How using makefile unit test

- Install "make"

If you are on windows you can install MinGW or similars<br>
If you are on windows and you have installed Git, you can integrate make:<br>
-Download make-x.x-without-guile-w32.zip from https://sourceforge.net/projects/ezwinports/files/<br>
-Copy the contents to your `Git\mingw64\` merging the folders, but do NOT overwrite/replace any existing files

- Install makefile dependencies (kodi-addon-checker, tox, coverage)
- To run a test open console and run: `make test` or `make run`

### The available resolutions and limitations

Netflix has a complicated system of protection and limitations to allow the viewing of high resolution video (720p/1080p/4k).

The main factors currently known to influence the available resolutions are:

- The type of CPU architecture
- The type of operative system *
- The type of browser *

Is taken in account of the type of User Agent used, it influences the shakti metadata, the ESN, the manifest and license requests.<br/>
We rely on the website specs: https://help.netflix.com/en/node/23742<br/>
In some cases it is possible to obtain even higher resolutions than those declared (depends from the MSL profiles used).

- The model of device in use *
- The DRM security level and HDCP version in use *

We use only the DRM Widevine. We can handle Sec.Lev. L1 only to certified android devices all others are L3.
If the device is L1 and have HDCP >= 2.2, will be available resolutions 1080p and higher in hardware deconding.

- The ESN

The ESN is a serial that _could_ contains information about the device in use, and can influence the resolutions.

- Some videos are also influenced by the producers
- Others things!? we hope no..

<sup>
* This parameter affects the ESN
</sup>