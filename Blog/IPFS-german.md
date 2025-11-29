![Image](/img/BannerIPFS.jpg)

(Photo: pixabay.com)

# Introduction to IPFS

***IPFS* stands for "InterPlanetary File System", but there is much more behind it than "just" a file system. IPFS uses many clever tricks and could become our network of the future.**. 

... ![Image](/img/MF.png) *By Markus Fleschutz* 🕓 *May 26, 2018*

## Content-based Addressing

The Internet uses so far mostly **Location-based Addressing:** with it media (e.g., a video) are found exclusively by their storage location. To do this, the media are accessed via the server IP address and file path after URL name resolution (such as "http://youtube.de"). However, this only works as long as (1.) the named server exists, (2.) a connection to it can be established, (3.) it provides the media at the correct location, and (4.) the connection persists (otherwise you get the well-known 404 error, among others).

With the new **Content-based Addressing**, on the other hand, media are found via their checksum, similar to the ISBN number for books. This offers several advantages:

👍 If at least one server worldwide holds the content, then it will also be found.

If several servers offer the content, the faster one can be selected and also loaded in parallel. If the connection is lost, it is possible to switch over at any time without interruption.

If parts of the Internet fail, the content can also be delivered via detours.

👍 The content is guaranteed to be unchanged, because any change to the content also inevitably changes the checksum.

👍 Caching servers can keep popular content close to the user and thus quickly in stock. This also works across the boundaries of our planet.

👍 Backup servers can save valuable content for eternity. With this, there will then also be "eternal" links.

## Packages

Larger content is automatically split into 256 KB packages by *IPFS*. This offers several advantages:

👍 Often different media files contain identical packages. With IPFS, these also occupy only one storage space.

👍 Identical packets can also be loaded from another server. This ensures a more even utilization of all servers.

👍 During the download, these packets are loaded individually and in parallel and only assembled at the end. Thus, a 2 MB image could have been loaded from 10 different servers.

## Distributed

Many of the Internet services we use today are centralized (**centralized**). If the central element fails (e.g. due to attacks, configuration errors, hardware failures, etc.), then the entire service automatically fails as well. 

As a workaround, many operators try to compensate for this with a decentralized approach (**decentralized**), but even here failures affect many users.

*IPFS*, on the other hand, is 100% **distributed**, with no single point of failure. 

![Image](/img/Distributed.jpg)

## Conclusion

Through *IPFS*, the Internet can become as robust as our water supply:

- Content is available **securely**, **fast**, and **unmodified** at all times.
- There is **no single point of failure**, so attacks or failures have a maximum regional impact.
- The content is also available during long signal runtimes (e.g. to other planets) or in case of connection failures (therefore "Interplanetary").

## Links

- [ipfs.io](https://ipfs.io) - the homepage of IPFS (English)
- [IPFS Desktop](https://docs.ipfs.io/install/ipfs-desktop/) - installation guide of IPFS Desktop (English)
- [blog.ipfs.io](https://blog.ipfs.io) - blog and news of IPFS (English)
- [discuss.ipfs.io](https://discuss.ipfs.io/) - discussion forum about IPFS (English)
- [awesome.ipfs.io](https://awesome.ipfs.io) - Apps, services and datasets based on IPFS (English)
- [IPFS Public Gateways](https://ipfs.github.io/public-gateway-checker/) - list of web gateways to IPFS (English)
- [Wikipedia: IPFS](https://en.wikipedia.org/wiki/InterPlanetary_File_System) (English)
