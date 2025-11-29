![Bild](/img/BannerZFS.jpg)

(Foto: pixabay.com)

ZFS - das bessere Dateisystem
=============================

**ZFS ist die Kurzform für das Zettabyte File System. Es ist ein modernes Computer-Filesystem das entwickelt wurde, um viele der großen Probleme in vorherigen Entwicklungen zu überwinden.** 

... ![Bild](/img/MF.png) *Von Markus Fleschutz*  🕓 *9. Sept. 2019*

Was macht ZFS besser?
----------------

1. **Checksummen:** Wenn Daten geschrieben werden, wird eine Checksumme berechnet und zusammen mit den Daten gespeichert. Wenn diese Daten später wieder eingelesen werden, wird diese Checksumme erneut berechnet. Falls die Checksummen nicht übereinstimmen, wurde ein Datenfehler festgestellt. *ZFS* wird versuchen, diesen Fehler automatisch zu korrigieren ("self healing"), falls genug Datenredundanz vorhanden ist.
2. **Copy-on-Write (COW):** *ZFS* überschreibt nie ursprüngliche Daten mit neuen Daten, sondern allokiert geänderte Daten neu. Auf diese Weise sind Daten in *ZFS* zu jedem Zeitpunkt konsistent - ein Stromausfall kann das Dateisystem nicht mehr beschädigen. 
3. **Zukunftssicher für riesige Datenmengen:** *ZFS* ist ein 128-Bit-Dateisystem, im Gegensatz zu gewöhnlichen 64-Bit-Dateisystemen. Somit liegen die Grenzen bei heute unvorstellbaren 256 ZiB (Zebibyte) für die maximale Dateisystemgröße, 16 EiB (Exbibyte) für die maximale Dateigröße, sowie 281 Billionen (2 hoch 48) für die Gesamtanzahl aller Dateien.
4. **Storage Pools:** Mit den optionalen Storage Pools kombiniert man ein oder mehrere Festplatten zu einer logischen Einheit. Das ermöglicht es, Festplatten ganz nach Bedarf zum Storage Pool und den Dateisystemen hinzuzufügen und bei laufenden Systemen Speicherplatz zu schaffen, wenn er benötigt wird. 
5. **Festplatten-Redundanz:** Bei *ZFS* ist die RAID-Funktionalität bereits in der Software verankert, teure und oft unsichere Hardware-RAID-Controller sind unnötig.
6. **Snapshots:** In *ZFS* können Snapshots unbeschränkt ohne vorherige Speicherreservierung erstellt werden. Aufgrund des Copy-on-Write-Verfahrens sind die älteren Daten weiter vorhanden. Die Snapshots können sowohl archiviert als auch gemountet werden. Das Erstellen und Vorhalten von Snapshots ist somit ohne Performance-Einbußen möglich. Somit kann man problemlos Snapshots vor jeder Programminstallation, aber auch regelmäßig täglich, stündlich und viertelstündlich machen.
7. **Komprimierung:** Um Speicherplatz zu sparen, kann man Datasets mit dem LZ4-, LZJB-, GZIP- oder ZLE-Verfahren komprimieren (standardmäßig ausgeschaltet). Bei den heutigen Prozessoren lohnt es sich fast immer. Einschalten geht mit: `zfs set compression=lz4 mypool/mydataset`
8. **Native Verschlüsselung:** Damit wirklich nur berechtigte Personen Zugriff auf die Daten haben, kann man die Verschlüsselung mit dem AES-256-CCM-Algorithmus einschalten. Beispielsweise mit: `zfs create -o encryption=aes-256-ccm -o keysource=passphrase,prompt mypool/mydataset`
9. **Deduplikation:** Dadurch werden Blöcke mit identischem Inhalt nur noch einmal physisch abgelegt, was Plattenplatz spart. Ein typischer Anwendungsfall ist das Anlegen von virtuellen Festplatten für virtuelle Maschinen, die jeweils alle eine Installation eines virtualisierten Betriebssystems enthalten. Eine weitere wäre aus gleichartigen Backups redundante Information zu entfernen. Die optionale Deduplikation benötigt allerdings viel RAM (Faustregel: 1 TB Daten benötigen 1 GB RAM).

## Fazit

- ZFS schützt seine Daten, andere Filesysteme verwalten sie nur!
- Leider wird trotz all dieser Vorteile *ZFS* gegenwärtig nur durch die Betriebssysteme Solaris, FreeBSD und Linux unterstützt. Mit ein Grund ist die strikte CDDL-Lizenz, die Oracle für ZFS gewählt hat.

Weblinks
-----

* [OpenZFS (Open Source Port von ZFS für FreeBSD, Linux, OS X und Windows)](https://open-zfs.org)
* [Wikipedia: ZFS](https://en.wikipedia.org/wiki/ZFS)
* [ZFS on Linux](https://zfsonlinux.org) (Englisch)
* [ZFS Cheatsheet](https://blog.programster.org/zfs-cheatsheet) (Englisch)