![Image](/img/BannerBoat.jpg)

(image: pixabay.com)

Correct C/C++ format string for printf()/scanf()
=====================================================

**Using the correct format string for printf(), scanf(), etc. is not trivial. Furthermore, not all compiler warn when a wrong specifier is being used, which may lead to a crash.**

... ![Bild](/img/MF.png) *By Markus Fleschutz* 🕑 *June 06, 2019*

```
DATATYPE      → SPECIFIER TO USE
================================
int           → %d for decimal

unsigned int  → %u for decimal, %x for hex and %o for octal

long          → %ld for decimal

unsigned long → %lu for decimal, %lx for hex and %lo for octal

size_t        → %zu for decimal or %zx for hex

float         → %f

double        → %lf

char *        → %s for a C string

void *        → %p to print the pointer itself
```




