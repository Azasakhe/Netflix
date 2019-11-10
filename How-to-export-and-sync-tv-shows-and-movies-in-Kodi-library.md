### You can export in two ways

1. One way is to manually export each tv show/movie through the context menu, in this case new seasons or episodes must be updated manually.
Some tips:
- To export, open context menu of a tv show and select `Export to library`.
- To export new seasons/episodes, open context menu of a tv show and select `Export new episodes`.
- To force a tv show update, open context menu of a tv show and select `Update inside library`, this function will completely delete all files exported of the tv show and export them again.

2. One way is to manually export each tv show / movie through the context menu, but with scheduled automatic updates.<br/>
The auto-update stands for the search for new seasons and episodes.
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
- Click on `Purge library`

NOTE: if you are an experienced user, instead of resetting you can move the folders of the files manually

### How to synchronize Kodi library with Netflix "My List" of an profile


