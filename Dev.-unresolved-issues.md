This document provides some points, the most critical, not solved

### "Resume from" context menu sometimes not work with sync of watched status

When "Synchronize the watched status of the videos with Netflix" is enabled the "Resume from" context menu of Kodi sometimes not work and video start from beginning.

I have opened an Issue: https://github.com/xbmc/xbmc/issues/17426

~I have circumscribed the problematic code in Kodi's core, but we need help from a Kodi developer or someone that know that part of the code.~
I found the problem in Kodi core, i have opened PR https://github.com/xbmc/xbmc/pull/17993 waiting devs response

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
