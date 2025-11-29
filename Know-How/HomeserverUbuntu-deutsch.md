![Bild](/img/BannerServer.jpg)

(Foto: pixabay.com)

Homeserver mit Ubuntu aufsetzen
=====================================

**Irgendwann ist Schluss: ein neuer PC muss her. Doch muß man wirklich den alten PC entsorgen oder kann er sogar als Homeserver für die ganze Familie dienen? Wir zeigen was ein Homeserver kann und wie der Umbau gelingt.** 

... ![Bild](/img/MF.png) *Von Markus Fleschutz* 🕓 *15. Mai 2020*

Welche Features bietet ein Homeserver?
-------------------

- **Zentraler Datenspeicher** für Filme, Fotos, eBooks, Dokumente, usw.
- **Zentrales Backup** für die Daten aller Geräte und Services 
- **DLNA-Server** um Filme, Musik und Fotos an Smart-TV's auszuliefern
- **Dashkiosk** für beliebige Geräte (Digital Signage)
- **Digitaler Videorekorder**
- **Audio/Video-Konferenz**-Server
- **Smart Home Server**
- **Game-Server** für ARK, Minecraft, etc.
- **Web-Server** für die eigene Homepage
- **Git-Server** für eigene Software-Projekte
- **grafana-Server** für die Daten-Visualisierung
- **NextCloud**-Server / **IPFS**-Server / **Remote Desktop** / und vieles mehr

1️⃣ Die Hardware
-------------------

Ein Homeserver benötigt ein Mainboard mit einer stabil laufenden CPU (CPU-Lüfter prüfen und säubern!), ein Netzteil, ausreichend RAM (je mehr desto besser), mindestens eine SSD oder Festplatte (evtl. Lüfter notwendig!) und einen Netzwerkanschluss (mindestens Gigabit-Ethernet). 

Im BIOS sollte ein evtl. Übertakten rückgängig gemacht werden und am besten das neueste  BIOS-Update eingespielt werden. Auf Nummer sicher geht, wer die BIOS-Einstellungen auf Default setzt.

>  **Hinweis:** Jede zusätzliche Hardware bedeutet nicht nur höherer Stromverbrauch, sondern auch höhere Ausfallwahrscheinlichkeit!

2️⃣ Betriebssystem installieren
-----------------------------

1. Unter Windows/Linux/MacOS die Software **UNetbootin** herunterladen und ausführen, danach die **Ubuntu Server Live 20.04 LTS (64-bit)** auf einen USB-Stick (min. 4 GB Kapazität) herunterladen und installieren. Danach den USB-Stick ordnungsgemäß auswerfen. Wichtig zu wissen: Die LTS-Versionen werden bis zu 10 Jahre unterstützt, alle anderen bis zu 2 Jahren.
2. Den Homeserver mit dem USB-Stick starten und zuerst das BIOS konfigurieren. Evtl. ein BIOS-Update einspielen, die Boot-Reihenfolge mit USB-Stick als Nummer 1, evtl. Übertakten abschalten, Wake-On-LAN für die Netzwerk-Karte einschalten, EuP 2013 abschalten, ... by BIOS abschalten. Danach "Save & Reboot".
3. Installiere Ubuntu Server: Sprache: Englisch, Tastatur: Deutsch, Mode "Install on entire disk". Zum Schluss den USB-Stick entfernen und Rebooten.

> **Hinweis:** Nach der Betriebssystem-Installation Grafikkarte, CD/DVD/Floppy-Laufwerke und alle anderen nicht mehr benötigten PCI-Karten entfernen!

## 3️⃣ sudo ohne Passwortabfrage

Bereits beim Einloggen mit ssh oder per Desktop wird das Passwort abgefragt. Darüber hinaus bei jedem sudo-Kommando das Passwort eingeben zu müssen ist einfach nur lästig. Als Abhilfe editiert man einfach die Datei /etc/sudoers mit einem Texteditor und hängt folgende Zeile an: (*tom* durch den Benutzernamen ersetzen)

```
tom ALL=(ALL) NOPASSWD:ALL
```

## 4️⃣ Livepatch Service aktivieren

Mit **Live Patching** können Kernel Security Fixes installiert werden, ohne das der PC neu gestartet werden muß. Somit werden Ausfallzeiten des Homeservers stark reduziert. Bis zu 3 Geräte können kostenlos damit ausgestattet werden. 

