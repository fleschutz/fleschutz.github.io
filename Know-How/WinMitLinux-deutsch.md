![Bild](/img/BannerLinux.jpg)

(Foto: pixabay.com)

Windows 10: Linux ausprobieren 🐧
==============================

**Einfach mal Linux unter Windows ausprobieren? Ohne extra PC, zweite Partition, Dual-Boot-System und ähnlichen Aufwand? Ja, das geht: das *Windows Subsystem for Linux* (WSL) erlaubt es, Linux-Terminal-Anwendungen unter Windows 10 (ausgenommen Windows 10 S) auszuführen.** 

... ![Bild](/img/MF.png) *Von Markus Fleschutz*  🕓 *21. September 2019*

Und so geht's:

1. **Das *Windows Subsystem for Linux* (WSL) einschalten:** Dazu öffnet man zunächst die PowerShell im Administratormodus. Dort gibt man folgenden Befehl ein:

   ```
   Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
   ```

   Danach muss der Rechner gebootet werden.

2. **Den *Microsoft Store* öffnen, nach "Ubuntu" suchen und installieren.** Natürlich können Sie auch jede andere Linux-Distribution installieren (z.B. Debian, Fedora, Kali Linux oder SuSE Linux).

3. **Das frisch installierte Ubuntu ausführen.**

4. **Benutzername und Passwort vergeben.**

5. **Ubuntu updaten:** Leider sind die Versionen aus dem Microsoft Store nicht auf dem neuesten Stand, sodass man zunächst eine Aktualisierung der installierten Linux-Version durchführen sollte:

   ```
   sudo apt update && sudo apt upgrade
   ```

Von jetzt an steht die mächtige Kommandozeile von Ubuntu-Linux mit all ihren Möglichkeiten zur Verfügung.

**Tipp:** die Festplatte oder SSD C: finden Sie unter /mnt/c (D: unter /mnt/d und so weiter)

Weblinks
------

* [Ubuntu](https://www.ubuntu.com)
* [Wikipedia: Windows Subsystem for Linux](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux)