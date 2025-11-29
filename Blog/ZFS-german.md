![Image](/img/BannerZFS.jpg)

(Photo: pixabay.com)

ZFS - the better file system
=============================

**ZFS is the short form for the Zettabyte File System. It is a modern computer file system that was developed to overcome many of the major problems in previous developments.**

... ![Image](/img/MF.png) *By Markus Fleschutz* 📅 *September 9, 2019*

What makes ZFS better?
----------------

1. **Checksums:** When data is written, a checksum is calculated and stored together with the data. When that data is later read back in, that checksum is calculated again. If the checksums do not match, a data error has been detected. *ZFS* will try to correct this error automatically ("self healing") if there is enough data redundancy.
2. **Copy-on-Write (COW):** *ZFS* never overwrites original data with new data, but reallocates changed data. In this way, data in *ZFS* is consistent at all times - a power failure can no longer damage the file system. 
3. **Future-proof for huge amounts of data:** *ZFS* is a 128-bit file system, unlike ordinary 64-bit file systems. Thus, the limits are an unimaginable 256 ZiB (zebibyte) for the maximum file system size, 16 EiB (exbibyte) for the maximum file size, and 281 trillion (2 to the 48th power) for the total number of all files.
4. **Storage Pools:** With the optional Storage Pools, one or more hard disks can be combined to form a logical unit. This makes it possible to add hard disks to the storage pool and file systems as needed, and to create storage space on running systems when it is needed. 
5. **Disk redundancy:** With *ZFS*, RAID functionality is already built into the software, eliminating the need for expensive and often unsafe hardware RAID controllers.
6. **Snapshots:** In *ZFS* snapshots can be created unlimited without prior storage reservation. Due to the copy-on-write procedure, the older data is still available. The snapshots can be archived as well as mounted. The creation and retention of snapshots is thus possible without performance losses. Thus, snapshots can easily be taken before each program installation, but also regularly on a daily, hourly and quarter-hourly basis.
7. **Compression:** To save disk space, you can compress datasets with the LZ4, LZJB, GZIP or ZLE method (switched off by default). With today's processors it is almost always worth it. Switching on is possible with: `zfs set compression=lz4 mypool/mydataset`.
8. **Native encryption:** So that only authorized persons have access to the data, you can switch on the encryption with the AES-256-CCM-algorithm. For example with: `zfs create -o encryption=aes-256-ccm -o keysource=passphrase,prompt mypool/mydataset`.
9. **Deduplication:** This means that blocks with identical contents are physically stored only once, which saves disk space. A typical use case is the creation of virtual disks for virtual machines, each of which contains an installation of a virtualized operating system. Another would be to remove redundant information from like backups. However, optional deduplication requires a lot of RAM (rule of thumb: 1 TB of data requires 1 GB of RAM).

## Conclusion

- ZFS protects its data, other file systems only manage it!
- Unfortunately, despite all these advantages, *ZFS* is currently only supported by the Solaris, FreeBSD and Linux operating systems. One of the reasons is the strict CDDL license Oracle has chosen for ZFS.

Links
-----

* [OpenZFS (Open Source Port of ZFS for FreeBSD, Linux, OS X and Windows)](https://open-zfs.org)
* [Wikipedia: ZFS](https://en.wikipedia.org/wiki/ZFS)
* [ZFS on Linux](https://zfsonlinux.org) (English)
* [ZFS Cheatsheet](https://blog.programster.org/zfs-cheatsheet) (English)
