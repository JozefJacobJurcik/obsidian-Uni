---
aliases: Online Certificate Status Protocol
---
Online Certificate Status Protocol (OCSP) ermöglicht Clients die Abfrage des Zertifikatszustandes (zeitnah) bei einem Server (OCSP-Responder).
- OCSP-Responder i.d.R. betrieben von ausstellender CA

### Ablauf: 
1. Client schickt Hash des zu verifizierenden Zertifikats 
2. Responder prüft und antwortet mit einer der folgenden signierten Nachrichten: 
	- „Good“ (Zertifikat ist gültig) 
	- „Revoked“ (Zertifikat ist widerrufen, mit entsprechender Zeitangabe) 
	- „Unknown“ (Responder kennt das Zertifikat nicht) 
3. Replay Protection über optionale Zufallszahl (in Client-Nachricht) 
4. Client kann Positiv-Antwort fordern; Responder antwortet dann mit Hash des gültigen Zertifikates

*Kein eigenes Transportprotokoll*; verwendet [[HTTP]] oder HTTPS
### OSCP Diskussion
##### Vorteile: 
- Geschwindigkeitsvorteil gegenüber CRL (Certificate Revocation Lists)
- Möglichkeit, gesperrte von gefälschten Zertifikaten zu unterscheiden: 
	- Responder darf „Good“ nur liefern, wenn Zertifikat gültig (Standard erlaubt Good auch wenn Zertifikat nicht in Sperrliste) 
- Individuelle Abfrage für aktuell verwendetes Zertifikat 

##### Nachteile: 
 - Aktualität hängt von Implementierung ab; es gibt Responder, die CRL nutzen 
 - Zertifikatskette muss vom Client geprüft werden (lässt sich ggf. über Server-based Certification Validation Protocol (SCVP) an den Server auslagern)