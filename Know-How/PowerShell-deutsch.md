![Bild](/img/BannerPowerShell.webp)

(Foto: pixabay.com)

Automatisierung mit PowerShell
========================

**Wiederkehrende Aufgaben am Computer lassen sich bequem per Shell-Skript automatisieren. Zur Auswahl stehen die Bourne Shell (bsh), die Bourne Again Shell (bash), die C Shell (csh), die Korn Shell (ksh), PowerShell und viele mehr. Aber nur *PowerShell* ist als Open-Source-Projekt plattformübergreifend für Linux, MacOS und Windows unter der MIT-Lizenz verfügbar.** 

... ![Bild](/img/MF.webp) *Von Markus Fleschutz*  🕓 *11. Januar 2019*

Die Kommandozeile
----------------------

Um PowerShell auszuprobieren benötigt man eine Text-Konsole. Dazu bietet sich das komfortable *Windows Terminal* an (kostenlos erhältlich im Windows App Store) . 

PowerShell bietet unter anderem folgende Kommandos an:

* **cat** <Dateiname> - gibt den Inhalt der angegebenen Datei aus
* **cd** <Ordner>- wechselt in den angegeben Ordner
* **cd ..** - wechselt eine Order-Ebene höher
* **clear** - löscht die Anzeige in Konsolen-Window
* **cp** <Quell-Dateiname> <Ziel-Dateiname> - kopiert die angegebene Datei
* **date** - zeigt die Systemzeit des Rechners an
* **diff** <Dateiname1> <Dateiname2> - zeigt den Unterschied beider Dateien an
* **echo** <Text> - gibt den angegebenen Text aus
* **echo** $Variable - gibt den Inhalt der angegeben Variable aus
* **exit** - beendet die PowerShell-Konsole, bzw. das PowerShell-Script
* **help** - zeigt die Hilfe zu PowerShell-Cmdlets und -Konzepten an (sehr hilfreich !!!)
* **history** - zeigt die bisher eingegebenen Befehle an
* **hostname** - gibt den Namen des Rechners aus
* **kill** <Prozess-ID> - beendet den angegebenen Prozess
* **ls** - listet den Inhalt eines Dateiordners
* **mkdir** <Ordnername> - erstellt einen Ordner mit dem angegebenen Namen
* **mv** <Quell-Dateiname> <Ziel-Dateiname> - verschiebt die angegebene Datei
* **ping** <hostname|IP adress> - prüft, ob der angegebene Rechner im Netzwerk erreichbar ist
* **ps** - listet alle gegenwärtig laufende Prozesse
* **pwd** - gibt den aktuellen Dateipfad aus
* **rm** <Dateiname> - löscht die angegebene Datei oder den angegebenen Ordner (!)
* **set** <Variablenname> <Wert> - setzt die angegebene Variable auf den angegebenen Wert
* **sleep** <Sekunden> - wartet die angegebene Anzahl von Sekunden
* **wget** <URL> - lädt die angegebene Datei aus dem Internet herunter

## Cmdlets

Die oben genannten Kommandos sind tatsächlich Aliase zu sogenannten "Cmdlets".  Cmdlets bestehen immer aus einem Verb, einem Bindestrich und einem Nomen, zum Beispiel `Get-ChildItem` (Datei-Ordner anzeigen). Mit `Get-Command` und `Show-Command` lassen sich Cmdlets suchen und finden. Welche Cmdlets zur Verfügung stehen, hängt nicht nur von der eingesetzten PowerShell-Version ab, sondern auch vom Betriebssystem und der installierten zusätzlichen Softwareausstattung. Cmdlets sind grundsätzlich in Modulen beheimatet.

PowerShell-Skripte schreiben
--------------------------------

Mit einem beliebigen Texteditor erstellt man eine neue Datei namens `HelloWorld.ps1` mit folgendem Inhalt:

```
echo "Hallo Welt!"
sleep 10
```

Danach die Datei abspeichern und mit einem Rechtsklick **Mit PowerShell ausführen** wählen. Schon wird das Skript ausgeführt.

## PowerShell-Features

PowerShell ist mächtig! Die Möglichkeiten von PowerShell reichen schon fast an eine Programmiersprache heran. Und die nachfolgenden Beispiele funktionieren sowohl in einem PowerShell-Skript als auch in der PowerShell-Konsole. Also einfach mal ausprobieren!

### Beispiel 1: Variablen & Zahlen

```
$PI = 3.1415927
echo $PI
```

### Beispiel 2: Variablen & Text

```
$var = "Hallo "
$var += "John"
echo $var
```

### Beispiel 3: Variablen & Text Arrays

```
$days = "Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"
foreach($day in $days) {
	echo $day
}
```

### Beispiel 4: Mehrere Variablen initialisieren

```
$a = $b = $c = 1
echo $a, $b, $c
```

