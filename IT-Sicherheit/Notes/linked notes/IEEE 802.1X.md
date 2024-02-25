---

---
IEEE 802.1X is an *IEEE Standard* for port-based network access control (PNAC). It is part of the IEEE 802.1 group of networking protocols. It provides an authentication mechanism to devices wishing to attach to a LAN or WLAN. 

### Overview
802.1X authentication involves three parties: a **supplicant**, an *authenticator*, and an `authentication server`. The **supplicant** is a client device (such as a laptop) that wishes to attach to the LAN/WLAN. The term 'supplicant' is also used interchangeably to refer to the software running on the client that provides credentials to the *authenticator*. The *authenticator* is a network device that provides a data link between the client and the network and can allow or block network traffic between the two, such as an Ethernet switch or wireless access point; and the `authentication server` is typically a trusted server that can receive and respond to requests for network access, and can tell the authenticator if the connection is to be allowed, and various settings that should apply to that client's connection or setting. `Authentication servers` typically run software supporting the RADIUS and [[EAP]] protocols. In some cases, the `authentication server` software may be running on the *authenticator* hardware. 

![[802.1X_wired_protocols.png]]

The *authenticator* acts like a security guard to a protected network. The **supplicant** (i.e., client device) is not allowed access through the *authenticator* to the protected side of the network until the **supplicant**'s identity has been validated and authorized. With 802.1X port-based authentication, the **supplicant** must initially provide the required credentials to the *authenticator* - these will have been specified in advance by the network administrator and could include a user name/password or a permitted digital certificate. The *authenticator* forwards these credentials to the `authentication server` to decide whether access is to be granted. If the `authentication server` determines the credentials are valid, it informs the *authenticator*, which in turn allows the **supplicant** (client device) to access resources located on the protected side of the network.



802er Standards für Local Area Networks (LAN), insbesondere für Schicht 1 und 2, z.B. 
- 802.1Q Virtual Bridged LANs ([[VLAN]]) 
- 802.3 CSMA/CD (Ethernet) 
- 802.5 Token Ring
- 802.6 Metropolitan Area Network 
- 802.11 Wireless LAN 
- 802.15 Wireless PAN (Personal Area Network) 
- 802.15.1 Bluetooth 

802.1X Port Based Network Access Control 
- Authentisierung und Autorisierung in IEEE 802 Netzen 
- Häufig genutzt in WLANs und (V)LANs 
- Port-basierte Network Access Control

