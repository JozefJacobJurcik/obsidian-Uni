---
aliases: Password Authentication Protocol
---
Spezifiziert in RFC1334
- Authentisierende Entität kennt ID und Passwort aller Clients 
- Client wird mit LCP zur Authentisierung via PAP aufgefordert 
- Client schickt ID und Passwort im **Klartext** 
- Server schickt im Erfolgsfall ACK

>[!danger] Keine Verschlüsselung, Übertragung der Passwörter im Klartext
>RFC 1334: „Any implementations which include a stronger authentication method (such as [[CHAP]], described below) MUST offer to negotiate that method prior to PAP.“

