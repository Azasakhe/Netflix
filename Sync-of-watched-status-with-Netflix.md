### How it works

By default this feature is disabled, we leave the choice to use this feature to the user.

If you enable it, all previous watched status and video progress (inside Kodi) will be replaced by those on your real Netflix account, until you disable this feature again.

Everything else will happen automatically.

#### To enable it
Open the add-on settings and turn on `Synchronize the watched status of the videos with Netflix`

#### To enable it on Kodi library
**If you enable this feature on the Kodi library, you can only send the watched status to netflix, therefore the synchronization will never update the watched status of your videos in the Kodi library.**

Before you will have to enable _Synchronize the watched status of the videos with Netflix_ then:

Open the add-on settings on `Synchronize the watched status of the videos with Netflix` -> turn on `Include Kodi library`


### What happen if you use multiple devices, apps or website

_In general there is no problem_, you can use any device, apps, website at the same time.

But the following behaviour should be highlighted:

- The synchronization from Kodi to the Netflix service is immediate
- The synchronization from Netflix service to Kodi could be in some cases delayed

This can happen if you use the _same_ profile on multiple device, apps, website at same time, then the videos progress that are been changed outside Kodi you may not see immediately.

If you want to see those changes immediately, you can choose to perform one of the following operations:<br/>
-Open the context menu on "My list" or "Continue watching" menu and force the refresh for these lists
-Do the `Clear in-memory cache` from add-on expert settings<br/>
-Disable and re-enable the add-on<br/>
-Reboot Kodi

### How to manually change state watched

By default Kodi provide these context menu:<br/>
`Mark as watched` / `Mark as unwatched` / `Reset resume position`

In this case **they will not work** because Kodi doesn't allow a personalized use of them.

Then you have to use this context menu:<br/>
`Change watched status (locally)`

This menu allows you to change the watched status, but _this change will never be communicated to Netflix but will only take effect within Kodi_.

Using it several times you will also have the possibility to restore the watched status of Netflix.

### The video resume not works

It is a know bug of Kodi 18.x version that prevent to resume the videos, fixed on Kodi 19.x.

### When i stop playback the resume is not updated

The synchronization requires updates to be sent from the first minute of playback, therefore the resume will be updated only after the first minute of the played video, then if you press stop before this minute no changes will be saved.

### Possible notifications with errors at the end of the playback

#### An error prevented the update the status watched on netflix

This error may cause:
- Failure to update the watched status of the video
- It may cause the Continue Watching list not to be updated
- You may find that the synchronization of the watched status can be viewed on the website but not on other devices

This is a problem that cannot be solved yet,
but sometime even if the synchronization has failed,
it may resolve automatically after a few hours.
