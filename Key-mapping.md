You can customize Kodi to allow use keys (of keyboard keys, mouse/remote/joysticks buttons and more) as shortcut for the add-on functions.

## How to map an add-on function

In order to add your custom quick shortcuts you have to
create or edit the Kodi _keyboard.xml_ file,
used to override the standard Kodi key mapping.

Kodi wiki provide all info and examples:
- https://kodi.wiki/view/HOW-TO:Modify_keymaps
- https://kodi.wiki/view/Keymap

This is a quick example of keyboard.xml content, to map the function _Export to library_ to the _G_ key:

```xml
<keymap>
  <global>
    <keyboard>
      <g>RunPlugin(plugin://plugin.video.netflix/keymaps/lib_export)</g>
    </keyboard>
  </global>
</keymap>
```

## List of mappable functions

Only some of the add-on functions are available for mapping:

Add/Remove to My list<br/>
`RunPlugin(plugin://plugin.video.netflix/keymaps/my_list)`

Change watched status (locally)<br/>
_Note: works only with "Sync of watched status with Netflix" enabled_<br/>
`RunPlugin(plugin://plugin.video.netflix/keymaps/change_watched_status)`

Export/Update to library<br/>
`RunPlugin(plugin://plugin.video.netflix/keymaps/lib_export)`

Remove from library<br/>
`RunPlugin(plugin://plugin.video.netflix/keymaps/lib_remove)`

## Notice

**Please be careful! Do not hold down the keys for a long time may cause side effects!**

_This could cause unexpected behaviour of the add-on and/or in worst case scenario also corrupt the database._
