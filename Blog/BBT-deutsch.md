![Bild](/img/BannerBBT.jpg)

(Foto: pixabay.com)

Big Bang Time & Planck Time
===========================

**Unsere heutige Zeitrechnung und Zeitdarstellung basiert auf der Erdrotation und der Erd-Bewegung um die Sonne, somit ist sie perfekt für uns Menschen auf der Erde angepasst. Weniger geeignet ist sie jedoch für Computer, in der Archäologie, der Astronomie und in der Raumfahrt. Für diese Fälle wird eine neue, globale Zeitrechnung benötigt.**

... ![Bild](/img/MF.png) *Von Markus Fleschutz* 🕓 *16. September 2017*

Das Bezugsdatum
---------------

Jede Zeitrechnung hat einen Zeitpunkt, von dem aus gezählt wird; wie etwa der Geburtstag oder Todestag des Religionsstifters oder Herrschers. Als Bezugsdatum für die Big Bang Time (BBT) wird die Entstehung des Universums (Urknall, Big Bang) festgelegt. Das Alter des Universums wurde im Jahre 2013 durch das Planck-Weltraumteleskop wie folgt gemessen: 13,82 ± 0,04 Milliarden Jahre. Somit wird festgelegt:

**BBT1 = 1. Januar 2013 00:00:00 UTC - 13.820.000.000 Jahre**

BBT1 bedeutet BBT Version 1. Version 1 deshalb da die Berechnung des Zeitpunkts des Urknalls in der Zukunft immer genauer werden dürfte. Diese neuen Berechnungen werden als neue Versionen einfach hochgezählt (BBT2, BBT3 und so weiter).

Die Zeiteinteilung
------------------

Jede Zeitrechnung teilt die Zeit in Abschnitte ein. Als Zeiteinteilung für die BBT wird die standardisierte SI-Sekunde (Atomsekunde) festgelegt. Menschen als auch Maschinen können mit Sekunden problemlos umgehen, außerdem können Atomuhren sie extrem genau messen. Die SI-Sekunde ist eine der Basiseinheiten im internationalen Einheitensystem SI und seit 1967 folgendermaßen definiert:

> Die Sekunde ist das 9.192.631.770-fache der Periodendauer der dem Übergang zwischen den beiden Hyperfeinstrukturniveaus des Grundzustandes von Atomen des Nuklids 133 Cs entsprechenden Strahlung.
>

BBT-Zeitpunkte
--------------

Ein vollständiger BBT-Zeitpunkt wird wie folgt angegeben: **BBTn[+|-]SEKUNDEN**, zum Beispiel: BBT1+100 bedeutet 100 Sekunden nach dem Urknall, BBT1+100,1 bedeutet 100 Sekunden und eine Zehntelsekunde nach dem Urknall und BBT1-1 bedeutet 1 Sekunde vor dem Urknall.

Der 1. Januar 2013 00:00:00 UTC entspricht dann BBT1+436.126.032.000.000.000, da in SI-Einheiten gilt: 1 y = 31.557.600 s (365,25 Tage).

BBT im Computer
---------------

Für Computer ist die Speicherung der BBT in einem Datentyp mit mindestens 64 Bit mit Vorzeichen vorzusehen (Minimum SignedInt64) sowie zusätzlich die Versionsnummer. Vorzeichenbehaftet deshalb, um die Zeit vor dem Urknall darstellen zu können.

Die meisten Computer rechnen intern mit der Unixtime (Sekunden seit 1. Januar 1970 00:00:00 UTC) und dieser Zeitpunkt entspricht BBT1+436.126.030.643.023.200. Somit gilt für die Umrechnung:

```
BBT1 = Unixtime + 436.126.030.643.023.200
```

sowie umgekehrt:

```
Unixtime = BBT1 - 436.126.030.643.023.200
```

SI-Präfixe
----------

Für uns Menschen ist der Umgang mit großen Zahlen nicht leicht. Deshalb ist die Einheit Sekunde mit verschiedenen Vorsätzen für Maßeinheiten (SI-Präfixe) in Verwendung:

```
1 Ks = 1000 s (Kilosekunde, ca. 16,67 Minuten)
1 Ms = 1.000.000 s (Megasekunde, ca. 11,57 Tage)
1 Gs = 1.000.000.000 s (Gigasekunde, ca. 31,69 Jahre)
1 Ts = 1.000.000.000.000 s (Terasekunde, ca. 31.688,74 Jahre)
1 Ps = 1.000.000.000.000.000 s (Petasekunde, ca. 31 Millionen Jahre)
1 Es = 1.000.000.000.000.000.000 s (Exasekunde, ca. 758 Milliarden Jahre)
```

Die Planck Time (PT)
--------------------

Um für uns Menschen den Umgang mit der BBT zu erleichtern, werden zusätzliche Namen wie die Planck Time für Referenz-Zeitpunkte eingeführt. Es gilt:

**PT = BBT1+436.126.032.000.000.000** (Planck Time, 1. Januar 2013 00:00:00 UTC)

Dieser Name wurde zu Ehren der Messung mit Hilfe des Planck-Weltraumteleskops eingeführt (das Weltraumteleskop selber wurde mittlerweile abgeschaltet). Damit wird automatisch auch die Komplexität der Zahlen halbiert, denn PT steht für 436.126.032 * 10 ^ 9.  Ein vollständiger Plank-Zeitpunkt mit mindestens 9 Dezimalstellen lautet dann zum Beispiel:

**PT+000.000.000 = 1. Januar 2013 00:00:00 UTC**

Ein Beispiel:

```
PT+123.456.789 = Freitag, 27. Januar 2017 21:33:09 UTC
             ^------ Sekunden
            ^------- Zehnersekunden
           ^-------- Hundertersekunden (ca. 1,66 Minuten)
         ^---------- Kilosekunden (1 Ks = ca. 16,67 Minuten)
        ^----------- Zehnkilosekunden (10 Ks = ca. 2,7 Stunden)
       ^------------ Hundertkilosekunden (100 Ks = ca. 27,77 Stunden)
     ^-------------- Megasekunde (1 Ms = ca. 11,57 Tage)
    ^--------------- Zehnmegasekunde (10 Ms = ca. 115,7 Tage)
   ^---------------- Hundertmegasekunde (100 Ms = ca. 1157,4 Tage)
```

Mit der Planck-Zeit lässt sich auch einfacher rechnen, zum Beispiel:
PT+000.123.456 + 1000 Sekunden = PT+000.124.456 

Weitere Namen für Referenz-Zeitpunkte werden zu gegebener Zeit eingeführt.
