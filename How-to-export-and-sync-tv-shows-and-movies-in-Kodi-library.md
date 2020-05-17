### You can export in two ways

**1. Export movies and tv shows (with manual updates for tv shows)**

This mode involves manual export of each tv show/movie through the context menu, in this case new seasons or episodes must be updated manually.

Some tips:
- To export, open context menu of a tv show and select `Export to library`.
- To export new seasons/episodes, open context menu of a tv show and select `Export new episodes`.
- To force a tv show update, open context menu of a tv show and select `Update inside library`, this function will completely delete all files exported of the tv show and export them again.

**2. Export movies and tv shows (with auto updates for tv shows)**

This mode involves manual export of each tv show/movie through the context menu, but with scheduled automatic updates for the search for new seasons and episodes.

_If you decide to use this feature pay attention to the notice written at the end._

How to enable the automatic updates:
- Open add-on settings, and go to the page Library
- `Auto update mode` set to `Scheduled`
- `Perform auto-update` set how often updates are performed
- `Time of Day` set the start time, if when open Kodi the time has already elapsed, the update will still be performed at a later time.
- `Only start after 5 minutes of idle` if turned on updates will only start when you do not use Kodi for at least 5 minutes. If turned off updates will start when you open Kodi.

### Where are the exported files?

By default the files are located in the add-on user data folder with a path like

…\Kodi\userdata\addon_data\plugin.video.netflix\shows<br/>
…\Kodi\userdata\addon_data\plugin.video.netflix\movies

but the full path may change depending on the type of operating system, the file path scheme is viewable in Kodi Wiki https://kodi.wiki/view/Userdata

For easier an access to your exported files, you can change the default path and choose a custom one.

So in add-on settings, go to Library page and:
- Turn on `Enable custom library folder`
- Click on `Custom library path`, to set up your preferred folder

**WARNING: If this setting is changed after you have already exported tv shows or movies, you must reset the database data! This implies the loss of all exports!<br/>**

To reset database, in add-on settings, go to Library page and:
- Select `Delete library contents`

NOTE: if you are an experienced user, instead of resetting you can move the folders of the files manually

### How to synchronize Kodi library with Netflix "My List" of an profile

Synchronization with My List involves the automatic export and removal from the Kodi library of what is added/removed from My List of a specific profile.

When you make changes to My List from another device or from another app or website, the changes will not be reported in the add-on in real time, but you will have to wait for the schedule to run.

_If you decide to use this feature pay attention to the notice written at the end._

Note that when you enable this feature the context menus like Export/Remove from library, will no longer be accessible, because all these operations will be performed automatically from the context menus Add/Remove to My List.

**Before continuing you must complete the point 2 of _You can export in two ways_, in order to enable the scheduled mode.**

How to enable the sync of Kodi library with My List:
- **First important thing, login with the profile containing the My List to synchronize!**
- Open add-on settings, go to Library page
- Turn on `Keep My List and Kodi Library in sync`
- Click on `Use "My List" of the current profile`, in order to get the My List of the chosen profile
- If you want customize the export folder go to paragraph _Where are the exported files?_. If you want to customize it must be done before before the next points
- Click on `Perform full sync now`, to start the synchronization immediately

### Notice for the use of auto-update and auto-sync with Netflix "My List" feature

AN INTENSIVE USE OF THIS FEATURES due to many exported tv shows MAY CAUSE A TEMPORARY BAN OF THE ACCOUNT that varies starting from 24/48 hours. **Use at your own risk.**

If it happens often, there is the possibility to exclude the auto update from the tv shows, by open context menu on a tv show and selecting `Exclude from auto update`.