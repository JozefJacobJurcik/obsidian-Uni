---

---

Benannt nach den Erfindern: Rivest, Shamir, Adleman (1978) 
Sicherheit basiert auf dem *Faktorisierungsproblem*: 
- Geg. zwei große Primzahlen $p$ und $q$ (z.B. 200 Dezimalstellen): 
- $n=pq$ ist auch für große Zahlen einfach zu berechnen, 
- aber für gegebenes $n$ ist dessen Primfaktorzerlegung sehr aufwendig 

Erfüllt alle Anforderungen an asymmetrisches Kryptosystem 
1983 (nur) in USA patentiert (im Jahr 2000 ausgelaufen)
Große Verbreitung, verwendet in: 
- TLS (Transport Layer Security) 
- PEM (Privacy Enhanced Mail) 
- PGP (Pretty Good Privacy) 
- GnuPG (GNU Privacy Guard) 
- SSH 
- ....

### Erzeugung eines Schlüsselpaars

Randomisierte Wahl von zwei ähnlich großen, unterschiedlichen Primzahlen, $p$ und $q$ 

$n = pq$ ist sog. RSA-Modul 

Euler‘sche Phi-Funktion gibt an, wie viele positive ganze Zahlen zu n teilerfremd sind: $\Phi(n) = (p-1)(q-1)$

Wähle teilerfremde Zahl $e$ mit $1\lt e \lt \Phi(n)$
d.h. der größte gemeinsame Nenner von $e$ und $\Phi(n)= 1$
- Für $e$ wird häufig 65537 gewählt: Je kleiner e ist, desto effizienter ist die Verschlüsselung, aber bei sehr kleinen e sind Angriffe bekannt. 
- Der öffentliche Schlüssel besteht aus dem RSA-Modul $n$ und dem Verschlüsselungsexponenten $e$. 

Bestimme Zahl $d$ als multiplikativ Inverse von $e$ bezüglich $\Phi(n)$ 
$$d = e^{-1}\:\operatorname{mod}\: \Phi(n)$$
- Berechnung z.B. über den erweiterten Euklidischen Algorithmus 
- $n$ und $d$ bilden den privaten Schlüssel; $d$ muss geheim gehalten werden

### Ver- und Entschlüsselung

Alice kommuniziert ihren öffentlichen Schlüssel $(n,e)$ geeignet an Bob (Ziel hier: [[Authentizität]] von Alice, nicht [[Vertraulichkeit]]!) 

Bob möchte Nachricht $M$ verschlüsselt an Alice übertragen:
- Nachricht $M$ wird als Integer-Zahl m aufgefasst, mit $0 \lt m \lt n$  d.h. Nachricht m muss kleiner sein als das RSA-Modul $n$ 
- Bob berechnet [[Ciphertext]] $c = m^e (\operatorname{mod} n)$ 
- Bob schickt $c$ an Alice 

Alice möchte Ciphertext $c$ entschlüsseln 
- Alice berechnet hierzu $m = c^d (\operatorname{mod} n)$
- Aus Integer-Zahl $m$ kann Nachricht $M$ rekonstruiert werden.