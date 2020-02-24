## Synchronisation of watched status with Netflix

### The limitations

Being an test feature, it has _not yet been included to work with the Kodi library_.

What is not working, due to an (yet) unknown problems:

- The **continue watching list will not be updated**
- The **watched status updated from Kodi are not displayed on Android official Netflix app**, but only on the website 

### How it works

This newly introduced feature is still under test, then by default this feature is disabled, is a choice of the user use it.

If you enable it, all previous watched status and progress will be replaced by those on your real Netflix account, until you disable this feature again.

You want enable it open the add-on settings and go to:
`Playback` -> `Synchronize the watched status of the videos with Netflix`

### What happen if you use multiple devices, apps or website

_In general there is no problem_, you can use any device, apps, website at the same time.

But the following behaviour should be highlighted:

- The synchronization from Kodi to the Netflix service is immediate
- The synchronization from Netflix service to Kodi could be in some cases delayed

This can happen if you use the _same_ profile on multiple device, apps, website at same time, then the videos progress that are been changed outside Kodi you may not see immediately.

If you want to see those changes immediately, you can choose to perform one of the following operations:<br/>
-Switch to another profile and return to the previous<br/>
-Do the _purge cache_ from add-on expert settings<br/>
-Reboot Kodi

### When i stop playback the resume is not updated

The synchronization requires updates to be sent from the first minute of playback, therefore the resume will be updated only after the first minute of the played video, then if you press stop before this minute no changes will be saved.

### How to manually change state watched

By default Kodi provide these context menu:<br/>
`Mark as watched` / `Mark as unwatched` / `Reset resume position`

In this case **they will not work** because Kodi doesn't allow a personalized use of them.

Then you have to use the context menu:<br/>
`Change watched status (locally)`

This menu allows you to change the watched status, but _this change will never be communicated to Netflix but will only take effect within Kodi_.

Using it several times you will also have the possibility to restore the watched status of Netflix.

**Be careful because of a Kodi problem, if you change the state watched manually, after stopping playback causes strange side effects, which will only resolve after Kodi restart**