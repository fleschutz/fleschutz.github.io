![Bild](/img/BannerBoat.jpg)

(Bild: pixabay.com)

Korrekter C/C++-Formatstring für printf()/scanf()
=====================================================

**Die Verwendung des korrekten Formatstrings für printf(), scanf() usw. ist nicht trivial. Außerdem warnen nicht alle Compiler, wenn ein falscher Spezifizierer verwendet wird, was zu einem Absturz führen kann.**

... ![Bild](/img/MF.png) *Von Markus Fleschutz* 🕓 *6. Juni 2019*

```
DATENTYP → SPEZIFIZIERER ZU VERWENDEN
================================
int → %d für dezimal

unsigned int → %u für dezimal, %x für hex und %o für oktal

long → %ld für dezimal

unsigned long → %lu für dezimal, %lx für hex und %lo für oktal

size_t → %zu für dezimal bzw. %zx für hex

float → %f

double → %lf

char * → %s für einen C-String

void * → %p, um den Zeiger selbst auszugeben
```




