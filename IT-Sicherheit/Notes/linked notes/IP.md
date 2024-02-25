---
aliases: Internet Protocol
---

The Internet Protocol (IP) is the network layer communications protocol in the Internet protocol suite for relaying datagrams across network boundaries. Its routing function enables internetworking, and essentially establishes the Internet. 

### Gefahren und Schwächen
[[Vertraulichkeit]]
- Mithören relativ einfach möglich 
- Man-in-the-middle-Angriffe 
- Verkehrsfluss-Analyse 
[[Integrität]] 
- Veränderung der Daten 
- Session Hijacking 
- Replay-Angriffe 
[[Authentisierung]]
- IP Spoofing 

**Lösung**
[[IPSec]] (Sicherheitserweiterungen für IP) 
- Fester Bestandteil von IPv6 
- Als Erweiterungs-Header auch für IPv4 einsetzbar 
- Motivation: Erspart den Aufwand für entsprechende Gegenmaßnahmen in jeder einzelnen Anwendung (d.h. auf höheren Schichten)