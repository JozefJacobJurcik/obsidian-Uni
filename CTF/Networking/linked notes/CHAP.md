---
aliases: Challange Handshake Authentication Protocol
---

RFC1334, RFC1994 und RFC2484 
- Periodische Authentisierung durch 3-Way-Handshake Protokoll 
- Basiert auf gemeinsamen Geheimnis (Passwort) $K_{AB}$ 
- $A$ (Authenticator) fordert $B$ zur Authentisierung auf: 

![[Pasted image 20240224175840.png]]
- id: 1 Byte Identifier („incrementally changing“) gegen Replay-Angriffe
- $R_A$ : Zufallszahl, $H$: Hash Verfahren, im Standard [[MD5]] 
- 3 = success; 4 = failure 

Auth-Request kann später beliebig neu geschickt werden