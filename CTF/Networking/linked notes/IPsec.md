---
aliases: Internet Protocol Security
---


*Internet Protocol Security* (`IPsec`) is a network security protocol that provides encryption and authentication for internet communications. It is a powerful and widely-used security protocol that provides encryption and authentication for internet communications and works by encrypting the data payload of each IP packet and adding an `authentication header` (`AH`), which is used to verify the integrity and authenticity of the packet. IPsec uses a combination of two protocols to provide encryption and authentication:

1. [Authentication Header](https://www.ibm.com/docs/en/i/7.1?topic=protocols-authentication-header) (`AH`): This protocol provides integrity and authenticity for IP packets but does not provide encryption. It adds an authentication header to each IP packet, which contains a cryptographic checksum that can be used to verify that the packet has not been tampered with.
    
2. [Encapsulating Security Payload](https://www.ibm.com/docs/en/i/7.4?topic=protocols-encapsulating-security-payload) (`ESP`): This protocol provides encryption and optional authentication for IP packets. It encrypts the data payload of each IP packet and optionally adds an authentication header, similar to AH.
    

IPsec can be used in two modes.

|**Mode**|**Description**|
|---|---|
|`Transport Mode`|In this mode, IPsec encrypts and authenticates the data payload of each IP packet but does not encrypt the IP header. This is typically used to secure end-to-end communication between two hosts.|
|`Tunnel Mode`|With this mode, IPsec encrypts and authenticates the entire IP packet, including the IP header. This is typically used to create a VPN tunnel between two networks.|
![[Pasted image 20240224234527.png]]

For example, an administrator could place a firewall in between. In order to facilitate IPsec VPN traffic from a VPN client outside a firewall to a VPN server inside, the firewall would need to allow the following protocols:

|**Protocol**|**Port**|**Description**|
|---|---|---|
|`Internet Protocol` (`IP`)|`UDP/50-51`|This is the primary protocol that provides the foundation for all internet communication. It is used to route packets of data between the VPN client and the VPN server.|
|`Internet Key Exchange` (`IKE`)|`UDP/500`|IKE is a protocol that is used to establish and maintain secure communication between the VPN client and the VPN server. It is based on the Diffie-Hellman key exchange algorithm, and it is used to negotiate and establish shared secret keys that can be used to encrypt and decrypt the VPN traffic.|
|`Encapsulating Security Payload` (`ESP`)|`UDP/4500`|ESP is also a protocol that provides encryption and authentication for IP datagrams. It is used to encrypt the VPN traffic between the VPN client and the VPN server, using the keys that were negotiated with IKE.|

These protocols are necessary for facilitating IPsec VPN traffic because they provide the security and encryption that are required for secure communication over the public internet. Without these protocols, the VPN traffic would be vulnerable to interception and tampering.

### Authentication Header (AH)

##### AH im Transport Mode 
-  Integrität durch [[MAC]] 
- Authentisierung durch gemeinsamen Schlüssel 
- Anti-Replay durch gesicherte Sequenznummer

![[Pasted image 20240224234800.png]]

![[Pasted image 20240224234929.png]]

##### AH im Tunnel Mode
![[Pasted image 20240224234820.png]]

![[Pasted image 20240224235018.png]]

### Encapsulating Security Payload (ESP) 

##### ESP Transport Mode
- Vertraulichkeit durch Verschlüsselung 
- Integrität durch [[MAC]] (optional) 
- Authentisierung durch [[HMAC]] (optional) 
- Anti-Replay durch gesicherte Sequenznummer (optional)
![[Pasted image 20240224235251.png]]

##### ESP Tunnel Mode
- Schutz vor Traffic-Analysen durch verschlüsselten IP-Header „alt“

![[Pasted image 20240224235307.png]]

![[Pasted image 20240224235356.png]]
#### Replay Protection
A monotonic strictly increasing sequence number (incremented by 1 for every packet sent) to prevent replay attacks. When replay detection is enabled, sequence numbers are never reused, because a new security association must be renegotiated before an attempt to increment the sequence number beyond its maximum value.

### IPSec Anwendungsszenarien
AH und ESP können kombiniert verwendet werden 
Auch Tunnel und Transport Mode können kombiniert werden 

###### Mögliche Einsatzszenarien 
- Kopplung von verschiedenen Unternehmensstandorten Verbindung von *Security Gateway* (SGW) zu Security Gateway
![[Pasted image 20240225015738.png]]

- Telearbeitsplätze; Remote Access („Road Warrior“)Endsystem zu SGW
![[Pasted image 20240225015801.png]]

- End-to-End
![[Pasted image 20240225015832.png]]

**Standortvernetzung**
![[Pasted image 20240225015910.png]]
*Mögliche Anforderungen* 
- Authentisierung SGW-to-SGW oder End-to-End 
- [[Integrität]]ssicherung SGW-to-SGW oder End-to-End 
- Schutz gegen Replay-Angriffe 
- Vertraulichkeit auch im (jeweils) internen Netz 
- SGW realisiert auch Firewall-Funktionen 
- Verwendung privater IP-Adressen in den Standorten 
- Verschattung interner Netzstrukturen

#### Protokollkombinationen

AH Tunnel Mode am Security Gateway 
- Integritätssicherung 
- Authentisierung SGW to SGW 
- Private Adressen im internen Netz 

ESP Tunnel Mode am Security Gateway 
- Vertraulichkeit (auch der privaten Adressen) 

AH Transport am Endsystem / ESP Transport am SGW 
- Integritätssicherung 
- Authentisierung End to End 
- Vertraulichkeit ab SGW 
- Private Adressen nicht möglich 
- Nur theoretische Kombination; praktisch schwer realisierbar (Empfänger SGW nicht adressierbar)

ESP Transport am Endsystem, AH Transport am SGW 
- Vertraulichkeit End to End 
- Authentisierung SGW to SGW 
- Private Adressen nicht möglich 
- SGW kann nicht mehr filtern (wegen Verschlüsselung) 
- Theoretisches Beispiel, in der Praxis schwer realisierbar, SGW nicht adressiert (transparentes SGW)

AH Transport am Endsystem / ESP Tunnel am SGW 
- Integritätssicherung 
- Authentisierung End to End 
- Vertraulichkeit ab SGW 
- Private Adressen möglich
### IPSec [[Security association]] (SA)

Inhalt einer SA 
- IPSec Protokoll Modus (Tunnel oder Transport) 
- Parameter (Algorithmen, Schlüssel, Zertifikat, Initialisierungsvektor,...)
- Lebensdauer der SA 
- Sequenznummernzähler mit –overflow 
- Anti-Replay-Window 
- ..... 

Identifikation einer SA per Kombination aus: 
- Security Parameter Index (SPI); 32-Bit Zahl 
- Ziel-Adresse 
- Verwendetes Protokoll (AH, ESP) 
- D.h. in jede Kommunikationsrichtung wird eine eigene SA vereinbart 
- Jeder IPSec-Teilnehmer hat eine lokale Security Policy Database (SPD) mit SAs 2