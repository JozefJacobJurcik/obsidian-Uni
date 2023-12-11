---

---

Each network is structured differently and can be set up individually. For this reason, so-called `types` and `topologies` have been developed that can be used to categorize these networks. When reading about all the types of networks, it can be a bit of information overload as some network types include the geographical range. We rarely hear some of the terminologies in practice, so this section will be broken up into `Common Terms` and `Book Terms`. Book terms are good to know, as there has been a single documented case of an email server failing to deliver emails longer than 500 miles but don't be expected to be able to recite them on demand unless you are studying for a networking exam.

#### Common Terminology

|**Network Type**|**Definition**|
|---|---|
|Wide Area Network (WAN)|Internet|
|Local Area Network (LAN)|Internal Networks (Ex: Home or Office)|
|Wireless Local Area Network (WLAN)|Internal Networks accessible over Wi-Fi|
|Virtual Private Network (VPN)|Connects multiple network sites to one `LAN`|

---

![[WAN]]

![[LAN and WLAN]]

---

![[VPN]]

---

## Book Terms

|Network Type|Definition|
|---|---|
|Global Area Network (GAN)|Global network (the Internet)|
|Metropolitan Area Network (MAN)|Regional network (multiple LANs)|
|Wireless Personal Area Network (WPAN)|Personal network (Bluetooth)|

#### GAN

A worldwide network such as the `Internet` is known as a `Global Area Network` (`GAN`). However, the Internet is not the only computer network of this kind. Internationally active companies also maintain isolated networks that span several `WAN`s and connect company computers worldwide. `GAN`s use the glass fibers infrastructure of wide-area networks and interconnect them by international undersea cables or satellite transmission.

#### MAN

`Metropolitan Area Network` (`MAN`) is a broadband telecommunications network that connects several `LAN`s in geographical proximity. As a rule, these are individual branches of a company connected to a `MAN` via leased lines. High-performance routers and high-performance connections based on glass fibers are used, which enable a significantly higher data throughput than the Internet. The transmission speed between two remote nodes is comparable to communication within a `LAN`.

Internationally operating network operators provide the infrastructure for `MAN`s. Cities wired as `Metropolitan Area Networks` can be integrated supra-regionally in `Wide Area Networks` (`WAN`) and internationally in `Global Area Networks` (`GAN`).

#### PAN / WPAN

Modern end devices such as smartphones, tablets, laptops, or desktop computers can be connected ad hoc to form a network to enable data exchange. This can be done by cable in the form of a `Personal Area Network` (`PAN`).

The wireless variant `Wireless Personal Area Network` (`WPAN`) is based on Bluetooth or Wireless USB technologies. A `wireless personal area network` that is established via Bluetooth is called `Piconet`. `PAN`s and `WPAN`s usually extend only a few meters and are therefore not suitable for connecting devices in separate rooms or even buildings.

In the context of the `Internet of Things` (`IoT`), `WPAN`s are used to communicate control and monitor applications with low data rates. Protocols such as Insteon, Z-Wave, and ZigBee were explicitly designed for smart homes and home automation.