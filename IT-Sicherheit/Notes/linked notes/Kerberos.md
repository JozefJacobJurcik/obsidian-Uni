---

---
Trusted Third Party Authentisierungsprotokoll 
- Entwickelt für [[TCP]]/IP Netze 
- Client (Person oder Software) kann sich über ein Netz bei Server(n) authentisieren 
- Kerberos-Server kennt Schlüssel aller Clients 
- Basiert auf [[Symmetrische Verschlüsselungsverfahren]] 
- Abgeleitet vom [[Needham–Schroeder protocol]] 
- Hierarchie von Authentisierungsservern möglich; jeder Server verwaltet einen bestimmten Bereich (sog. Realm) 
- Über Kooperationsmechanismen der Kerberos-Server kann Single-Sign-On realisiert werden

### Authentisierungsdaten
- Authentisierung basiert auf gemeinsamem (Sitzungs-)Schlüssel 
- Kerberos arbeitet mit Credentials; unterschieden werden 
	1. Ticket 
	2. Authenticator 

**Ticket** 
-  als „Ausweis“ für die Dienstnutzung; nur für einen Server gültig 
- wird vom Ticket Granting Server erstellt 
- keine Zugriffskontrolle über Ticket (nicht mit Capability verwechseln!)
$$T_{c,s} = s,c,addr,timestamp,lifetime,K_{c,s}$$
**Authenticator** 
- „Ausweis“ zur Authentisierung; damit Server ein Ticket verifizieren kann 
- vom Client selbst erzeugt
- Wird zusammen mit dem Ticket verschickt
$$A_{c,s}= c,addr,timestamp $$
![[Pasted image 20240224021304.png]]

1. Request für Ticket Granting Ticket 
2. Ticket Granting Ticket 
3. Request für Server Ticket 
4. Server Ticket 
5. Request für Service 
6. Authentisierung des Servers (Optional) 

Im folgenden Kerberos V5 vereinfacht, d.h. ohne Realms und Optionenlisten; exaktes Protokoll

#todo
![[itsec-k10-v14.pdf#page=64|itsec-k10-v14, page 64]]

### Bewertung
- Sichere netzweite Authentisierung auf Ebene der Dienste 
- Authentisierung basiert auf IP-Adresse 
	- IP-Spoofing u.U. möglich 
	- Challenge Response Protokoll zur Verhinderung nur optional 
- Sicherheit hängt von der Stärke der Passworte ab (aus dem Passwort wird der Kerberos-Schlüssel abgeleitet) 
- Lose gekoppelte globale Zeit erforderlich (Synchronisation) 
- Kerberos-Server und TGS müssen (auch physisch) besonders gut gesichert werden und sind potenziell „Single Point of Failure“ 
- Verlässt sich auf „vertrauenswürdige“ Software (Problem der Trojanisierung, vgl. CA-2002-29) 
- Administrationsschnittstelle und API nicht standardisiert