```
$a, $b, $c = 1, 2, 3
echo $a, $b, $c
```

### Beispiel 5: Variablen & Programmausgaben

```
$output = ls
echo $output
```

### Beispiel 6: for-Schleifen

```
for($i = 0; $i -le 100; $i++) {
	echo "Hallo"
}
```

### Beispiel 7: foreach-Schleifen

```
$colors = "red","green","blue"
foreach($color in $colors) {
	echo $color
}
```

### Beispiel 8: do-while-Schleifen

```
do {
	echo "Hallo"
} while ($false)
```

### Beispiel 9: while-Schleifen

```
while ($true) {
    echo "Hallo"
    break
}
```

### Beispiel 10: Endlos-Schleifen

```
while ($true) {
	echo "ENDLOS"
}
```

### Beispiel 11: Kommentare

```
# Kommentar
1 + 1 # sollte 2 ergeben
```

### Beispiel 12: Vergleichsoperatoren

```
1 -eq 1     # ist gleich?
0 -ne 1     # ist ungleich?
0 -lt 1     # ist kleiner als?
0 -le 1     # ist kleiner oder gleich?
1 -gt 0     # ist größer?
1 -ge 0     # ist größer oder gleich?
"PowerShell" -like "Pow*"           # Vergleich mit Wildcards (Gegenteil: -notlike)
"Jan","Feb","March" -contains "Feb" # Vergleich mit Arrays (Gegenteil: -notcontains)
"PowerShell" -match "ower"          # Vergleich mit Teilstring (Gegenteil: -notmatch)
1 -and 1     # logisches UND
1 -or 0      # logisches ODER
1 -xor 0     # logisches EXKLUSIV-ODER
-not 0       # logische NEGIERUNG
!0           # logische NEGIERUNG
```

### Beispiel 13: Text-to-Speech (TTS)

```
$voice = New-Object –ComObject SAPI.SPVoice
$voice.Speak("Hi developer");
```

### Beispiel 14: Zeit in HTML/JSON/CSV umwandeln

```
Get-Date | ConvertTo-Html
Get-Date | ConvertTo-Json
Get-Date | ConvertTo-CSV
```

### Beispiel 15: Aliase in HTML umwandeln

```
Get-Alias | ConvertTo-Html | Out-File aliases.html
```

### Beispiel 16 für Skripte: Benutzereingaben

```
$age = Read-Host "Enter your age"
echo $age
```

### Beispiel 17 für Skripte: Passwort-Eingabe

```
$password = Read-Host "Enter password" -assecurestring
echo $password
```

### Beispiel 18 für Skripte: Zeit messen

```
$start = Get-Date
# some code ...
$stop = Get-Date
$interval = New-Timespan -start $start -end $stop
echo "$interval"
```

## Beispiel 19 für Skripte: Fehler abfangen

```
try {
	# some code ...
} catch { Write-Error $Error[0] }
```

### Beispiel 20 für Skripte: Funktionen

```
function MyPing {
	$Hostname = $args[0]
	Test-Connection $Hostname
}
MyPing 192.168.1.100
```

PowerShell Remoting
--------------

Mit *PowerShell Remoting* kann ein entfernter Rechner über Secure Shell (SSH) und PowerShell ferngesteuert werden. Dazu installiert und konfiguriert man den SSH-Server auf dem entfernten Windows-Rechner in einer PowerShell-Konsole mit Administrationsrechten wie folgt:

```
Add-WindowsCapability -Online -Name OpenSSH.Server*
Start-Service sshd
Set-Service -Name sshd -StartupType 'Automatic'
```

und den SSH-Client auf dem lokalen Rechner mit:

```
Add-WindowsCapability -Online -Name OpenSSH.Client*
```

Jetzt kann man mit folgendem Kommando auf dem entfernten Rechner arbeiten:

```
ssh <BENUTZER>@<RECHNERNAME>
```

Übliche Datei-Endungen in PowerShell
------------------------

```
<Dateiname>.PS1    →  PowerShell Shellskript
<Dateiname>.PS1XML →  PowerShell Format- und Typdefinitionen
<Dateiname>.PSC1   →  PowerShell Konsolendatei (exportierte Shell-Konfiguration)
<Dateiname>.PSD1   →  PowerShell Datendatei
<Dateiname>.PSM1   →  PowerShell Moduldatei
```

Weblinks
----------------------

* [wikipedia.org/PowerShell](https://wikipedia.org/wiki/PowerShell) - alles rund um die PowerShell
* [docs.microsoft.com/en-us/powershell](https://docs.microsoft.com/en-us/powershell/) - die PowerShell-Dokumentation
* [github.com/PowerShell](https://github.com/PowerShell/PowerShell) - das PowerShell Projekt
* [github.com/fleschutz/PowerShell](https://github.com/fleschutz/PowerShell) - große Sammlung von PowerShell-Skripten
