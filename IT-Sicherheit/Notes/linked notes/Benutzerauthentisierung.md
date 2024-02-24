---

---

##### Wissen
- Passwort, Passphrase (Unix Passwort Verfahren, vgl. Kap. 3) 
- Einmal-Passwort 
- PIN 
- ...... 
##### Besitz
- Smartcard, Token, („physischer“) Schlüssel, Token-App auf Smartphone 
- Kryptographischer Schlüssel als Datei 
##### Eigenschaft 
- Biometrie: 
	- Fingerabdruck 
	- Stimmerkennung 
	- Gesichtserkennung 
	- Iris-Scan
	- Hand-Geometrie; Venenbild der Hand 
	- Behavioral Biometrics, z.B. – Anschlags- oder Andruck-Charakteristik beim Schreiben – Lippenbewegungen

#### Einmalpasswörter
Motivation 
- Nutzung nicht vertrauenswürdiger Geräte 
- Erwartetes „Shoulder-Surfing“, z.B. bei Messen / Präsentationen 

*Abgehörtes Passwort* soll für den Angreifer möglichst *nutzlos* sein: 
- Passwort kann nicht mehrfach verwendet werden
- Begrenzte Gültigkeitsdauer nach Beginn der Nutzung 
- Aus dem (n-1)ten Passwort lässt sich das n. Passwort nicht ableiten 

Design-Kriterien aus den 1990ern: 
- Benutzer gibt Anzahl der Einmalpasswörter vor 
- Keine Verschwendung von kostbarem Speicherplatz durch Passwort-Listen 
- Keine Out-of-Band-Kommunikation (z.B. Nutzung eines Mobiltelefons) 

Bekannte Verfahren: [[S - Key|S/Key]] und [[OTP]] 
#### Smartcards
Klassifikation und Abgrenzung: 
1. Embossing Karten (Prägung auf der Karte, z.B. Kreditkarte) 
2. Magnetstreifen-Karten; nur Speicherfunktion (alte EC-Karte) 
3. Smartcard (eingebettete Schaltung): 
	- Speicherkarten 
	- Prozessor-Karten 
	- Kontaktlose Karten 
		- Bsp.: Prozessor-Karte mit Fingerabdruck-Sensor 

Zugangsdaten werden auf Karte gespeichert oder erzeugt 
- Schutz der Daten ggf. durch PIN/Passwort und/oder Verschlüsselung 
- PIN-/Passworteingabe setzt vertrauenswürdiges Eingabegerät
#### RSA SecurID
SecurID Token 
- generiert jede Minute eine neue Zahl, die nur durch den zentralen Authentifizierungsserver vorhersagbar ist 
- Diese 6- bis 8-stellige Zahl muss zusammen mit dem Benutzerpasswort eingegeben werden (= 2-Faktor-Authentisierung) 

Unterstützung in kommerziellen VPN-Gateways und OpenSSH 

Zahl wird per AES „berechnet“; Eingabe ist eine „echte“ Zufallszahl (Seed) bei der Fertigung des Tokens.

Aktuelle Produktversion hat USB-Schnittstelle, die als Smartcard / Zertifikatsspeicher dient. Auch als App verfügbar.

**Details:**
Die angezeigte Zahl ist eine AES-Verschlüsselung 
- der Anzahl der seit 01.01.1986 00:00 Uhr vergangenen Sekunden (Klartext) 
- mit der bei der Fertigung gewählten Zufallszahl als Schlüssel 

Damit auch *Zeitabweichungen* der Quartzuhren in den Token berücksichtigbar 

„Lebensdauer“ je nach Modell *1-5 Jahre*; das Gerät schaltet sich zu einem vorgegebenen Zeitpunkt ab. 

*Kein „Batteriewechsel“*: Hardwaremanipulation führt immer zu Hardwarebeschädigung / - Zerstörung 

Kosten ca. 25 Euro pro Token (je nach Mengenrabatt)

#### [[Biometrie]]

#### Multimodale Systeme
Sicherheit lässt sich durch multimodale Systeme deutlich erhöhen 
- Multimodale Systeme kombinieren verschiedene Verfahren

Auch verschiedene biometrische Verfahren lassen sich kombinieren: 
- Erhöhung der Sicherheit 
- Verringerung der Fehlerraten 
- Z.B. Iris-Scan mit Spracherkennung kombiniert