![Image](/img/BannerWakeup.jpg)﻿

(Photo: pixabay.com)

Windows 10: Set up Wake-On-LAN ⏰
==================

**Whoever wants to work or play on a remote PC (for example, with Steam Link), often has to turn on the remote PC first. With Wake-On-LAN (WOL for short), computers that are switched off or in energy-saving mode can be switched on again remotely at any time. In theory, it's simple: as soon as the network card on UDP port 9 receives a network packet with its own MAC address (the so-called magic packet), it boots up the PC. In practice, however, some stumbling blocks lurk.**

... ![Bild](/img/MF.png) *By Markus Fleschutz* 🕑 *November 24, 2019*

1️⃣ Note down IP and MAC address 📝 
---------------------------------

Both the IP and MAC addresses of the sleeping PC(s) are needed for wakeup. Both addresses can be displayed under ***Settings* > *Network* > *Network and Internet* > *Ethernet* > *Display Network Properties*** and noted for later.

2️⃣ Permanently powering up the PC ⚡️ 
----------------------------

It sounds trivial, but: those who use a master-slave outlet must make sure that the PC is plugged into the master outlet. Even a foot switch or power switch will permanently disconnect the PC from the power when it is off. Then, of course, WOL cannot work.

3️⃣ Turn off monitor(s) during shutdown.
--------------------------------------------

If you use WOL often, you should get in the habit of turning off the monitors when shutting down the computer. This is because if the computer is booting up via WOL, the monitors can remain off, thus saving on the power bill and the environment. Alternatively, the monitor power management can also be modified to automatically power-save the monitor after 5 minutes.

4️⃣ BIOS support for WOL
------------------------------------

The BIOS in modern motherboards (younger than 2012) supports WOL and also has WOL turned on by default. Only if you have problems with WOL, you should also check the BIOS for support.

5️⃣ Network card support for WOL
------------------------------------

Windows 10 also has WOL enabled by default with Magic Packet for network cards. Only if you have problems with WOL, you should check the support.

6️⃣ Turn off login screen (optional).
----------------------

If the computer is woken up by WOL, then by default the PC boots up to the login screen and waits (forever) for username/password/PIN. Either use software like *Remote Desktop Connection* for the input or disable the login screen. To do this, go to *Settings* > *Logon Options* ... Password prompt... Select "Never".

7️⃣ Set up VPN access (optional)
----------------------------------

If you want to wake up the computer not only from the home network, but from the Internet worldwide, you need a VPN access to the home network. To do this, you need to dial into the home router, set up VPN access and then use it on the mobile device.

8️⃣ Install and set up WOL app.
-----------------------------

The last step and the question: from which device to wake up?

- From an Alexa enabled device? Then see [ Amazon Alexa Skills](https://www.amazon.de/kostenlos-Alexa-Skills/s?ie=UTF8&page=1&rh=n%3A10068460031%2Ck%3Akostenlos)
- From an Android device? Then see [ Android Apps on Google Play](https://play.google.com/store/apps?hl=de)
- From an Apple device? Then see [ Apple App Store](https://www.apple.com/de/ios/app-store/)
- From a Windows computer? Then see [ Windows Apps on Windows Store](https://www.microsoft.com/de-de/store/apps/windows)

Search there for "Wake on LAN" or "WOL" and install the appropriate application/software/skills. When setting up, the IP address as well as the MAC address of the computer is now required and then the big wake-up can begin ⏰ .

Links
-----

- [Amazon Alexa Skills](https://www.amazon.de/kostenlos-Alexa-Skills/s?ie=UTF8&page=1&rh=n%3A10068460031%2Ck%3Akostenlos)
- [Android Apps on Google Play](https://play.google.com/store/apps?hl=de)
- [Apple App Store](https://www.apple.com/de/ios/app-store/)
- [Windows Apps on Windows Store](https://www.microsoft.com/de-de/store/apps/windows)
- [Steam Link](https://store.steampowered.com/app/353380/Steam_Link/)
