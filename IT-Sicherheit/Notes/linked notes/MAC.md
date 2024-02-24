---
aliases: Message Authentication Code
---

Message Authentication Code (MAC) für Nachricht $M$ 

**Idee**: Kryptographische Checksumme wird mit Algorithmus $A$ berechnet, $A$ benötigt einen Schlüssel $K$ 

MAC = $A(K,M)$ 

Authentisierung über Schlüssel $K$ (kennen nur Alice und Bob)

![[Pasted image 20240224003550.png]]

See also: Hashed MAC ([[HMAC]])
### Sicherheit von MACs

##### Brute Force:
- MAC ist $n$ Bits lang, Schlüssel $K$ ist $k$ Bits lang mit $k > n$ 
- Angreifer kennt Klartext $m$ und MAC$(m,K)$ 
- Für alle $K_i$ berechnet der Angreifer: MAC$(m,K_i)$ == MAC$(m,K)$? 
- D.h. der Angreifer muss $2^k$ MACs erzeugen 
- Es existieren aber nur $2^n$ verschiedene MACs $(2^n < 2^k)$ 
- D.h. mehrere $K_i$ generieren den passenden MAC ($2^{(k-n)}$ Schlüssel) 
- Angreifer muss den Angriff iterieren: 
	1. Runde liefert für $2^k$ Schlüssel ca. $2^{(k-n)}$ Treffer 
	2. Runde liefert für $2^{(k-n)}$ Schlüssel $2^{(k-2n)}$ Treffer 
	3. Runde liefert .... $2^{(k-3n)}$ Treffer
Falls $k < n$, liefert die erste Runde bereits den korrekten Schlüssel

##### length extension attack
- Möglich wenn Hash-Funktion mit Merkle-Damgard-Konstruktion verwendet wird (z.B. [[MD5]], SHA, SHA-1) 
- MAC$(k,m)$, z.B. SHA-1$(k||m)$ 
- Dienst liefert für $m$ MAC als Ausweis für Dienstnutzung 

- Angreifer kennt Blocklänge und Länge der Nachricht 

- Angreifer kann Nachricht verlängern ohne $k$ zu kennen 
- SHA-1$(k||mm’)$ liefert „gültigen“ Hash auch ohne Kenntnis von $k$ 
- Beispiel $m$=Überweise-100-€ 
- Beispiel $m’$=\x00\x00\x00&Überweise-10000000000000-$