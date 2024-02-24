---

---
Möglichkeiten zur Authentisierung des Datenursprungs bzw. zur Peer-Entity Authentication:

1. Verschlüsselung der Nachricht (Authentisierung erfolgt mittelbar durch Wissen, d.h. Kenntnis des Schlüssels) 
2. Digitale Signatur 
3. Message Authentication Code ([[MAC]]) MAC = Hashverfahren + gemeinsamer Schlüssel 
4. Hashed Message Authentication Code ([[HMAC]]) 

-> Kombinationen der angegebenen Verfahren

Nomenklatur: [[Kryptologie#^ad0405]] 
#### Authentisierung durch symm. Verschlüsselung
![[Pasted image 20240224000613.png]]
**Merkmale**: 
- Authentisierung des Datenursprungs (Nachricht kann nur von Alice stammen, wenn der Schlüssel nur Alice und Bob bekannt ist) 
- Bob wird nicht explizit authentisiert, aber nur Bob kann Nachricht nutzen 
- [[Vertraulichkeit]] der Daten (nur Alice und Bob kennen K)

„**Nachteile**“: 
- Sender kann die Sendung leugnen (Bob könnte sich die Nachricht auch selbst geschickt haben) 
- Alice / Bob können Zugang / Empfang nicht beweisen

#### Authentisierung durch asym. Verschlüsselung
![[Pasted image 20240224000820.png]]

**Merkmale**: 
- Bob wird nicht explizit authentisiert, aber nur Bob kann Nachricht nutzen 
- Vertraulichkeit der Daten (nur Bob kennt seinen privaten Schlüssel)

**Nachteile**: 
- KEINE Authentisierung des Datenursprungs (Jeder kann senden, weil jeder Bobs Public Key haben kann) 
- Sender kann die Sendung leugnen (könnte irgendjemand anderes gewesen sein) 
- Alice / Bob können Zugang / Empfang nicht beweisen

#### Digitale Signatur
![[Pasted image 20240224001733.png]]

**Merkmale:** 
- Authentisierung des Datenursprungs (Nachricht kann nur von Alice stammen; nur Alice kennt ihren geheimen Schlüssel) 
- Jeder kann die Signatur verifizieren (auch ohne Mithilfe von Alice) 
- Alice kann die Sendung nicht leugnen 

**Nachteile**
- Bob wird nicht authentisiert 
- Keine Vertraulichkeit (Jeder kann Nachricht lesen, jeder „kennt“ öffentlichen Schlüssel von Alice) 
- Alice kann Zugang nicht beweisen

#### Asym. Verschlüsselung + Signatur
![[Pasted image 20240224002045.png]]

**Merkmale**
- Authentisierung des Datenursprungs 
- Nur Bob kann Nachricht nutzen 
- Vertraulichkeit der Daten 
- Vertraulichkeit der Signatur 
- Alice kann Sendung nicht leugnen 

**Nachteile**
- Operationen für Signatur und asymmetrische Verschlüsselung sind „teuer“ 
- Alice kann Zugang nicht beweisen 
- Bei allen Verfahren bisher keine [[Integrität]]ssicherung („blinde“ Modifikation des Chiffretextes wird nicht erkannt)

#### Verwendung von Hash-Fkt. zur Authentisierung
![[Pasted image 20240224002249.png]]

Authentisierung des Datenursprungs (durch „Geheimnis“ S) 
- Nachricht wird mit S konkateniert und dann der Hash berechnet 
- (Daten-) Integrität (durch Hash) 

**Nachteile**
- Keine Vertraulichkeit, jeder kann M lesen 
- Alice kann Sendung leugnen 
- Alice/Bob können Zugang / Empfang nicht beweisen

#### Verwendung von Hash-Fkt. zur Authentisierung
![[Pasted image 20240224002510.png]]

- Zusätzlich [[Vertraulichkeit]] durch Verschlüsselung 

**Nachteile**
- Alice kann Sendung leugnen 
- Alice/Bob können Zugang / Empfang nicht beweisen
---
![[Pasted image 20240224002753.png]]

- Authentisierung des Datenursprungs (durch Schlüssel K) 
- [[Vertraulichkeit]] 
- [[Integrität]]
---
![[Pasted image 20240224002906.png]]
- Authentisierung und Integrität, keine Vertraulichkeit
--- 
![[Pasted image 20240224003007.png]]

- Authentisierung des Datenursprungs durch digitale Signatur 
	- Alice signiert Hash 
- (Daten-) Integrität (durch Hash) 
**Nachteile**
- Keine Vertraulichkeit, jeder kann M lesen 
- Alice kann Zugang nicht beweisen
---
![[Pasted image 20240224003109.png]]

- Zusätzlich Vertraulichkeit durch (symmetrische) Verschlüsselung 
- Am häufigsten verwendetes Verfahren 
**Nachteile**
- Alice kann Zugang nicht beweisen

