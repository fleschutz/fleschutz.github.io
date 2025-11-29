![Bild](/img/BannerServer.jpg)

(Foto: pixabay.com)

Projekt: Raspi 4 + SSD = Mini-Server
=============================

**Ziel dieses Projektes ist es, einen preisgünstigen und gleichzeitig leistungsfähigen Mini-Server aufzusetzen. Dazu wird ein Raspberry Pi 4 mit einer schnellen SSD kombiniert. Für mehr Leistung und höhere Ausfallsicherheit werden einfach entsprechend mehr von diesen Mini-Servern aufgesetzt.** 

... ![Bild](/img/MF.png) *Von Markus Fleschutz* 🕓 *9. April 2023*

![Bild](/img/RasPi4.jpg)

Hardware
----------------

* **Board:** Raspberry Pi 4 Model B mit Cortex A72 CPU (4 Kerne á 1,5 GHz) und 4 GB LPDDR4-3200 SDRAM
* **Gehäuse:** MANOUII Aluminium Gehäuse ohne Lüfter (€18,99)
* **SD-Card:** 32 GB, Class 10 (wird nur zum Aufsetzen benötigt)
* **USB 3.0 auf SATA Adapter:** zur Verbindung des Boards mit der SSD (€8,99)
* **500 GB SATA SSD:** SanDisk Ultra 3D NAND, 2.5 Zoll (benötigt kein zusätzliches Stromkabel und keine Lüftung)
* **USB-C Netzteil:** 5V, 3A, 15W
* **Anschlüsse:** 2x USB 3.0, 2x USB 2.0, GPIO 40 Pins, 2x HDMI, 3.5mm Audio, WLAN, Gigabit-Ethernet
* **Gesamt-Kaufpreis:** circa 150 € (Stand 2019)

Software
--------

* **Betriebssystem:** Ubuntu Server 22.04 LTS für ARM64 
* **Installierte Pakete:** *powershell, smartmontools, ecryptfs-utils* (für verschlüsseltes Home-Dir), *evcc* (PV-Steuerung), *samba* (als File-Server), *unbound* (als DNS-Server), *gcc, clang, clang-tidy, distcc, make, ninja-build* (für Software-Entwicklung)
* **Installierte Snaps:** *ant, audacity, bashtop, cmake, emacs, gimp, htop, hw-probe, cppcheck, go, groovy, python38*, *ipfs* (als IPFS-Server), *plexmediaserver* (als Media-Server) und *minidlna-escoand* (als DLNA-Server)
* **Installierte Services:** Calibre eBook-Server, Nextcloud Media-Server, Plex Media-Server, Unbound DNS-Server

Messungen
------------------------

* **Stromverbrauch:** von 7,5 Watt (ruhend) bis maximal 15 Watt (unter Vollast)
* **Abmessungen:** 12 x 7 x 5 cm gesamt (L x B x H), entspricht 420 cm³
* **Stabilität**: läuft stabil seit 1. Juni 2020 
* **Lautstärke:** 0 dB, da lüfterlos
* **CPU-Temperatur:** von 41 °C bei Idle bis 62 °C unter Vollast, gemessen bei Zimmertemperatur 20 °C
* **Gigabit Ethernet:** 117 MB/s Durchsatz, Ping min/average/max/mdev = 0.173/0.241/0.302/0.029 ms
* **USB 3.0:** 363 MB/s Lese-Durchsatz, 323 MB/s Schreib-Durchsatz
* **Linpack Benchmark:** 13,5 GFlops, 925 MIPS single-precision, 748 MIPS double-precision, 2037 MIPS single-precision using NEON instructions
* **Effizienz:** 1,8 GFlops/W

## Fazit

👍 Daumen hoch für Stabilität, Energieverbrauch, Gesamtkosten und Effizienz

👍 Der Raspberry Pi 4 ist auch in einer Version mit 8 GB RAM verfügbar - ideal für Server

👍 Der Raspberry Pi 4 unterstützt jetzt auch das Booten über USB (die langsame und ausfallträchtige SD-Card kann entfallen)

👌 Perfekt wäre *Power over Ethernet* (PoE), dann würde auch das separate Netzteil entfallen

👎 Noch sind nicht alle Software-Pakete und Snap-Pakete für ARM64 verfügbar, hier sollte Ubuntu nachbessern 

Quellenangaben
-----

* [raspberrypi.org](https://www.raspberrypi.org) - die Raspberry Pi Homepage
* [wikipedia.org](https://de.wikipedia.org/wiki/Raspberry_Pi) - alles über den Raspberry Pi
* [ubuntu.com](https://www.ubuntu.com) - die Ubuntu Homepage
* [snapcraft.io/store](https://www.snapcraft.io/store) - der Snap Store