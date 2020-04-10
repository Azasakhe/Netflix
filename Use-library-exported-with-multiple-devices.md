When you need to share the same Kodi exported library (of Netflix videos) with multiple devices, there are two possibilities of setting.

_But first a foreword:_<br/>
This add-on makes use of an internal database to manage the videos exported to the Kodi library,
so pay attention to cases of use, to avoid compromising the internal database, where in the best cases the menus to manage the exported videos (e.g. add, remove) will be inconsistents, in the worst cases increasing the risk of ban cases of Netflix account due to a too heavy synchronization.

So be careful to choose the case that suits your needs.

### CASE 1 - All devices can manage the Kodi library of netflix exported items

Recommended method

In this case every devices can manage the Kodi library of netflix exported items, but is needed a _MySQL server_.

Then will be needed to configure all Kodi installations, with a central MySQL server. You can follow the official Kodi MySQL setup instructions at [Kodi Wiki](https://kodi.wiki/view/MySQL).

When done, in each device, open the add-on settings and under Library page:
* Turn ON `Enable custom library folder` and choose a common library directory (like SMB) `Custom library path`. The path must be the exact the same to all devices.
* Enable `Use MySQL shared library database`, then set the same connection parameters used in Kodi MySQL setup.

Last step is set what device is responsible for updating the library (e.g. check for new episodes):
Then in the device you have choose, under Library page settings, click on `Set this device as main auto-updates manager`

Now you can manage the Netflix exported library from all configured devices.

### CASE 2 - Only a main device must manage the Kodi library of netflix exported items, any other device must access to the library in read-only mode

Not recommended, can causing problems explained above



