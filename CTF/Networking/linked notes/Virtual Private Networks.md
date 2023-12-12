---
aliases: VPN
---

A `Virtual Private Network` (`VPN`) is a technology that allows a secure and encrypted connection between a private network and a remote device. This allows the remote machine to access the private network directly, providing secure and confidential access to the network's resources and services. For example, an administrator from another location has to manage the internal servers so that the employees can continue to use the internal services. Many companies limit servers' access, so clients can only reach those servers from the local network. This is where VPN comes into play, where the administrator connects to the VPN server via the internet, authenticates himself, and thus creates an encrypted tunnel so that others cannot read the data transfer. In addition, the administrator's computer is also assigned a local (internal) IP address through which he can access and manage the internal servers. Administrators commonly use VPNs to provide secure and cost-effective remote access to a company's network. VPN typically uses the ports `TCP/1723` for [Point-to-Point Tunneling Protocol](https://www.lifewire.com/pptp-point-to-point-tunneling-protocol-818182) `PPTP` VPN connections and `UDP/500` for [IKEv1](https://www.cisco.com/c/en/us/support/docs/security-vpn/ipsec-negotiation-ike-protocols/217432-understand-ipsec-ikev1-protocol.html) and [IKEv2](https://nordvpn.com/blog/ikev2ipsec/) VPN connections.

This allows employees to access the network and its resources, such as email and file servers, from remote locations, such as their homes or while traveling. There are several reasons why administrators use VPNs. VPNs encrypt the connection between the remote device and the private network, making it much more difficult for attackers to intercept and steal sensitive information. With this, the entire communication is more secure.

Another reason is that VPNs allow employees to access the private network and its resources remotely from anywhere, as long as they have an internet connection. This is particularly useful for employees who need to work remotely, such as those traveling or working from home. Additionally, VPNs can be more cost-effective than other remote access solutions, such as leased lines or dedicated connections, because they use the public internet to connect remote users to the private network.

Moreover, we can use VPNs to connect multiple remote locations, such as branch offices, into a single private network, making it easier to manage and access network resources. However, several components and requirements are necessary for a VPN to work:

|**Requirement**|**Description**|
|---|---|
|`VPN Client`|This is installed on the remote device and is used to establish and maintain a VPN connection with the VPN server. For example, this could be an OpenVPN client.|
|`VPN Server`|This is a computer or network device responsible for accepting VPN connections from VPN clients and routing traffic between the VPN clients and the private network.|
|`Encryption`|VPN connections are encrypted using a variety of encryption algorithms and protocols, such as AES and IPsec, to secure the connection and protect the transmitted data.|
|`Authentication`|The VPN server and client must authenticate each other using a shared secret, certificate, or another authentication method to establish a secure connection.|

The VPN client and server use these ports to establish and maintain the VPN connection. At the TCP/IP layer, a VPN connection typically uses the [Encapsulating Security Payload](https://www.ibm.com/docs/en/i/7.4?topic=protocols-encapsulating-security-payload) (`ESP`) protocol to encrypt and authenticate the VPN traffic. This allows the VPN client and server to exchange data over the public internet securely.

---

![[IPsec]]

## PPTP

[Point-to-Point Tunneling Protocol](https://www.vpnranks.com/blog/pptp-vs-l2tp/) (`PPTP`) is also a network protocol that allows the creation of VPNs and works by establishing a secure tunnel between the VPN client and server and then encapsulating the data being transmitted within this tunnel.

It is an extension of the PPTP and is implemented in many operating systems. Due to known vulnerabilities, PPTP is no longer considered secure today. PPTP can be used to tunnel protocols such as IP, IPX, or NetBEUI via IP. Due to known vulnerabilities, the PPTP is no longer considered secure and has been largely replaced by other VPN protocols such as `L2TP/IPsec`, `IPsec/IKEv2`, or `OpenVPN`. Since 2012, however, PPTP is no longer considered secure because the authentication method MSCHAPv2 uses the dusty DES and can therefore be easily cracked with special hardware.