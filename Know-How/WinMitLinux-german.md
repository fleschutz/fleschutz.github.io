![Image](/img/BannerLinux.jpg)

(Photo: pixabay.com)

Windows 10: Try Linux 🐧
==============================

**Just try Linux under Windows? Without extra PC, second partition, dual-boot system and similar effort? Yes, you can: the *Windows Subsystem for Linux* (WSL) allows you to run Linux terminal applications under Windows 10 (except Windows 10 S)**. 

... ![Image](/img/MF.png) *By Markus Fleschutz* 🕑 *September 21, 2019*

Here's how it works:

1. **Turn on the *Windows Subsystem for Linux* (WSL):** To do this, first open PowerShell in administrator mode. There one enters the following command:

   ```
   Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
   ```

   After that the computer must be booted.

2. **Open the *Microsoft Store*, search for "Ubuntu" and install it.** Of course you can also install any other Linux distribution (e.g. Debian, Fedora, Kali Linux or SuSE Linux).

3. **Run the freshly installed Ubuntu.**

4. **Allocate username and password.**

5. **Update Ubuntu:** Unfortunately, the versions from the Microsoft Store are not up to date, so you should update the installed Linux version first:

   ```
   sudo apt update && sudo apt upgrade
   ```

From now on, the powerful command line of Ubuntu-Linux with all its possibilities is available.

**Tip:** the hard disk or SSD C: can be found under /mnt/c (D: under /mnt/d and so on).

Links:
------

* [Ubuntu](https://www.ubuntu.com)
* [Wikipedia: Windows Subsystem for Linux](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux)