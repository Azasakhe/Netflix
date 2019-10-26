## Explanation of the functions in the Library settings

### Keep My List and Kodi Library in sync
Allows you to automatically export/remove the tv shows/films to the Kodi library when they are added/removed from My List, but only through the addon interface, then through the context menu "Add/Remove to My List" on selected tv show/movie. So if My List has been modified for example through the website, in the Kodi library no changes will be made, if you want this read next about scheduling.

Perform full sync now: Start synchronization immediately (export tv shows and also movies) by eliminating everything previously exported.

### Export new episodes (Updates scheduling)
Scheduling can be set at desired intervals of hours and days, when it is executed it checks:
* If My List has been modified (no matter from what device or apps), then update the Kodi library accordingly
* If there are new seasons/episodes in the tv shows previously exported, then update the Kodi library accordingly
* Note: at this moment this function DO NOT sync the movies of My List

If neither of these two options are enabled (Keep My List and Kodi Library in sync, Export new episodes):
the exports to the Kodi library can be always performed manually through the context menu "Export/Remove to library".

### Enable NFO files export
If enabled when a tv show or movie is exported (automatically by sync or manually), NFO files will also be created.

This function has two purposes:
1) It helps to add missing information to episodes of TV series or movies when Kodi's built-in screapers don't get information.
For example, it can happen that a TV series on netflix is divided into two seasons, while on the TMDB database it is in a single season. This means that Kodi's screaper doesn't get the information for the second season because it doesn't exist in the database. So the NFO files add this missing information.
2) To allow the use of the "Local information only" screaper in Kodi's library,
in this case, you must also enable the option "Include all information in NFO files".

### Enable custom library folder
Here you can change the folder where the addon exports the files that are added to the Kodi library.

### Purge library
Completely eliminates the tv shows/films exported to the Kodi library.

### Migrate Library to new format
To use only if the old 13.x version of the addon was installed,
allows you to transfer the tvshows/movies exported with the old version to the new one

Warning: in some cases this function may not work or may only migrate a part of the existing library

### Use MySQL shared library database
It allows you to share what you export to the Kodi library, with multiple different devices, where each device has its own Kodi installation.

In order to work it is necessary use all Kodi's with a central MySQL server. You can follow the official Kodi MySQL setup instructions at [Kodi Wiki](https://kodi.wiki/view/MySQL).

When done, in each device open the addon settings and under Library page:
* Check "Enable custom library folder", and choose a shared "Custom library path". The path must be the exact same on all devices.
* Enable "Use MySQL shared library database", then set the same connection parameters used in Kodi MySQL setup.

As a last thing you need to set that only one device is responsible for updating the library (i.e. check for new episodes):
Then in the device you choose, click on "Set this device as main auto-updates manager"
