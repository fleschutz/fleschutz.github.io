![Bild](/img/BannerBoat.jpg)

(Bild: pixabay.com)

Reguläre Ausdrücke (RegEx) Spickzettel
=====================================================

... ![Bild](/img/MF.png) *Von Markus Fleschutz* 🕓 *5. Mai 2020*

## Anker

```
^ Anfang der Zeichenkette oder Anfang der Zeile
$ Ende der Zeichenkette oder Ende der Zeile
\b Wortgrenze
\B nicht Wortgrenze
\< Wortanfang
\> Ende des Wortes
```

## Übereinstimmende Zeichen

```
. jedes beliebige Zeichen außer Zeilenumbruch
[abc] irgendeines dieser Zeichen
[^abc] keins dieser Zeichen
[a-z] beliebiges Zeichen in diesem Bereich
[*a-z] kein Zeichen in diesem Bereich
\d \D beliebige Ziffer / beliebiges Zeichen außer einer Ziffer
\w \W beliebiges Wort / beliebiges Zeichen außer einem Wort
\s \S beliebiges Leerzeichen / beliebiges Zeichen außer Leerzeichen
\c beliebiges Steuerzeichen
\x beliebige hexadezimale Ziffer
\O beliebige Oktalziffer
\n entspricht Zeilenumbruch
\r passt zu Wagenrücklauf
\t entspricht einem Tabulator
\v entspricht einem vertikalen Tabulator
\f entspricht einem Seitenvorschub
\xxx entspricht dem Oktalzeichen xxx
\xhh entspricht dem Hexadezimalzeichen hh
```

## Übereinstimmende Wörter

```
ab?c passt null oder einmal, z. B. abc, ab7c
ab*c stimmt null oder mehr Mal überein, z.B. abc, ab123c
a{3} stimmt genau n-mal überein, z. B. aaa
a{3,5} stimmt zwischen n und m mal überein, z. B. aaa, aaaa, aaaaa
a{n,} stimmt mindestens n-mal überein
abc|def passt auf abc oder def
```

