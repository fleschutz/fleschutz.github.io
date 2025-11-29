Der (lange) Weg zu Windows 11
=============================

Am 4. Oktober erschien das neue Betriebssystem Windows 11. Aber weder gelingt der Umstieg von Windows 10 vollautomatisch, noch muss generell neue Hardware gekauft werden. Auf jeden Fall will der Umstieg wohlüberlegt sein, da doch einige Fallstricke lauern können.

Systemvoraussetzungen
---------------------

Das kostenlose Open-Source-Programm **WhyNotWin11** gibt Auskunft, ob der eigene Rechner und die darin verbauten Komponenten mit Windows 11 kompatibel sind (zum Download siehe: https://github.com/rcmaehl/WhyNotWin11).

![WhyNotWin11](/img/WhyNotWin11.png)

Rot markierte Einträge zeigen die Hürden für Windows 11. 

TPM 2.0 
--------

Sollte WhyNotWin11 kein Trusted Platform Module (TPM) in der Version 2.0 finden:

* Bei Desktop-PCs seit circa 2015 ist die Firmware-TPM (fTPM 2.0) auf Mainboards verbaut, aber häufig deaktiviert. Wie man das fTPM aktiviert, unterscheidet sich von Mainboard-Hersteller zu Mainboard-Hersteller, teilweise auch von Baureihe zu Baureihe. In jedem Fall muss man ins (UEFI-)BIOS-Setup, in das man durch das Drücken der Entfernen-Taste beim PC-Start gelangt (manchmal auch F2). Wie es von da an weitergeht, beschreiben die Hersteller hier:
  * Für ASRock: https://www.asrock.com/support/faq.asp?id=500
  * Für Asus: https://www.asus.com/microsite/motherboard/ASUS-motherboards-Win11-ready/
  * Für Biostar: https://www.biostar.com.tw/app/es/support/faq_content.php?S_ID=809
  * Für EVGA: https://www.evga.com/support/faq/faqdetails.aspx?faqid=59812
  * Für Gigabyte: https://www.gigabyte.com/Press/News/1925
  * Für MSI: https://www.msi.com/blog/How-to-Enable-TPM-on-MSI-Motherboards-Featuring-TPM-2-0
* Für Mainboards ohne fTPM besteht die Möglichkeit, TPM als kleines Hardware-Modul nachzurüsten.

Aufräumen
---------

Ein großes System-Update benötigt erst einmal (viel) Platz auf der Festplatte bzw. SSD und muss danach auch noch ausgepackt werden. Nutzen Sie die Gelegenheit und misten Sie aus:

* Den Desktop-Papierkorb leeren (kann nicht rückgängig gemacht werden!)
* Nicht benötigte Software (auch Apps) löschen
* Nicht benötigte Mediendateien wie Audio, Fotos, Videos, etc. löschen

Backup
------

Vor einem großen System-Update sollte unbedingt ein Backup angefertigt werden. Sollte es wider Erwarten zu größeren Problemen kommen, dann steht wenigstens kein Datenverlust im Raum.