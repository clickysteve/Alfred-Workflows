Keybase.io Alfred Workflow
================
Version 0.3

A simple encryption and decryption workflow for Keybase.io.

###Why Keybase.io?###

Keybase.io is a centralised verified profile that makes encryption and decryption using PGP easier and more accessible.

To use their web app you need to provide your private key to be stored on their servers, which I'm not too comfortable with. I don't remember command line instructions all that well, so thought an Alfred workflow made sense.

###Requirements###

* All the usual stuff to run Alfred on the Mac.
* The Keybase Shell. Instructions available on keybase.io.

###Configuration###

* An AppleScript runs to kill the Terminal application after the encryption/decryption has been completed. If you use a different default app (such as iTerm), you'll need to change the relevant line from 'Terminal' to 'iTerm'. This is explained in the comments, and should be obvious when you look at it.

###Usage###

* To *encrypt and sign* text, use the keyword 'encrypt', followed by the message you wish to encrypt. 

* To *decrypt* text, use the Alfred keyword 'decrypt', followed by the PGP block you wish to have decrypted.

###Process###

* For *encryption and signing*, Alfred will ask for the message you wish to send, and then re-prompt you to enter the keybase username of who you wish to send the message to. The output will be passed to the Keybase shell, and the resulting PGP block will then be copied to the clipboard.

* For *decryption*, Alfred will take the PGP block provided, decrypt it using the Keybase shell, and copy the resulting decrypted message to the clipboard.

* To *track* a user, type 'track' followed by the username. Terminal will not close automatically, to allow you to verify the proofs manually.


###Known Issues/Improvements###

* This requires you to be logged in to the Keybase Shell, and so the first time the process isn't as smooth. In future I'd like to work out a better way of doing this (if possible).
* At some point I might look to add an option just to sign messages separately from the encryption itself. This would over-complicate things at the minute.
* This works best when you are exchanging messages with somebody that you area already tracking in keybase.io, and them tracking you. For example, sometimes it doesn't decrypt a message from a user you have not interacted before properly for the first time, as it needs to verify them. At present this isn't a big problem, as this is really meant to be a quick script for people you regularly communicate with. However, in future I'd like to improve on this.

All contributions welcome!
