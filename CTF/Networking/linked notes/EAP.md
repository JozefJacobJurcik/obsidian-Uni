---
aliases: Extensible Authentication Protocol
---

RFC3748, RFC5247 und RFC7057 
- Authentisierungs-Framework, bietet gemeinsame Funktionen und Aushandlungsmechanismen für konkretes Verfahren (als Methode bezeichnet)
- Rund 40 Methoden werden unterstützt: 
	- EAP-MD5; äquivalent zu [[CHAP]] 
	- EAP-[[OTP]] (One Time Password) 
	- EAP-GTC (Generic Token Card) 
	- EAP-TLS (Transport Layer Security) 
	- EAP-SIM (Global System for Mobile Communications (GSM) Subscriber Identity Modules (SIM) 

Herstellerspezifische Methoden: 
- LEAP (Cisco) Lightweight Extensible Authentication Protocol 
- PEAP (Cisco, Microsoft, RSA) Protected Extensible Authentication Prot.
- ...
### Grundlagen
**EAP** kann Sequenz von Verfahren verwenden 
Verfahren muss aber vollständig abgeschlossen werden, bevor neues beginnt 
Request - Response Schema mit Success / Failure Antwort 

**Beispiel** EAP-GTC (Generic Token Card, RFC3748) 
- Nutzbar für verschiedenste Autentisierungs-Token-Implementierungen 
- Request beinhaltet Nachricht, die dem Nutzer angezeigt wird 
- Nutzer gibt Token-Information ein 
- Server prüft und antwortet