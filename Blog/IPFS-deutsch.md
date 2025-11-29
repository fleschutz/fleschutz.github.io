![Bild](/img/BannerIPFS.jpg)

(Foto: pixabay.com)

Einführung in IPFS
==================

***IPFS* steht für "InterPlanetary File System", dahinter steckt aber weit mehr als "nur" ein Filesystem. IPFS nutzt viele clevere Tricks und könnte unser Netzwerk der Zukunft werden.** 

... ![Bild](/img/MF.png) *Von Markus Fleschutz* 🕓 *26. Mai 2018*

Content-based Addressing
------------------------

Das Internet nutzt bisher zumeist **Location-based Addressing:** damit werden Medien (z.B. ein Video) ausschließlich über ihren Ablageort gefunden. Dazu werden die Medien nach der URL-Namensauflösung (wie z. B. "http://youtube.de") über die Server-IP-Adresse und den Dateipfad erreicht. Dies funktioniert aber nur, solange (1.) der genannte Server existiert, (2.) eine Verbindung zu ihm aufgebaut werden kann, (3.) er die Medien an der richtigen Stelle bereit stellt und (4.) die Verbindung bestehen bleibt (ansonsten erhält man unter anderem den bekannten Fehler 404).

Beim neuen **Content-based Addressing** hingegen werden Medien über ihre eindeutige Checksumme gefunden, ähnlich der ISBN-Nummer für Bücher. Dies bietet gleich mehrere Vorteile:

👍 Hält mindestes ein Server weltweit den Content bereit, dann wird er auch gefunden.

👍 Bieten mehrere Server den Content an, dann kann der schnellere gewählt werden und zusätzlich auch parallel geladen werden. Bei Verbindungsverlust kann jederzeit unterbrechungsfrei umgeschaltet werden.

👍 Fallen Teile des Internets aus, dann kann der Content auch über Umwege ausgeliefert werden.

👍 Der Content ist garantiert unverändert, denn jegliche Veränderung des Inhalts ändert auch zwangsläufig die Checksumme.

👍 Caching-Server können beliebten Content nahe am Benutzer und somit schnell vorrätig halten. Dies funktioniert auch über die Grenzen unseres Planeten hinweg.

👍 Backup-Server können wertvollen Content für die Ewigkeit sichern. Damit wird es dann auch erstmalig "ewige" Links geben.

Aufteilung in Pakete
--------------------

Größere Dateien werden von *IPFS* automatisch in 256 KB-Pakete aufgeteilt. Auch das bietet mehrere Vorteile:

👍 Oft enthalten unterschiedliche Mediendateien identische Pakete. Diese belegen bei IPFS auch nur einen Speicherplatz.

👍 Identische Pakete können auch von einem anderen Server geladen werden. Dies sorgt für eine gleichmäßigere Auslastung aller Server.

👍 Beim Download können diese einzelnen Pakete parallel geladen und erst zum Schluss zusammengesetzt werden. Somit könnte ein 2 MB-Bild von 10 verschiedenen Servern geladen worden sein.

100% Distributed
----------------

Viele der Internet-Dienste die wir heute nutzen, sind zentralisiert (**centralized**). Fällt dann das zentrale Element aus (z. B. durch Angriffe, Konfigurationsfehler, Hardwarefehler, etc.), dann fällt auch automatisch der gesamte Dienst aus. 

Als Abhilfe versuchen viele Betreiber dies durch einen dezentralen Ansatz (**decentralized**) auszugleichen, aber auch hier treffen Ausfälle viele Benutzer.

*IPFS* hingegen ist 100% **distributed**, ohne einen Single Point of Failure. 

![Bild](/img/Distributed.jpg)

Fazit
-----

Durch *IPFS* kann das Internet so robust wie unsere Wasserversorgung werden:

- Content steht jederzeit **sicher**, **schnell** und **unverändert** zur Verfügung.
- Es gibt **keinen Single Point of Failure**, dadurch haben Angriffe oder Ausfälle maximal regionale Auswirkungen.
- Auch bei langen Signallaufzeiten (z.B. zu anderen Planeten) oder bei Verbindungsabbrüchen steht der Content zur Verfügung (deshalb "Interplanetary")

 Weblinks
 --------

- [ipfs.io](https://ipfs.io) - die Homepage von IPFS 
- [IPFS Desktop](https://docs.ipfs.io/install/ipfs-desktop/) - Installationsanleitung von IPFS Desktop
- [blog.ipfs.io](https://blog.ipfs.io) - Blog und Neuigkeiten von IPFS 
- [discuss.ipfs.io](https://discuss.ipfs.io/) - Diskussionsforum rund um IPFS 
- [awesome.ipfs.io](https://awesome.ipfs.io) - Apps, Services und Datensätze basierend auf IPFS 
- [IPFS Public Gateways](https://ipfs.github.io/public-gateway-checker/) - aktuelle Liste von Web-Zugängen zu IPFS 
- [Wikipedia: IPFS](https://en.wikipedia.org/wiki/InterPlanetary_File_System) 
