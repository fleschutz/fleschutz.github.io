![Image](/img/BannerDNS.jpg)

(Photo: pixabay.com)

# Tip: Change the DNS server

**It happens unnoticed as soon as we use computers, cell phones & Co: almost every activity on the net is first preceded by a request for the IP address to the DNS servers (the "phone books of the Internet"). By default, the DNS servers of the Internet provider answer this. However, each device can be configured to use one or more other DNS servers.**

... ![Image](/img/MF.png) *By Markus Fleschutz* 🕓 *April 6, 2020*

Why change at all?
----------------------------------------

There are some good reasons to change the DNS server:

1. it is not running reliably or responds too slowly.
2. it is censored, "forbidden" domains are not resolved.
3. it is not trustworthy. The requested domains are stored, user behavior is extracted from them and resold.
4. it does not support features such as malware blocklist, adult content blocklist, encrypted transmission or protection against DNS attacks.

Selected public DNS servers
----------------------------------

- **Cloudflare:** IPv4: 1.1.1.1 and 1.0.0.1, and IPv6: 2606:4700:4700::1111 and 2606:4700:4700::1001.
- **Cloudflare with malware blocklist:** IPv4: 1.1.1.2 and 1.0.0.2 and IPv6: 2606:4700:4700::1112 and 2606:4700:4700::1002
- **Cloudflare with Malware Blocklist and Adult Content Blocklist:** IPv4: 1.1.1.3 and 1.0.0.3 as well as IPv6: 2606:4700:4700::1113 and 2606:4700:4700::1003
- **Level 3 Communication** (Verizon): IPv4: 4.2.2.1 to 4.2.2.6
- **Google:** IPv4: 8.8.8.8 and 8.8.4.4 and IPv6: 2001:4860:4860::8888 and 2001:4860:4860::8844
- Quad9 with malware blocklist and DNSSEC validation: IPv4: 9.9.9.9 and IPv6: 2620:fe::fe
- Quad9 without malware blocklist, without DNSSEC, send EDNS client subnet:** IPv4: 9.9.9.10 as well as IPv6: 2620:fe::10)
- Quad9 with malware blocklist, send EDNS client subnet and DNSSEC validation:** IPv4: 9.9.9.11
- Quad9 with malware blocklist, NXDOMAIN only and DNSSEC validation:** IPv4 9.9.9.12

Links
-----

* [Cloudflare DNS](https://www.cloudflare.com/DNS)
* [Google Public DNS](https://developers.google.com/speed/public-dns/)
* [Quad9](https://www.quad9.net/)

