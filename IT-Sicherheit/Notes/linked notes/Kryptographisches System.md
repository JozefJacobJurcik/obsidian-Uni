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

![[Symmetrische Verfahren]]

![[Asymmetrische Verfahren]]