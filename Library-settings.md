## Explanation of the functions in the Library settings

### Auto update mode
Establishes which method to use to update the tv shows in order to export automatically new seasons and episodes.

- Manual: updates to tv shows must be done manually, through context menus `Export new episodes`, or in alternative by select the menu `Check for updates now`.
- Scheduled: updates to tv shows are automatic, you will need to set up a schedule.

### Keep My List and Kodi Library in sync
Allows you to automatically export/remove the tv shows/films to the Kodi library when they are added/removed from My List of an specific profile. If My List has been modified externally for example through the website, in the Kodi library no changes will be made immediately, you will have to wait for the schedule to run.

Perform full sync now: Start synchronization immediately (export tv shows and also movies) but delete everything previously exported.<br/>
_DO NOT USE IT TO SYNCHRONIZE WITHOUT WAITING FOR THE START OF THE SCHEDULING, OTHERWISE RISK BAN OF YOUR ACCOUNT._

### Enable NFO files export
If enabled when a tv show or movie is exported (automatically by sync or manually), NFO files will also be created.

This function has two purposes:
1) It helps to add missing information to episodes of TV series or movies when Kodi's built-in screapers don't get information.
For example, it can happen that a TV series on netflix is divided into two seasons, while on the TMDB database it is in a single season. This means that Kodi's screaper doesn't get the information for the second season because it doesn't exist in the database. So the NFO files add this missing information.
2) To allow the use of the "Local information only" screaper in Kodi's library,
in this case, you must also enable the option "Include all information in NFO files".

### Enable custom library folder
Here you can change the default folder where the addon save the file exported of tv shows or movies.

[[Read here detailed instructions|How-to-export-and-sync-tv-shows-and-movies-in-Kodi-library#where-are-the-exported-files]]

### Purge library
This makes a complete removal of:
- All tv shows/films exported to the Kodi library
- All library data in the netflix add-on database

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
