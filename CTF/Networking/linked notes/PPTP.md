---
aliases: Point to Point Tunneling Protocol
---
The Point-to-Point Tunneling Protocol (**PPTP**) is an **obsolete** method for implementing virtual private networks. PPTP has many well known security issues.

PPTP uses a [[TCP]] control channel and a Generic Routing Encapsulation tunnel to encapsulate [[PPP]] packets. Many modern [[VPN]]s use various forms of [[UDP]] for this same functionality.

The PPTP specification does not describe encryption or authentication features and relies on the Point-to-Point Protocol being tunneled to implement any and all security functionalities. 

### Sicherheit
Protokoll komplizierter als nötig 

Nutzen der „piggybacked“ Peer Authenticator Challenge PC fragwürdig 

**Fazit** 
- Auch MS-CHAP v2 hat keinen integrierten Schutz vor Angriffen 
- Starke Abhängigkeit von der Wahl eines „guten“ Benutzerpassworts 
- Bessere Verfahren (z.B. Encrypted Key Exchange und Varianten) waren bereits verfügbar, wurden von Microsoft aber nicht genutzt 

*Version Rollback Attack möglich*: Mallet „überzeugt“ Client und Server, MS-CHAP v1 zu verwenden