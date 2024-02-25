---
aliases: Point-to-Point Protocol
---

Point-to-Point Protocol (PPP) is a data link layer (*layer 2*) communication protocol between two routers directly without any host or any other networking in between. It can provide loop detection, authentication, transmission encryption, and data compression.

PPP is a layered protocol that has three components:

1. An encapsulation component that is used to transmit datagrams over the specified physical layer.
2. A Link Control Protocol (LCP) to establish, configure, and test the link as well as negotiate settings, options and the use of features.
3. One or more Network Control Protocols (NCP) used to negotiate optional configuration parameters and facilities for the network layer. There is one NCP for each higher-layer protocol supported by PPP.

### Sicherheitsdienste
- Authentifizierung optional 
- Im Rahmen der LCP-Aushandlung der Konfiguration kann jeder Partner eine Authentifizierung fordern 
- Definierte Authentifizierungsprotokolle: 
	- Password Authentication Protocol ([[PAP]]) 
	- Challenge-Handshake Authentication Protocol ([[CHAP]]) 
	- Extensible Authentication Protocol ([[EAP]])

##### Sicherheitsrisiko [[PAP]]-Fallback
Clients unterstützen immer noch Server, die nur [[PAP]] anbieten 
- Für Client-Hersteller einfach zu implementieren 
- Abwärtskompatibilität vom Markt gewünscht 
- Die meisten Anwender kennen den Unterschied zwischen [[PAP]], [[CHAP]], etc. sowieso nicht: Hauptsache, es funktioniert! 

**Man-in-the-middle-Angriff** 
- Client kommuniziert nicht direkt mit Server, sondern über Angreifer 
- Angreifer gibt sich als „nur [[PAP]]“-Server aus 
- Angreifer erhält Klartext-Passwort vom Client 
- Somit kann der Angreifer u.a. als [[CHAP]]-fähiger Client gegenüber dem richtigen Server auftreten