---
aliases: verdecktes Schreiben
---
Methoden, die bereits die Existenz der geheimen Nachricht verbergen (geheime Nachricht in anderer, nicht geheimen „Nachrichten“ verbergen) Unterscheidung: linguistische und technische Steganographie

### Linguistische Steganographie

##### Semagramme: 
Nachrichten, die in Details von Schriften oder Bildern verborgen sind.
###### Beispiel: 

![[Pasted image 20240114201909.png]]

> [!hint]- Hint
> Strands of grass -> morse code

##### Maskierung (Open Code):
Nachricht verborgen in offen übertragener, unverfänglicher Nachricht (z.B. Husten in „Wer wird Millionär“) 
- **Stichworte:** Begriff, Satzteil oder Satz mit vorher vereinbarter Bedeutung; z.B. HIGASHI NO KAZE AME („Ostwind, Regen“) im japanischen Wetterbericht - zwei mal wiederholt - sollte „Krieg mit USA“ bedeuten.

##### Jargon, Millieu-Code:
Sondersprachen oder Sonderzeichen beruflicher oder gesellschaftlicher Art 
- z.B. „Schnee“ für Kokain; „Kies“ für Geld; „abstauben“, ... 
- Für Zensoren durch „gestelzte“ Sprache relativ leicht erkennbar. 
- Umformulieren durch Synonyme kann Inhalt „zerstören“.

### Technische Steganographie

- Herodot (490 v.Chr.): Nachricht auf den rasierten Schädel eines Sklaven tätowiert 
- Alle Arten von „Geheimtinten“ 
- Steganographie in digitalen Bildern; Beispiele mit *outguess*

![[Pasted image 20240114203349.png]]

##### Steganographie in Bildern 
**Cover** = Bild in das die Nachricht eingebettet wird 
- Finde redundante Bits im Cover 
- Least Significant Bits 
- „Rauschen“ 
- Nahe zusammenliegende Farben 

Kodieren der Nachricht in diesen redundanten Bits 

Steganographie führt zu “sehr geringen Veränderungen” im Bild

![[Pasted image 20240114203732.png]]

**Merkmale:**
Unterschiede bei “sehr strukturierten Bildern” mit hohem versteckten Datenvolumen evtl. erkennbar

![[Pasted image 20240114203852.png]]

##### Plausible Deniability (glaubhafte Abstreitbarkeit) 
**Praktisches Problem:** 
	- Verschlüsselung der gesamten Festplatte schützt Vertraulichkeit der Daten 
	- Aber: Strafverfolgung kann evtl. Herausgabe des Passworts verlangen 
	- *Beispiel* Großbritannien: 2-5 Jahre Haftstrafe bei Weigerung, Passwort herauszugeben 

**Lösungsansatz**, z.B. mit *TrueCrypt/VeraCrypt*: 
- Verschlüsselte Festplatte enthält nur unverfängliche Dateien und ist ansonsten scheinbar leer. 
- *„Leerer“ Bereich enthält ein zweites, verschlüsseltes System, das von außen nicht als solches erkennbar ist. *
- Zielperson gibt nur das Passwort für das äußere/erste Dateisystem preis. 
- Randbedingungen in der Praxis: 
	- Auf dem System sollten keine Verweise auf Dateien innerhalb des zweiten Dateisystems vorzufinden sein (Windows-Registry; „zuletzt benutzte Dateien“ in Anwendungen; ...). 
	- Zielperson darf Existenz des zweiten Dateisystems nicht zugeben.

##### Verdeckte Kanäle 
Nachrichtentransport über nicht erkennbare Kanäle/Medien 

**Charakterisierung durch** 
- *Entdeckbarkeit (detectability)*: Nur designierter Empfänger soll versteckte Daten erkennen können. 
- *Ununterscheidbarkeit (indistinguishability)*: Monitor/Zensor soll bei einem ihm bekanntem verdeckten Kanal nicht erkennen können, ob aktuell versteckte Daten übertragen werden oder nicht. 
- *Bandbreite (bandwidth)*: Länge der pro Zeiteinheit verdeckt übertragbaren Daten.
###### Beispiele: 
- Daten im Paket-Header statt in der TCP-Payload (z.B. TCP SeqNr.) 
- Künstliches Delay in übertragenen Datenpaketen 
- Nicht Inhalt, sondern Name und Größe einer Datei sind relevant

##### ![[Spreu-und-Weizen-Algorithmus]]
