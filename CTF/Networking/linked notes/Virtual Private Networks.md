---
aliases: VPN
---
A virtual private network (VPN) is a mechanism for creating a *secure connection* between a *computing device and a computer network*, or between *two networks*, using an insecure communication medium such as the public Internet.

A VPN can extend access to a private network (one that disallows or restricts public access) to users who do not have direct access to it, such as an *office network allowing secure access from off-site over the Internet*.

The benefits of a VPN include security, reduced costs for dedicated communication lines, and greater flexibility for remote workers.

A VPN is created by establishing a virtual point-to-point connection through the use of tunneling protocols over existing networks. A VPN available from the public Internet can provide some of the benefits of a private wide area network (WAN).

### ISO
![[Pasted image 20240224173350.png]]

#### Virtual Network auf Schicht 1
Virtual Private Wire Service (VPWS) 
- Provider bietet Punkt zu Punkt Verbindung 
Virtual Private Line Service (VPLS) 
- Provider bietet Punkt zu Multipunkt Verbindungen 

**Beispiel**
Optical Private Link oder Optical Private Network (OPN) 
- Provider betreibt Glasfaserinfrastruktur 
- Kunde erhält eine Wellenlänge (Farbe) in dieser Infrastruktur
- Kunde kann diese nutzen wie einen dedizierten Schicht 1 Link 
- Kunde muss sich um Routing, Switching, etc. selbst kümmern 
- Über dieselben Glasfasern werden auch andere Kunden bedient

![[Pasted image 20240224173745.png]]

#### Virtual Network auf Schicht 2/3/4
##### Schicht 2: 
Virtual LAN (VLAN) 
- Mehrere LAN Broadcast Domains über den selben physischen Link 
- Standard: VLAN Tagging (IEEE 802.1Q) 
Virtual Private LAN Services (Achtung: Abkürzung auch VPLS) 
- Verbindet physisch getrennte (V)LANs miteinander 
Point-to-Point Verbindungen 
Layer2 Tunneling Protocol
usw..

###### Aufgaben der Schicht 2
Fehlerfreie Übertragung von Frames (Rahmen) 
- Aufteilung von Bitströmen in Frames 
- Fehlerkontrolle über Prüfsummen (z.B. Cyclic Redundancy Check, CRC) 

Flusskontrolle (Verhindert, dass der Empfänger mit Frames überflutet wird und diese verwerfen muss) 

Medienzugriffsverfahren für gemeinsam genutztes Übertragungsmedium
- CSMA/CD bei Ethernet (IEEE 802.3) 
- CSMA/CA bei WLAN (IEEE 802.11)
- ....

##### Schicht 3 und höher: 
- [[IPSec]] 
- SSL / TLS 
- OpenVPN, eduVPN 
- ...

### Virtual LAN ([[VLAN]])

### [[IPsec]]

### [[PPP]]

### [[PPTP]]
