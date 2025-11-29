![Bild](/img/BannerBoat.jpg)

(Bild: pixabay.com)

Anwendungsabsturz-Dumps unter Windows
==================================

**Absturzdumps (auch 'Memory Dumps' oder 'Core Dumps' genannt) sind extrem hilfreich, um Anwendungsabstürze oder -aufhängungen zu untersuchen. Um solche Crash-Dumps abzurufen und zu analysieren, folgen Sie den unten stehenden Anweisungen. Dies funktioniert auf allen Windows-Versionen ab Vista und Server 2008.**

... ![Bild](/img/MF.png) *von Markus Fleschutz* 🕓 *6. Mai 2020*

## 1️⃣ Crash Dumps aktivieren

Standardmäßig wird kein Crash-Dump geschrieben, wenn eine Windows-Anwendung abnormal beendet wird. Um dies zu aktivieren, gehen Sie wie folgt vor:

1. Öffnen Sie den **Registrierungseditor** (z. B. durch Ausführen von `regedit`).
2. Suchen Sie nach dem Registrierungsschlüssel `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\Windows Error Reporting\LocalDumps`.
3. Erstellen Sie den Schlüssel (falls nicht bereits vorhanden): Rechtsklick → Neu → Schlüssel, und nennen Sie ihn `LocalDumps`.

**HINWEIS:** Windows-Updates setzen diesen Schlüssel manchmal auf den Standardwert zurück und deaktivieren damit die Crash-Dumps!

## 2️⃣ Bringen Sie die Anwendung zum Absturz

Reproduzieren Sie das Problem und bringen Sie die Anwendung zum Absturz. Falls sich die Anwendung aufhängt, starten Sie den **Task Manager** (z.B. durch Drücken von `Strg-Alt-Entf`), klicken Sie mit der rechten Maustaste auf den Prozess und wählen Sie `Dump-Datei erstellen`.

Starten Sie den **Windows Explorer** und suchen Sie die Dump-Datei im Ordner `%LOCALAPPDATA%\CrashDumps` mit der Dateiendung `.dmp`.

Beispiel Dump-Datei: `C:\Users\<USERNAME>\AppData\Local\CrashDumps\App.exe.3652.dmp`

**HINWEIS:** Dieser Ordner enthält standardmäßig nur bis zu 10 Dump-Dateien! Dump #11 wird die älteste Dump-Datei #1 ersetzen. Verschieben Sie daher die Dump-Dateien in einen anderen Ordner, um ein Entfernen zu vermeiden!

## 3️⃣ Analysieren Sie den Crash-Dump

Bitte beachten Sie, dass dieser Schritt nur von Softwareentwicklern durchgeführt wird. Normalerweise senden Sie die Crash-Dump-Datei einfach mit einem Fehlerbericht an den Softwarehersteller.

1. Kopieren Sie die `.dmp`-Crash-Dump-Datei in den Ordner, in dem sich die entsprechenden `.pdb`-Dateien befinden (dies hilft bei der Auflösung der symbolischen Namen von Funktionen, Methoden, Variablen usw.).
2. Doppelklicken Sie auf die `.dmp`-Datei - dies sollte die Entwicklungsumgebung (z.B. *Visual Studio*) starten und grundlegende Informationen anzeigen. Klicken Sie dann auf `Debug with Native Only` (in der oberen rechten Ecke)
3. Klicken Sie auf `Call Stack` (rechte untere Ecke), um den Aufrufstapel des aktuellen Threads und die lokalen Variablen zu sehen.
4. Vergessen Sie nicht, die anderen Threads auszuwählen, um deren Aufrufstapel und die lokalen Variablen zu überprüfen!








































