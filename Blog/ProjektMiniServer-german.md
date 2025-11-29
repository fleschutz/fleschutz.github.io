![Image](/img/BannerServer.jpg)

(Photo: pixabay.com)

Project "Mini-Server": Raspberry Pi 4 & SSD
=============================

**The goal of this project is to set up an inexpensive yet powerful mini-server. For this purpose a Raspberry Pi 4 is combined with a fast SSD. For more performance and higher reliability, more of these mini servers will be set up.**

... ![Image](/img/MF.png) *By Markus Fleschutz* 🕓 *March 11, 2021*

Hardware used
----------------

![Image](/img/RasPi4.jpg)

* **Board:** Raspberry Pi 4 Model B with Cortex A72 CPU (4 cores á 1.5 GHz) and 4 GB LPDDR4-3200 SDRAM.
** **Case:** MANOUII aluminum case without fan (€18,99)
* **SD-Card:** 32 GB, Class 10 (only used for booting the operating system)
* **SSD:** Samsung EVO SATA 512 GB (needs no additional power cable and no fan)
**USB 3.0 to SATA adapter:** to connect the board to the SSD (€8,99)
**USB-C power supply:** 5V, 3A, 15W

Software used
--------

* **Operating system:** Ubuntu 20.04 LTS Server Edition for ARM64 
* **Packages:** *powershell, smartmontools, samba* (general), *gcc, clang, clang-tidy, distcc, ninja-build* (for software development)
* **Snaps:** *bashtop, htop, hw-probe* (general), *ant, ccache, cmake, cppcheck, go, groovy, python38* (for software development), *adguard-home* (as DNS server with ad blocker), *ipfs* (as IPFS server), *plexmediaserver* (as media server) and *minidlna-escoand* (as DLNA server)

Measurements & Data
------------------------

* **Current consumption:** 7.5 watts (including SSD) in idle mode
* **Dimensions:** 12 x 7 x 5 cm total (L x W x H), corresponds to 420 cc
* **Purchase price:** circa 150 € total (as of 2019).
* **Stability**: runs stable since June 1, 2020, even under full load.
* **Loudness:** 0 dB (fanless)
* **CPU temperature:** from 41 °C (idle) to 62 °C (full load), measured at room temperature 20 °C.
* **Linpack Benchmark:** 13.5 GFLOPS, 925 MIPS single-precision, 748 MIPS double-precision, 2037 MIPS single-precision using NEON instructions
* **Gigabit Ethernet:** 117 MB/s throughput, ping min/average/max/mdev = 0.173/0.241/0.302/0.029 ms
* **USB 3.0:** 363 MB/s read throughput, 323 MB/s write throughput
* **MicroSD:** 46 MB/s read throughput, 27 MB/s write throughput
* **Efficiency:** 1.8 GFLOPS per Watt

## Conclusion

👍 Thumbs up for stability, energy consumption, total cost of ownership and efficiency.

👍 The Raspberry Pi 4 is also available in a version with 8 GB RAM - ideal for servers

👍 The Raspberry Pi 4 also supports booting via the USB interface, so no slow and failure-prone SD card is needed anymore

👌 Perfect would be *Power over Ethernet* (PoE), then also the separate power supply would be omitted

👎 Not all software packages and snap packages are available for ARM64 yet, Ubuntu should improve here

👎 For an encrypted user directory, the Raspberry Pi is (still) too weak 

Links
-----

* [raspberrypi.org](https://www.raspberrypi.org) - the Raspberry Pi homepage
* [wikipedia.org](https://de.wikipedia.org/wiki/Raspberry_Pi) - everything about the Raspberry Pi
* [ubuntu.com](https://www.ubuntu.com) - the Ubuntu homepage
* [snapcraft.io/store](https://www.snapcraft.io/store) - the Snap Store
