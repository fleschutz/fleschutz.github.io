![Bild](/img/BannerDNS.jpg)

(Foto: pixabay.com)

# Tipp: Den DNS-Server wechseln

**Es geschieht unbemerkt sobald wir Computer, Handy & Co. benutzen: fast jeder Aktivität im Netz geht zuerst eine Anfrage nach der IP-Adresse an die DNS-Server voraus (den "Telefonbüchern des Internet"). In der Voreinstellung beantworten dies die DNS-Server des Internetproviders. Jedes Gerät lässt sich aber so einstellen, das ein oder mehrere andere DNS-Server genutzt werden.** 

... ![Bild](/img/MF.png) *Von Markus Fleschutz*  🕓 *12. Februar 2023*

Warum überhaupt wechseln?
----------------------------------------

Es gibt viele gute Gründe den DNS-Server zu wechseln:

1. Er läuft nicht zuverlässig oder antwortet zu langsam.
2. Er ist zensiert, "verbotene" Domains werden nicht aufgelöst.
3. Er  ist nicht vertrauenswürdig. Die angefragten Domains werden gespeichert, daraus Nutzerverhalten extrahiert und weiterverkauft.
4. Er unterstützt keine Features wie Malware-Blocklist, Adult Content Blocklist, verschlüsselte Übertragung oder Schutz vor DNS-Angriffen

Alternative DNS-Server
----------------------------------

Als Alternative zum DNS-Servers des Internetanbieters bieten sich folgende öffentliche DNS-Server an:

- **Cloudflare:** IPv4: 1.1.1.1 und 1.0.0.1 sowie IPv6: 2606:4700:4700::1111 und  2606:4700:4700::1001
- **Cloudflare mit Malware-Blocklist:** IPv4: 1.1.1.2 und 1.0.0.2 sowie IPv6: 2606:4700:4700::1112 und 2606:4700:4700::1002
- **Cloudflare mit Malware-Blocklist und Adult Content Blocklist:** IPv4: 1.1.1.3 und 1.0.0.3 sowie IPv6: 2606:4700:4700::1113 und 2606:4700:4700::1003
- **DNS0.eu**: 193.110.81.0 und 185.253.5.0 (IPv4) sowie 2a0f:fc80:: und 2a0f:fc81:: (IPv6)
- **Level 3 Communication** (Verizon): IPv4: 4.2.2.1 bis 4.2.2.6
- **Google:** IPv4: 8.8.8.8 und 8.8.4.4 sowie IPv6: 2001:4860:4860::8888 und 2001:4860:4860::8844
- **Quad9 mit Malware-Blocklist und DNSSEC-Validation:** IPv4: 9.9.9.9 sowie IPv6: 2620:fe::fe
- **Quad9 ohne Malware-Blocklist, ohne DNSSEC, send EDNS Client-Subnet:** IPv4: 9.9.9.10 sowie IPv6: 2620:fe::10)
- **Quad9 mit Malware-Blocklist, send EDNS Client-Subnet und DNSSEC-Validation:** IPv4: 9.9.9.11
- **Quad9 mit Malware-Blocklist, NXDOMAIN only und DNSSEC-Validation:** IPv4 9.9.9.12

Weblinks
-----

* [Cloudflare DNS](https://www.cloudflare.com/DNS)
* [Google Public DNS](https://developers.google.com/speed/public-dns/)
* [Quad9](https://www.quad9.net/)

