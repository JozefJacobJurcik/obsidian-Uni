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

