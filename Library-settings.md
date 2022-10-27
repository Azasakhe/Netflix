## Explanation of the functions in the Library settings

### Enable Kodi library management
Enables the use and management of the Kodi library, when enabled will be add on each TV Show / Movie the following context menus:

Export to library / Remove from library / Update inside library / Export new episodes

### Add Netflix folders to Kodi library sources
Add to the sources of Kodi library the netflix folders, to browse Netflix content directly from the Kodi library.

Once added you will have to restart Kodi to be able to view them, after that you need to configure them as follow:
1) In the Kodi homepage, open menu `TV Shows` or `Movies`, then open `Files` sub-menu.
2) Select `Netflix-Shows` or `Netflix-Movies` (both need to be configured) and open the context menu `Edit source`
3) In the new window press Ok, another window will be opened
4) Set `This directory contains` field with appropriate content
5) Set `Choose information provider` field with the appropriate scraper e.g. The Movie Database Python
6) Press OK to complete the configuration of the selected folder

### Auto update mode
Establishes which method to use to update the tv shows in order to export automatically new seasons and episodes.

- Manual: updates to tv shows must be done manually, through context menus `Export new episodes`, or in alternative by select the menu `Check for updates now`.
- Scheduled: updates to tv shows will be automatic, you will need to set up a schedule.
- When Kodi starts: updates to tv shows will starts at Kodi start-up, once a day.

### Synchronize Kodi library with "My list"
Allows you to automatically export/remove the tv shows/films to the Kodi library when they are added/removed from My List of an specific profile. If My List has been modified externally (for example through the website or mobile app), the Kodi library updates will be postponed to the scheduled time.

Perform full sync now: Start synchronization immediately (export tv shows and also movies) but delete everything previously exported.<br/>
_DO NOT USE IT TO SYNCHRONIZE WITHOUT WAITING FOR THE START OF THE SCHEDULING, OTHERWISE RISK BAN OF YOUR ACCOUNT._

### Enable NFO files export
If enabled when a tv show or movie is exported (automatically by sync or manually), NFO files will also be created.

This function has these purposes:
- It adds the length of the videos to the media-flags.
- It helps to add missing information to episodes of TV series or movies when Kodi's built-in screapers don't get information.
For example, it can happen that a TV series on netflix is divided into two seasons, while on the TMDB database it is in a single season. This means that Kodi's screaper doesn't get the information for the second season because it doesn't exist in the database. So the NFO files add this missing information.
- To allow the use of the "Local information only" screaper in Kodi's library,
in this case, you must also enable the option `Include all information in NFO files`.
- When Kodi's screaper does not recognize a title (TV Show/Movie) the title may not be displayed in the Kodi library, enabling NFO files still allows you to view unrecognized titles. In this case, you must also enable the option `Include tv show NFO details`.

### Enable custom library folder
Here you can change the default folder where the addon save the file exported of tv shows or movies.

[[Read here detailed instructions|How-to-export-and-sync-tv-shows-and-movies-in-Kodi-library#where-are-the-exported-files]]

### Delete library contents
This makes a complete removal of:
- All tv shows/films exported to the Kodi library
- All library data in the netflix add-on database

### Import existing library
It allows you to import a previously exported library.
Useful for example after an add-on reinstallation allowing you to restore the library.

This feature also support to import STRM library files generated from old add-on versions, like 0.13.x or versions less than 1.7.0.

Before starting the import make sure you have selected the appropriate Netflix profile (open the add-on with the chosen profile).<br/>
When you will be asked to select the path of the library to import, select the path of the folder that contains the subfolders `shows` and `movies`.

If some titles are not imported it is possible that:
- The title is not more available on netflix
- The import failed because of an unmanageable problem with the STRM file to import
- The title is not available in the selected profile (try to open the add-on with a different profile and try again)

### Use MySQL shared library database
It allows you to share what you export to the Kodi library, with multiple different devices, where each device has its own Kodi installation.

In order to work it is necessary use all Kodi's with a central MySQL server.

The versions of MySQL supported are: MySQL => 5.5.3 or MariaDB => 5.5

Read "[[Use library exported with multiple devices]]" page for configuration instructions
