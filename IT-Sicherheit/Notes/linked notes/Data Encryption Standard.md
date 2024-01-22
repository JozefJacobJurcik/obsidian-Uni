---
aliases: DES
---

1977 vom NBS (National Bureau of Standards; heute: National Institute of Standards (NIST)) in USA zum Standard erklärt 

**2002 durch** [[Advanced Encryption Standard|AES]] (Advanced Encryption Standard) **ersetzt** 
DES entwickelt von IBM aus dem 128-Bit-Verfahren LUCIFER 

Klassifikation: 
- Symmetrisches Verfahren 
- *Mit Permutation, Substitution und bitweiser Addition modulo 2* 
- *Blockchiffre mit 64 Bit großen Ein- und Ausgabeblöcken* 
- *Schlüssellänge 64 Bit*, davon 8 Paritätsbits, d.h. effektive Schlüssellänge (nur) 56 Bit 

**Bedeutung von DES:** 
- Erstes standardisiertes Verfahren mit intensiver, weltweiter Nutzung 
- Aus heutiger Sicht einfach zu knacken (Verbesserung: 3DES) 
- Zeigt aber viele Bestandteile moderner symmetrischer Verschlüsselungsverfahren.

##### DES: Zusammenfassung

![[Pasted image 20240118160107.png]]

### Stärken und Schwächen

##### Stärken:
- Starker [[Avalanche Effekt]] (Lawineneffekt; große Streuung) Kleine Änderungen in der Eingabe breiten sich schnell aus. Eine Änderung eines Bits in der Eingabe verursacht eine Änderung von durchschnittlich 50% der Ausgabe.
- 16 Iterationen: Known-plaintext Angriff auf DES mit < 16 Runden immer effizienter als Brute force
- Stark gegen analytische Angriffe: Differentielle Kryptoanalyse braucht 258 Operationen.

##### Schwächen:
- *(teilweise) geheimes Design*
- *Deutlich zu geringe Schlüssellänge:* Schlüsselraum der Größe $2^{58}$
- 4 schwache Schlüssel mit: DES(DES(x,K),K) = x
- 6 semi-schwache Schlüsselpaare: DES(DES(x,K),K‘) = x
- Optimiert auf Implementierung in Hardware: Initialpermutation IP und inverse IP verbessern die Sicherheit nicht, sondern erhöhen nur den Aufwand für Software-Implementierungen

### Deep Crack

1998 von der Electronic Frontier Foundation (EFF) für rund $250.000 gebaut. 
- 29 beidseitig bestückte Platinen mit je 64 Deep Crack Chips 
- *Knackte DES-Schlüssel innerhalb weniger Tage*. 

Sollte demonstrieren, dass DES **nicht mehr sicher ist**.

### DES Varianten

*Double-DES*: 
- DES(DES(m,K1),K2)
- Erwartete Komplexität: 
	- bei Schlüssellänge n: $2^{2n}$

Merkle und Hellman haben gezeigt, dass ein Known-Plaintext Angriff möglich ist mit Komplexität $2^{n+1}$ 
- D.h. doppelte Ausführung von DES bringt **KEINE relevante Steigerung der Sicherheit**!

*Triple-DES (3DES)*
- Schlüssellänge eigentlich 168 Bit 
- Wegen Meet-in-the-Middle-Angriff effektiv aber nur 112 Bit

### Abschließende Bemerkungen

Claude Shannon forderte bereits 1949:
- Konfusion ([[Confusion]]) : Vom Chiffretext kann möglichst wenig auf den Klartext geschlossen werden. 
- [[Diffusion]]: Kleine Änderungen an der Eingabe bewirken große Änderungen an der Ausgabe.

DES gehört zur Klasse der [[Feistel cipher]] 
- Horst Feistel (1915-1990), arbeitete für IBM an DES mit 
- Bezeichnung für bijektive symmetrische Blockverschlüsselungsverfahren mit typischen Eigenschaften: 
	- Zerlegung des Eingabeblocks in zwei Teile 
	- n Runden mit verschiedenen Rundenschlüsseln 
	- Funktion f muss nicht umkehrbar sein 
	- Alternierende Substitutionen und Permutationen setzen Konfusion und Diffusion um (Avalanche-Effekt nach Feistel).

Iterationen und zueinander ähnliche Ver-/Entschlüsselung ermöglichen günstige Hardwareimplementierungen.