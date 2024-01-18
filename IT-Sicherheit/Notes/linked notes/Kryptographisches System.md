Ein Kryptosystem *KS* ist ein Fünftupel
$$KS = (M, K, C, e, d)$$
$M$ = Nichtleere, endliche [[Menge]] aller [[Plaintext|Klartext]]e (Messages) 
$K$ = Nichtleere, endliche Menge aller Schlüssel (Keys) 
$C$ = Menge von Chiffretexten ([[Ciphertext]]s) 
$e = M \times K \rightarrow C$   ist *Verschlüsselungsfunktion* 
$d = C \times K \rightarrow M$   ist *Entschlüsselungsfunktion*
$$\forall \, k_e \in K : f(k_e)=k_d \quad\quad\quad\quad d(e(m,k_e),k_d)=m $$

###### Substitution:

*Substitution*: $f: A^n_1 \rightarrow A^m_2$
Alphabete: $A_1 = \{a,b,...,z\}(=\mathbb Z_{25}); A_2 = \{1,2,3,4,5\}$
Verschlüsselungsverfahren: $E : A_1^1 \rightarrow A_2^2$
Schlüssel: $K_E = K_D$

![[Pasted image 20240114212514.png]]

**Beispiel** (pro Buchstabe Zeilen-/Spaltennummer ermitteln): 
`vorlesung` wird zu `513442311543453322`

###### Permutation
*Permutation* als Spezialfall der Substitution: $f: A^n \rightarrow A^m$
	gleiche Wortlänge; gleiche Alphabete $A_1 = A_2 = \{a,b,...,z\}$ 

$K_E = K_D$ (hier: NEWYORK) 
	(Zur besseren Lesbarkeit werden Chiffrentexte trotzdem oft in Großbuchstaben dargestellt.) 

Matrixschreibweise: 
![[Pasted image 20240114212855.png]]

Zykelschreibweise: (a,n,h) (b,e,o,i) (c,w,u,s,p,j) (d,y,x,v,t,q,l,f,r,m,g,k) (z) 

**Beispiel**: 
TIMFOPSHKBQPBWAOMAOBQ = Vorlesung it sicherheit 

Chiffrentext wird in Blöcken übertragen Leer- und Satzzeichen werden nicht kodiert (Kryptanalyse: Leerzeichen noch häufiger als „e“)

### Symmetrische Verfahren

- Kommunikationspartner teilen *gemeinsamen, geheimen Schlüssel* (Shared Secret; deshalb: Symmetrie) 
- Ver- und Entschlüsselungsschlüssel sind identisch oder jeweils trivial aus dem Shared Secret abzuleiten. 
- Setzt vorherige Verständigung (*Schlüsselaustausch*) voraus. 

**Protokoll:**
1. Alice und Bob vereinbaren („out of band“) den gemeinsamen Schlüssel: $k_e = k_d = k_{A,B}$
2. Alice verschlüsselt $m$ : $c = e(m,k_{A,B})$ und sendet $c$ an Bob 
3. Bob entschlüsselt $c$ : $m = d(c, k_{A,B}) = d(e(m, k_{A,B}), k_{A,B})$

**Beispiele:** DES, AES, IDEA, RC4, Blowfish, Serpent, Twofish, ...

### Asymmetrische Verfahren

Jeder Partner besitzt *Schlüsselpaar* aus 
- persönlichem, geheim zu haltenden Schlüssel (*private key*) (wird NIE übertragen) 
- und öffentlich bekannt zu gebenden Schlüssel (*public key*) (kann über unsichere und öffentliche Kanäle übertragen werden) 

**Protokoll:** 
1. Alice und Bob erzeugen sich Schlüsselpaare: $(k^A_e,k^A_d)(k^B_e,k^B_d)$
2. Öffentliche Schlüssel $(k^A_e,k^B_e)$ werden geeignet öffentlich gemacht 
3. Alice will $m$ an Bob senden; dazu benutzt sie Bobs öffentlichen Schlüssel $c = e(m, k^B_e)$
4. Bob entschlüsselt die Nachricht mit seinem privaten Schlüssel: $m = d(c,k^B_d)=d(e(m, k^B_e), k^B_d)$

**Beispiele:** RSA, DSA, ElGamal, ...

![[One Time Pad]]

