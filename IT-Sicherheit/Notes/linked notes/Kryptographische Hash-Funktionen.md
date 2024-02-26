---
aliases: cryptographic hash function
---

## Hash-Funktionen zur [[Integrität]]ssicherung

**Ziel:** Sicherstellen, dass Manipulationen an einer übertragenen Nachricht erkannt werden.

### Grundlagen
Hash-Funktionen 
- bilden „Universum“ auf endlichen Bildbereich ab 
- sind nicht [[Injektivität|injektiv]] 
- Bildbereich i.d.R. sehr viel kleiner als Universum
- Kollisionen möglich:  
$$\exists\: x, y \in U : x \ne y \wedge h(x) = h(y)$$
Kryptographische Hash-Funktion $H$ : 
- Eingabe: beliebig langes Wort $m$ aus dem Universum $U$ 
- Ausgabe: Hashwert $H(m)$ mit fester Länge 
- $H$ soll möglichst kollisionsresistent sein

### Def. Kryptographische Hashfunktion

*Schwache Hash-Funktion* $H$: 
- $H$ besitzt die Eigenschaften einer *Einwegfunktion* 
- Hashwert $H(m) = h$ mit $|h|=k$ (z.B. k = 128 Bits) ist bei gegebener Nachricht m einfach zu berechnen 
- Bei gegebenem $h = H(m)$ für $m \in A^*_1$ ist es praktisch unmöglich, eine (sinnvolle) $m$‘ zu finden mit:
$$m´ \ne m \:,\:\:  m´ \in A^*_1 \:\: \wedge \: H(m´)=h $$

*Starke Hash-Funktion* $H$ :
- $H$ hat alle Eigenschaften einer schwachen Hash-Funktion 
- Es ist zusätzlich praktisch unmöglich, eine Kollision zu finden, d.h. ein Paar verschiedene Eingabewerte m und m‘ mit:
$$m´ \ne m \:,\:\:  m,m´ \in A^*_1 \:\: \wedge \: H(m)=H(m´) $$

### Birthday Attack auf One-Way-Hash-Funktionen

>[!question]- Wie viele Personen brauchen Sie, damit mit Wahrscheinlichkeit P > 0,5 zwei Personen am selben Tag Geburtstag haben? 
> Antwort: 253   $$P = 1 - ( 1 - \frac{1}{365})^n \quad \quad \operatorname{(ab\: n=253 \: ist \:P> 0,5)}$$


>[!question]- Wie viele Personen brauchen Sie, damit mit Wahrscheinlichkeit P > 0,5 zwei Personen am selben Tag Geburtstag haben?
>Antwort: 23
>$$P = 1 -  \frac{365 \cdot 364 ... (365-(n-1))}{365^n} \quad \quad \operatorname{(ab\: n=23 \: ist \:P> 0,5)}$$

Wie können Sie dieses Wissen für Angriffe gegen Hash-Funktionen nutzen? 
**Eine Kollision zu finden ist deutlich einfacher als zu einem gegebenen Hash-Wert einen passenden Text!**

##### Vorgehensweise
1. Alice sichert mit einem $k$ Bits langen Hash eine Nachricht $M$ 
2. Mallet erzeugt $2^{k/2}$ Variationen der Nachricht $M$

Die Wahrscheinlichkeit für eine Kollision ist größer 0,5. 

Wie können $2^{k/2}$ Variationen erzeugt werden? 
- Z.B. Einfügen von „Space – Backspace – Space“ Zeichen zwischen Wörtern 
- Wörter durch Synonyme ersetzen 
- .....

###### Beispiel für einen Brief mit $2^{37}$ Variationen

![[Pasted image 20240123014742.png]]

### Konstruktion kryptographischer Hash-Funktionen
- Folge von Kompressionsfunktionen $G$ 
- Nachricht $m$ wird in Blöcke $Mi$ mit fester Länge $y$ zerlegt 
- Hash-Verfahren wird mit Initialisierungswert IV vorbelegt

![[Pasted image 20240123015008.png]]

Letzter Block $Mn$ muss ggf. auf vorgegebene Länge $y$ „aufgefüllt“ werden (Padding) 
Als Kompressionsfunktion $G$ können verwendet werden: 
- Hash-Funktionen auf der Basis symmetrischer Blockchiffren 
- Dedizierte Hash-Funktionen

### Algorithmen:

##### DES als Kompressionsfunktion
[[Data Encryption Standard|DES]] im Cipher Block Chaining (CBC) Mode
![[Pasted image 20240123020505.png]]
Letzter Output Block ist Hashwert 
Länge des Hashwerts? - 64 Bits

![[MD5]]
 
 ![[SHA-3]]
### Praktisches Anwendungsbeispiel: Passwort-Hashes

- Krypto-Hashes werden verwendet um Passwörter (PW) zu speichern 
- Bei PW-Eingabe wird Hash berechnet und mit gespeichertem verglichen 
	- Hash als Einwegfunktion - Rückrechnung von Hash auf Passwort „schwer“ 
	- ABER: gleiches Passwort liefert gleichen Hash 
	- Damit Wörterbuchangriff oder Rainbow-Tables (vgl. Kap. 12) möglich 
	- Offline Angriff auf gestohlene Hash-Listen

- Abhilfe: 
	- Salt: Zufallszeichenkette der beim Hash mitberechnet und mitgespeichert wird (vgl. Kap 3) - allerdings länger als beim ursprünglichen crypt - mindestens so lang wie Hash 
	- Pepper: geheime Information, die nicht mit gespeichert wird: 
		- gespeichert wird Salt | Hash(Passwort, Salt, Pepper) 
	- Verwendung spezieller Hash-Funktionen 
		- vgl. Password Hashing Competition - Gewinner Aragon 
		- Speicherabhängige Hashes - damit fällt GPU-Vorteil weg