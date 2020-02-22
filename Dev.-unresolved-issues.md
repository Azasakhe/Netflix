# Unresolved issues

### Wrong runtime (length) video value

Some videos played by the website have a longer length, compared to when they are played inside Kodi.
An example is the tv show "You" S01E02, on the website after the ending netflix logo, the video continue and you can view others credits, that with Kodi player you can not see, therefore this is the cause of the wrong video length.
Is it possible that some of the credits have a separate video stream?

Ref. https://github.com/CastagnaIT/plugin.video.netflix/issues/414

### Wrong selection of audio/subtitle track due to unsupported language code from Kodi

Kodi support only the language code of ISO 639-1 standard,
Netflix (and other VOD services) use the IETF BCP 47 standard, that have language-country.

What happen? Kodi recognizes with wrong names, example `pt-BR` for Kodi is `Portuguese-Breton` instead of `Portuguese-Brazil` and so on..

To now we have fixed this by changing the language code with an unrecognized type see fix_locale_languages method in kodiops.py, but it seems that it is not always effective, some users complain that the automatic language selection does not always happen correctly.

Unfortunately here you need to make a modification on Kodi to solve the problem.

Ref. https://github.com/xbmc/xbmc/issues/15308
