# My credentials are safe?

To answer this question in brief yes,
but like everything that travels on the internet nothing is really safe.

## What security measures are being considered?

The protective measures taken into account are the following:

- The credentials inside the add-on (in the device) are stored in a encrypted form, the encryption is mostly related to the hardware of device in use (when possible, otherwise device information are collected), in this way will not be possible to use and/or decrypt the credentials from other devices.
- The Login is done in the same way as it occurs on the website, through the secure HTTPS internet protocol
- In network flow that using Netflix Shakti API, there are never credentials sent.
- In network flow that using Netflix API with MSL, the communication takes place only in encrypted mode according to the Netflix MSL standard.
- When you Logout, the credentials stored will be permanently deleted

## I found a possible data breach, what can i do?

First rule, _DO NOT disclose to the public the problem_, e.g. forum posts or Github Issues.

Then communicate privately (like e-mails or PVT forum message), the problem to the add-on maintainers,
providing as much information as possible, including Kodi LOGs with debugging information.

## My password no longer works on any device

Netflix adopts protection measures according to their algorithms, some of which are explained in their [official document](https://help.netflix.com/en/node/56461), which involves resetting the password under certain circumstances.

Since October 2019, **Netflix is introducing a new policy for users who use shared accounts with multiple people**,
this will result in the account being blocked.

At the moment, there are no details revealed about how this policy work and what is the threshold above which it is applied.