[Auf diesen Link klicken](https://auth.livepatch.canonical.com), ein Token erhalten und wie folgt aktivieren:

```
$ sudo snap install canonical-livepatch
$ sudo canonical-livepatch enable [TOKEN]
```

5️⃣ Software-Pakete installieren
---------------------------------------

Aus Sicherheitsgründen werden nur die nötigsten Software-Pakete installiert:

```
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install htop smartmontools samba curl pm-utils hddtemp snap zfsutils-linux zfs-initramfs zip
```
Und zur Sicherheit gleich Festplatten/SSD's mit *S.M.A.R.T* überprüfen: (XXX ersetzen)

```
$ sudo smartctl --smart=on --nocheck=standby --offlineauto=on -t long /dev/sdXXX
```

und nach Testende:

```
$ sudo smartctl -a /dev/sdXXX
```

6️⃣ Snaps installieren
----------------------

Snaps sind Software-Pakete, die völlig isoliert voneinander laufen, alle notwendigen Libraries gleich mitbringen und nur Zugriff auf freigegebene Bereiche haben. All dies zusammen erhöht die System-Stabilität ganz beträchtlich. Für einen Homeserver sind folgende Snaps besonders interessant:

1. Der kompakte Medienserver **MiniDLNA**

   MiniDLNA ist ein kompakter DLNA/UPnP Medienserver. Er liefert Mediendateien (Musik, Bilder, Videos) an Smart-TV's, Computer, Laptop, Tables, und Handys im Heim-Netzwerk. Mit dem folgenden Kommando wird der DLNA-Server heruntergeladen und gestartet:

   ```
   $ sudo snap install --classic minidlna-escoand
   ```

   Die Konfiguration ist unter `/var/snap/minidlna-escoand/current/minidlna.conf` anzupassen (nur das Media-Verzeichnis). Mit dem Browser erreicht man den Server unter `http://<RECHNERNAME>:8200` und geloggt wird nach `/var/snap/minidlna-escoand/common/minidlna.log`.

2. Daten-Synchronisation mit **NextCloud**

   ```
   $ sudo snap install nextcloud
   ```

   Jetzt kann der neu installierte NextCloud-Server mit dem Browser unter `http://<RECHNERNAME>` erreicht und eingerichtet werden.

3. Der Web-Server **caddy**:

   ```
   $ sudo snap install caddy-hduran
   ```

4. Der Smart Home Server **openHAB**:

   ```
   $ sudo snap install openhab
   ```
   Unter `http://<RECHNERNAME>:8080` kann danach der openHAB-Server eingerichtet und genutzt werden.

5. Dateien verteilen: **IPFS-Server**

   ```
   $ sudo snap install ipfs
   $ ipfs init
   $ ipfs config Addresses.API /ip4/0.0.0.0/tcp/5001
   $ ipfs config Addresses.Gateway /ip4/0.0.0.0/tcp/8765
   $ ipfs daemon &
   ```
   Mit dem Browser erreicht man dann den IPFS-Server unter `http://<RECHNERNAME>:5001/webui`. Eine Port-Weiterleitung für den Router muss noch für Port 4001 eingerichtet werden.

6. Audio/Video-Anrufe und -Konferenzen mit **Spreed WebRTC**:

   ```
   $ sudo snap install spreed-webrtc-snap
   ```

   Danach erreicht man den WebRTC-Server unter `http://<RECHNERNAME>:8084`

7. Der Datenbank-Server **PostgreSQL**:

   ```
   $ sudo snap install postgresql10
   ```

8. Automatisierung mit dem **Jenkins-Server**

   ```
   $ sudo snap install jenkins
   ```

   Danach erreicht man den Jenkins-Server unter `http://<RECHNERNAME>:8080`

9. Für Gamer ein **Minecraft-Server**:

   ```
   $ sudo snap install minecraft-server-jdstrand
   $ sudo minecraft-server-jdstrand.util help     <-- danach den Anweisungen folgen
   ```

   Und danach noch eine Weiterleitung des Port 25565 beim Router einrichten.

10. Die Medienzentrale **Plex Media Server**:

  ```
  $ sudo snap install plexmediaserver
  ```

  Unter  `http://<RECHNERNAME>:32400/web` kann der Plex Media Server dann eingerichtet und genutzt werden. 
**Pro Tipp:** Plex kann auch die Medien mehrerer Maschinen unter einer einheitlichen Oberfläche verwalten!

11. Der digitale Videorekorder **tvheadend**:

    ```
    $ sudo snap install tvheadend
    ```

    Danach erreicht man tvheadend unter `http://<RECHNERNAME>:9981`.

12. **Dashkiosk**:

    ```
    $ sudo snap install dashkiosk
    ```

    Den Administrationsbereich erreicht man unter `http://<RECHNERNAME>:9400/admin` und unter `http://<RECHNERNAME>:9400/receiver` läuft dann der eigentliche Dashkiosk. 
    
13. Der eigene DNS-Server **AdGuard Home**:

    ```
    $ sudo snap install adguard-home
    ```

    Und danach kann AdGuard Home mit dem Browser unter `http://<RECHNERNAME>:3000` eingerichtet werden.

14. Die eigene Such-Maschine **yacy-search**:

    ```
    $ sudo snap install yacy-search
    $ yacy-search.password              <- admin-Passwort festlegen
$ yacy-search                       <- Suchmaschine starten
    ```

    Danach erreicht man die Suchmaschine mit dem Browser unter `http://<RECHNERNAME>:8090` und richtet erst mal alles ein.
    
15. Daten visualisieren mit **grafana**:

    ```
    $ sudo snap install grafana
    ```

    Danach erreicht man grafana mit dem Browser unter `http://<RECHNERNAME>:3000`

    

Viele weitere Snaps samt Beschreibung finden sich im [Snap Store](https://snapcraft.io/store). 

**Hinweis:** generell sind Snaps je nach Stabilität in einen der folgenden Channels eingestuft: von *edge* (brandneu), über *beta* (Test-Version), *candidate* (Release-Kandidat) bis hin zu *stable* (stabil). In der Voreinstellung wird nur vom sicheren *stable*-Channel installiert. 

7️⃣ Dropbox installieren
----------------------

Der Dropbox-Daemon ist mit allen 32-Bit und 64-Bit-Linux Servern kompatibel. Wenn Sie ihn installieren möchten, führen Sie in Ihrem Linux-Terminal den folgenden Befehl aus. Für 32-Bit:

```
cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86" | tar xzf -
```

Und für 64-Bit:

```
cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86_64" | tar xzf -
```

Führen Sie den Dropbox-Daemon danach von dem neuen `.dropbox-dist` -Ordner aus aus.

```
~/.dropbox-dist/dropboxd
```

Wenn Sie Dropbox zum ersten Mal auf Ihrem Server ausführen, werden Sie aufgefordert, zum Erstellen eines neuen Kontos einen Link zu kopieren und in einen Browser einzufügen oder Ihren Server mit einem vorhandenen Konto zu verknüpfen. Anschließend wird in Ihrem Basisverzeichnis der Dropbox-Ordner erstellt. Laden Sie dieses [Python-Skript](https://www.dropbox.com/download?dl=packages/dropbox.py) herunter, um Dropbox über die Kommandozeile zu steuern. Um schneller darauf Zugriff zu haben, fügen Sie dem Skript an einer beliebigen Stelle im PATH einen Symlink hinzu.

8️⃣ Remote Desktop mit X2Go installieren
-------------------------

Auf dem Homeserver führen Sie bitte aus:

```
$ sudo add-apt-repository ppa:x2go/stable
$ sudo apt update
$ sudo apt install x2goserver x2goserver-xsession xfce4-session
```

Danach auf den Windows-PC's den **X2Go Client** installieren und ausführen (Sitzungsart XFCE wählen)

9️⃣ Health-Check
----------------

Dazu in regelmäßigen Abständen das folgende Shell-Script ausführen.

```
#!/bin/sh
#
# NOTE: to be started as superuser! Requires package hddtemp and smartctl!

echo "\n(1/5) Checking uptime: `uptime --pretty` since `uptime --since`"

echo "\n(2/5) Checking temperature ..."
hddtemp --unit=C /dev/sda /dev/sdb

echo "\n(3/5) Checking HDD/SSD ..."
smartctl --smart=on --nocheck=standby --offlineauto=on --health /dev/sda
smartctl --smart=on --nocheck=standby --offlineauto=on --health /dev/sdb

echo "\n(4/5) Checking filesystem ..."
zpool list
zpool status

echo "\n(5/5) Checking for updates ..."
apt update
apt upgrade
snap refresh
```

## Weblinks

- [UNetbootin](https://unetbootin.github.io/)
- [Ubuntu Homepage](https://www.ubuntu.com)
- [Snap Store](https://snapcraft.io/store)
