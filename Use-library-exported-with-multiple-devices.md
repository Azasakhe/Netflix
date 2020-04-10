When you need to share the same Kodi exported library (of Netflix videos) with multiple devices, there are two possibilities of setting.

Choose the case that suits your needs.

### CASE 1 - All devices can manage and play from the same Kodi library of Netflix exported items

In this case every devices can manage the Kodi library of Netflix exported items (e.g. export, remove).

- Recommended method
- Needed a shared network folder (like SMB)
- Needed a MySQL server

**How to configure:**

To first you must create a shared network folder (using SMB or other services) where place the exported library items.

Then will be needed to configure all Kodi installations, with a central MySQL server. You can follow the official Kodi MySQL setup instructions at [Kodi Wiki](https://kodi.wiki/view/MySQL).

When done, in each device, open the add-on settings and under Library page:
* Turn ON `Enable custom library folder` and choose the path of the shared network folder `Custom library path`. The path must be the exact the same to all devices.
* Enable `Use MySQL shared library database`, then set the same connection parameters used in Kodi MySQL setup.

Now you have set what main device that is responsible for updating the library (e.g. check for new episodes):
Then in the device you have choose, under Library page settings, click on `Set this device as main auto-updates manager`.

To configure the main device to auto-update the library see [[How to export and sync tv shows and movies in Kodi library]].

Now you can manage and play the Netflix exported items from all configured devices.

### CASE 2 - Only a main device must manage the Kodi library of Netflix exported items, all devices can play from same library
In this case _only_ the main device must manage the Kodi library (e.g. export, remove) netflix exported items, any other device must access to the library as "_read-only_" mode, so you should not modify the exported library items from the other devices.

- Method to be used carefully, can causing problems explained below
- Needed a shared network folder (like SMB)

**Pay attention!**

This add-on makes use of an internal database to manage the videos exported to the Kodi library,
to avoid compromising the internal database _you should never modify the Kodi library of Netflix exported items from the other devices_.

Otherwise this will cause in the best cases inconsistencies with the menus to manage the exported videos (e.g. export, remove), in the worst cases increasing the risk of ban cases of Netflix account due to a too heavy synchronization.

**How to configure:**

To first you must create a shared network folder (using SMB or other services) where place the exported library items.

In the in the _main device_:
* Open the add-on settings and under Library page: Turn ON `Enable custom library folder` and choose the path of the shared network folder `Custom library path`.
* If you want configure also the auto-update feature see [[How to export and sync tv shows and movies in Kodi library]]

In the _other devices_:
* Install the add-on
* In the Kodi Video browser and add the path of the shared network folder.
* Remember not to modify the Kodi library of Netflix exported items from these devices
* Do not enable the feature `Enable custom library folder` on this devices 

Now you can play the Netflix exported items from all configured devices.
