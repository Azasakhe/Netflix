This document provides some points, the most critical, not solved

### "Resume from" context menu sometimes not work with sync of watched status

When "Synchronize the watched status of the videos with Netflix" is enabled the "Resume from" context menu of Kodi sometimes not work and video start from beginning.

I have opened an Issue: https://github.com/xbmc/xbmc/issues/17426

I have circumscribed the problematic code in Kodi's core, but we need help from a Kodi developer or someone that know that part of the code.

### Path call "refreshListByContext" of update_lolomo_context method often fails

Here we talk about Sync watched status with netflix feature,
at the end of playing a video (or stop it) to request the update of continueWatching lolomo, we need to call api path `refreshListByContext` (see update_lolomo_context method in api_requests.py).

This invalidate the "continueWatching" list in the netflix cache, in order to update the contents of the list.
The call is done after the Stop event request from _process_event_request in events_hadler.py.

Often this call return HTTPError 500 (error visible from log, on screen only when debug verbose is enabled).

On NF website there is some cases where this call is not performed, it is possible that this is the cause of the error, but i failed to understand the rule.

### Wrong selection of audio/subtitle track due to unsupported language code from Kodi

Kodi support only the language code of ISO 639-1 standard,
Netflix (and other VOD services) use the IETF BCP 47 standard, that have language-country.

What happen? Kodi recognizes with wrong names, example `pt-BR` for Kodi is `Portuguese-Breton` instead of `Portuguese-Brazil` and so on..

To now we have fixed this by changing the language code with an unrecognized type see fix_locale_languages method in kodiops.py, but it seems that it is not always effective, some users complain that the automatic language selection does not always happen correctly.

Unfortunately here you need to make a modification on Kodi to solve the problem.

Ref. https://github.com/xbmc/xbmc/issues/15308

### Mixed menu languages, due to different Kodi GUI language

When a netflix profile is set with a certain language, and Kodi GUI is set with a different language, some menus result with mixed languages.

To fix the problem you would need a Kodi method to get the addon language strings in the chosen language and not the default one of the GUI.

Which will still result in the same language code problem with ISO 639-1 (because is provided in IETF BCP 47),
but here it would be less invasive.
