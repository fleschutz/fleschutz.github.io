![Image](/img/BannerServer.jpg)

(Photo: pixabay.com)

# SHORTY

**SHORTY ist ein vollständiger Public-Key-Algorithmus, er eignet sich sowohl für Verschlüsselung als auch für digitale Signaturen. Der Chiffretext ist dabei kaum größer als der Klartext und die dabei verwendete modulare Multiplikation ist weit weniger rechenintensiv als modulare Potenzierung, wie sie in anderen Algorithmen verwendet wird.** 

... ![Bild](/img/MF.png) *Von Markus Fleschutz*  🕓 *12. April 2000*

## Beschreibung

Zur Vorbereitung teile die Nachricht in Teilblöcke mit der festen Größe nBits und wähle die vier Werte a, b, c und m so das gilt:

- c und m dürfen keinen gemeinsamen Teiler haben (relativ prim)
- m muß größer sein als  2 ^ nBits
- a * b * c mod m muß 1 ergeben

Die Werte a und b bilden den privaten Schlüssel, c und m den öffentlichen Schlüssel. Je größer diese Werte gewählt werden, desto stärker die Sicherheit. Danach berechne die Zahlenfolge K wie folgt:

Für i = 0, 1, 2, ... bis nBits - 1 
​        K[i] = (2 ^ i) * a mod m 

Zur Verschlüsselung setze den Chiffretext ("cipher") auf 0.

Für i = 0, 1, 2... bis nBits - 1 
​        Wenn in der Nachricht das Bit 2 ^ i gesetzt ist, dann: cipher = cipher + K[i]

cipher = cipher * b mod m 

Zur Entschlüsselung berechne:

Klartext = cipher * c mod m

## Beispiel

Wir teilen die Nachricht in Teilblöcke von 6 Bit und wählen a = 7, b = 2, c = 9 und m = 125. 

Die Zahlenfolge K wird daraus wie folgt berechnet:

```
1 * 7 mod 1301 = 7 
2 * 7 mod 1301 = 14 
4 * 7 mod 1301 = 28 
8 * 7 mod 1301 = 56 
16 * 7 mod 1301 = 112 
32 * 7 mod 1301 = 99
```

Die Zahlenfolge K besteht also aus: { 7, 14, 28, 56, 112, 99 }.

Lautet die Nachricht 010110, so verläuft die Verschlüsselung wie folgt:

​        010110 entspricht 14 + 28 + 112 = 154 
​        Der Chiffretext lautet dann: 154 * 2 mod 125 = 58

Die Entschlüsselung geschieht ganz einfach über:

​    58 * 9 mod 125 = 22, das entspricht 10110

Der wiederhergestellte Klartext lautet damit: 010110

## Herleitung

SHORTY leitet sich aus dem Rucksackalgorithmus (knapsack algorithm) von Merkle-Hellman [1] her, der wie folgt definiert ist:

1. Wähle eine Rucksackfolge mit der Superincreasing-Eigenschaft. 
2. Wähle einen Multiplikator n und ein Modul m mit folgenden Eigenschaften:

​           m > Summe aller Zahlen in der Rucksackfolgen, n und m haben keine gemeinsamen Teiler 

3. Berechne die normale Rucksackfolge aus: superKnapsack[i] * n mod m
4. Addiere für jedes gesetzte Bit in der Nachricht das entsprechende Element in der normalen 

​          Rucksackfolge zum Chiffretext.

5. Bestimme nn so daß gilt: n * nn = 1 (mod m) 
6. Berechne: chiffretext * nn mod m
7. Gewinne den Klartext über die Rucksackfolge mit der Superincreasing-Eigenschaft.

Für SHORTY nehmen wir in Schritt (1) die Zweierpotenz-Rucksackfolge (1, 2, 4, 8, 16, 32, ...), welche die Superincreasing-Eigenschaft erfüllt, damit kann dann Schritt (7) entfallen.

Schritt (6) wird in zwei modulare Multiplikationen aufgespaltet, da gilt: 
​    ab * x mod m  entspricht:  (a * x mod m) * b mod m

nn wird dabei in die 2 Multiplikatoren b und c aufgespalten, n entspricht a in SHORTY.

## Beispiel-Schlüssel

Für 80 Bit:

```
private a = 1b538a (24 bit)
private b = abd93  (20 bit)

public c = 66bf4b8ecceafb123c7961ba37c655f8a61eae2b7cb1ceb6cf402ad7eb788a6d6e14b311b6ac3bd9f700ae32a1e41ff8ccd48792ea2448f04cfd7346ed733e0c1b8a5972d5af0acf0dd34c1b741adae718599d69e550431a14235b5f403f917324a5ec40fe372f9d7e3d1ce27a8ba9a00cd97c71712e84344d2aa7d1d2b824a5c652c36567 (1064 bit)
public mod = dcffdb7769a382d02f69 (80 bit)
```

Für 96 Bit:

```
private a = 1a4824 (24 bit)
private b = 219a9c (24 bit)

public c = 3441ae7ce03d48bc2139b0d95838d41e9e86ace4085396d5c254262385aae2fcda47941ec8668ad53b81005a9e7e380b23e3ff4352d43d5507aeace418b27654719506536151e17c347065c5d35e62ee4dc31b565aaba000c3a7c40579dfea1d54ad3ff994ff1d3fdd0e34270d26c4e311f98307fe138580164ce0c9c65a7a13b7eb192442889d (1080 bit)
public mod = c3c694bcb70d5dcfb3d5f239 (96 bit)
```

Für 100 Bit:

```
private a = 1fdb48 (24 bit)
private b = 2457c6  (24 bit)

public c = 181e0b1397d13baa66e861d0feae1734b418db2e1aa5efc74a3c1a2fe920dacc26adca8b1dd579bb2bc51ef204b778e8dd04d0f3f02ed8edb254582f8a99ecb26aab5a58c433a3332ca82f5c44f64a5265fb611d1fc0a3b200fdc21f42836ece72fb20060d03b30f9416cbc82f8fe9f4ea0fc15de1e8084d518a6b (984 bit)
public mod = 8ee82a56a73549610d9dbf8db (100 bit)
```

## Patente und Lizenzen

Der Algorithmus von Merkle-Hellman ist zwar in vielen Ländern patentiert, jedoch ist der Patentschutz in den meisten Ländern bereits abgelaufen [2]:

Deutschland: Nummer 2843583 erteilt am 10. Mai 1979 
Deutschland: Nummer 2843583 erteilt am 3. Juni 1982 
Deutschland: Nummer 2857905 erteilt am 15. Juli 1982 
Kanada: Nummer 1128159 erteilt am 20. Juli 1982 
USA: Abgelaufen am 19. August 1997

## Quellenangaben

1. Bruce Schneier "Angewandte Kryptographie", Addison-Wesley Publishing Company, ISBN  3-89319-854-7, Seite 526 
2. Bruce Schneier "Angewandte Kryptographie", Addison-Wesley Publishing Company, ISBN 3-89319-854-7, Seite 531 
