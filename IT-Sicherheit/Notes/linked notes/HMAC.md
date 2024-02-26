---
aliases: Hashed MAC
---

**Gesucht**
[[MAC]], der nicht symm. Verschlüsselung, sondern kryptographische Hash-Funktion zur Kompression verwendet 
- Hashes wie [[SHA-3]] sind deutlich schneller als z.B. [[Data Encryption Standard|DES]] 

**Problem** 
Hash-Funktionen verwenden keinen Schlüssel 

**Lösung** HMAC 
- Beliebige Hash-Funktion $H$ verwendbar, die auf (Input) Blöcken arbeitet 
- Sei $b$ die Blocklänge (meist 512 Bits) 
- Beliebige Schlüssel $K$ mit Länge $|K| = b$ verwendbar 
- Falls $|K| < b$: 
	- Auffüllen mit Null-Bytes bis |$K^+| = b$; d.h. $K^+ = K||0....0$ 
- Falls $|K| > b$: 
	- $K = H(K)$ 
- Schlüssel wird mit konstanten Input- (ipad) bzw. Output-Pattern (opad) XOR verknüpft:
	- ipad = 0x36 ($b$ mal wiederholt), opad = 0x5c ($b$ mal wiederholt)

### HMAC Algorithmus
$$HMAC(m) = H \Big[ (K^+ \oplus opad) || H [(K^+ \oplus ipad) ||m] \Big]$$
1. Schlüssel $K$ auf Länge von $b$ Bits gebracht 
2. $b$ Bits langer Block $S_i := K^+ \: XOR \:\:ipad$
3. Nachricht $m$ mit dem Block $S_i$ konkatenieren 
4. Hash-Wert von $S_i || m$ berechnen 
5. $b$-Bit-Block $S_0 := K+ \: XOR \: \: opad$
6. $S_0$ mit dem Ergebnis von 4. konkatenieren 
7. Hash-Wert über das Ergebnis von 6. berechnen 

Es muss verhindert werden, dass ein Angreifer eigenen Text an die Nachricht $m$ anhängt und einfach den (zweiten, inneren) Hashwert weiterrechnet (s. length extension Attack) 

Die äußere Hashfunktion sichert also nicht den ursprünglichen Nachrichteninhalt, sondern „das Ende“ der Nachricht.