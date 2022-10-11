This document provides some points, the most critical, not solved. Other could be found on Projects page.

### Login with E-Mail/Password could cause "Incorrect password" error

Due to changes in the website the login endpoint cause "Incorrect password" error even when the credentials are correct.

Seems that is caused by the new reCAPTCHA v3 score, currently it is not possible to implement it without a paid service,
or ~through "mechanical" webpage navigation (e.g. selenium) due to multi-platform add-on system and the large size of this module.~
UPDATE: An user has reported that also selenium now not works anymore for login.

UPDATE 22/08/2021:
The transition to HTTP2 module (httpx) has improved a lot the login problem, but it seems that in not all countries it works, i don't think there are any other possible solutions.

### Unsupported iso language code from Kodi for audio/subtitle

Kodi support only the language code of ISO 639-1 standard,
Netflix (and other VOD services) use the IETF BCP 47 standard, that have language-country,
this iso allows you to have multiple variations of the same language.

Example:<br/>
`es` --> `Spanish`<br/>
`es-ES` --> `Spanish-Spain`

What happen? Kodi recognizes the language with wrong names:

`es-ES` --> `Spanish-Spanish`<br/>
(`pt-BR` for Kodi is `Portuguese-Breton` instead of `Portuguese-Brazil` and so on..)

and as a side effect a language with country code can never be set as default language in Kodi player settings,
therefore the user who speaks the language "es-ES" must always select it manually.

Waiting for the correct implementation on Kodi, the temporary solutions that have been taken are:

- Replacing language code<br/>
`fix_locale_languages` in kodi_ops.py is used to replace all the language code with country code (of video manifest) with a customized language code, example "es-ES" with "es-Spain". In this way Kodi not recognize the language code and does not try to translate it with wrong names.

- Set manually as default the audio track with country code<br/>
`_get_default_audio_track_id` in converter.py, set as default in the manifest the audio track with the country code, when the user want to do this, see `if G.ADDON.getSettingBool('prefer_alternative_lang'):` line. In this way when a user play a video will have its audio/subtitle language as default.

Some more info PR: https://github.com/CastagnaIT/plugin.video.netflix/pull/933

**UPDATE:** On Kodi v20 i have partially fixed this problem (see https://github.com/xbmc/xbmc/pull/21776)
now Kodi do not convert language codes with country codes with wrong descriptions but keep them as is
so for example `es-ES` now become `Spanish-es`.

Plus an user can also add custom description by using Kodi advancedsetting.xml, for example :
```xml
<advancedsettings>
<languagecodes>
  <code>
    <short>es-es</short>
    <long>Spanish - Spain</long>
  </code>
</languagecodes>
</advancedsettings>
```

### Mixed menu languages, due to different Kodi GUI language

When a netflix profile is set with a certain language, and Kodi GUI is set with a different language, some menus result with mixed languages.

To fix the problem you would need a Kodi method to get the addon language strings in the chosen language and not the default one of the GUI.

Which will still result in the same language code problem with ISO 639-1 (because is provided in IETF BCP 47),
but here it would be less invasive.

### License request error: This title is not available to watch instantly

This error is obscure, over time it has not been possible to identify the cause, because it seems to group together a number of different problems, such as:

- could happen if you are using an hotspot/tethering connection with your device (where is running Kodi)
- could happen with some models of android (not certificated) devices
- could happen if you try use a VPN
- could happen if you limit video resolutions from account settings
- could happen if something in MSL manifest/license format is changed

Some users have solved in these ways:
- make the log out
- reinstall the Widevine library
- manually changing/reset ESN
- changed internet connection (before hotspot/tethering, after wired)
- waited about two days and the problem disappeared on its own.

the most common solutions have been to reinstall the widevine libraries and logout,
but others who have tried these solutions have not solved the problem not even reinstalling the addon,
other users (linux OS) have resolved by updating the operating system, but i can't find a relationship between the two, as nothing should change in the addon's execution environment.

### Android Chromebook devices cannot be used

Not found a way to make works the ESN handshake i dont know what ESN format could be used
ref. https://github.com/CastagnaIT/plugin.video.netflix/issues/1286
