---

---

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
### Basically
A basic principle behind *RSA* is the observation that it is practical to find three very large positive integers $e$, $d$, and $n$, such that with modular exponentiation for all integers $m$ (with $0 ≤ m < n$):
$${\displaystyle (m^{e})^{d}\equiv m{\pmod {n}}}$$
and that knowing $e$ and $n$, or even $m$, *it can be extremely difficult to find* $d$. Here the symbol $≡$ denotes modular [[Kongruenz|congruent]]: i.e. both $(m^e)^d$ and $m$ have the same remainder when divided by $n$.

In addition, for some operations it is convenient that the order of the two exponentiations can be changed: the previous relation also implies
$${\displaystyle (m^{d})^{e}\equiv m{\pmod {n}}}$$
RSA involves a *public key* and a *private key*. The public key can be known by everyone and is used for encrypting messages. The intention is that messages encrypted with the public key *can only be decrypted in a reasonable amount of time* by using the private key. The *public key is represented by the integers $n$ and $e$*, and the *private key by the integer $d$* (although $n$ is also used during the decryption process, so it might be considered to be a part of the private key too). $m$ represents the message (previously prepared with a certain technique explained below). 
### Erzeugung eines Schlüsselpaars

Randomisierte Wahl von zwei ähnlich großen, unterschiedlichen Primzahlen, $p$ und $q$ 

$n = pq$ ist sog. RSA-Modul 

[[Euler‘sche Phi-Funktion]] gibt an, wie viele positive ganze Zahlen zu $n$ [[Teilerfremdheit|Teilerfremd]] sind: $\Phi(n) = (p-1)(q-1)$

Wähle teilerfremde Zahl $e$ mit $1\lt e \lt \Phi(n)$
d.h. der größte gemeinsame Nenner von $e$ und $\Phi(n)= 1$
- Für $e$ wird häufig 65537 gewählt: Je kleiner $e$ ist, desto effizienter ist die Verschlüsselung, aber bei sehr kleinen $e$ sind Angriffe bekannt. 
- Der öffentliche Schlüssel besteht aus dem RSA-Modul $n$ und dem Verschlüsselungsexponenten $e$. 

Bestimme Zahl $d$ als [[Modular multiplicative inverse|modulo multiplikativ Inverse]] von $e$ bezüglich $\Phi(n)$ 
$$d = e^{-1}\:\operatorname{mod}\: \Phi(n)$$
- Berechnung z.B. über den [[erweiterte Euklidische Algorithmus]] 
- $n$ und $d$ bilden den privaten Schlüssel; $d$ muss geheim gehalten werden

### Ver- und Entschlüsselung

Alice kommuniziert ihren öffentlichen Schlüssel $(n,e)$ geeignet an Bob (Ziel hier: [[Authentizität]] von Alice, nicht [[Vertraulichkeit]]!)

Bob möchte Nachricht $M$ verschlüsselt an Alice übertragen:
- Nachricht $M$ wird als Integer-Zahl $m$ aufgefasst, mit $0 \lt m \lt n$  d.h. Nachricht $m$ muss kleiner sein als das RSA-Modul $n$ 
- Bob berechnet [[Ciphertext]] $c = m^e (\operatorname{mod} n)$ 
- Bob schickt $c$ an Alice 

Alice möchte Ciphertext $c$ entschlüsseln 
- Alice berechnet hierzu $m = c^d (\operatorname{mod} n)$
- Aus Integer-Zahl $m$ kann Nachricht $M$ rekonstruiert werden.