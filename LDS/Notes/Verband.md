
Eine [[Menge]] $A$ mit [[Partielle Ordnung]] $\preceq$ ist ein **Verband**, wenn es für je zwei $a, b$ ein [[Infimum und Supremum|Infimum]] und [[Infimum und Supremum|Supremum]] gibt.

### Rechenregeln

Sei $A$ mit der Ordnung $\sqsubseteq$ ein Verband. 
Wir schreiben $a \sqcup b$ für das [[Infimum und Supremum|Supremum]],  und $a \sqcup b$ für das *Infimum* von $a$ und $b$. *Infimum* und *Supremum* erfüllen die folgenden Gesetze:  

$a \sqsubseteq b$   *gdw.*   $a \sqcap b = a$   *gdw.*   $a \sqcup b = b$ 

[[Assoziativgesetz|Assoziativität]] 
- $a \sqcup (b \sqcup c) = (a \sqcup b) \sqcup c$   und   $a \sqcap (b \sqcap c) = (a \sqcap b) \sqcap c$ 

[[Kommutativgesetz|Kommutativität]] 
- $a \sqcup b = b \sqcup a$   und   $a \sqcap b = b \sqcap a$ 

[[Absorptionsgesetz|Absorption]]
- $a \sqcup (a \sqcap b) = a$   und   $a \sqcap (a \sqcup b) = a$

 ![[Distributive Verbände]]
 
###### Beispiel 1: Potenzmengenverband
$\mathcal P (M)$ mit der Ordnung $\subseteq$ 

- $A \cup B$ ist das [[Infimum und Supremum|Supremum]], und $A \cap B$ das *Infimum* von $A$ und $B$. 
- *Kleinstes Element* ist $\emptyset$, *größtes Element* ist $M$

###### Beispiel 2: Teiler verband
${ x \in \mathbb N ;\: x \:|\: n }$ mit der Ordnung | (Teilbarkeit) 
- [[ggT]]$(x, y)$ ist das [[Infimum und Supremum|Infimum]], und [[kgV]]$(x, y)$ das *Supremum* von $x$ und $y$. 
- Kleinstes Element ist 1, größtes Element ist n.

###### Beispiel 3: Partitionsverband

Seien $\mathcal A = \{ A_1, . . . , A_n \}$ und $\mathcal B = \{ B_1, . . . , B_m \}$ [[Partition]]en einer [[Menge]] $M$. 

Die [[Relation]] $A \preceq B$ ist definiert durch $\forall i \leq n \:\: \exists j \leq m \:\: A_i \subseteq B_j$ 

$Part(M)$ ist die [[Menge]] aller Partitionen von $M$.

>[!info] Theorem 
>Die Menge $Part(M)$ mit der Relation $\preceq$ bildet einen *Verband*.

**Bemerkung:** die Zahlen $B_n = |Part([n])|$ heißen [[Bell-Zahlen]] Es gilt: $B_0 = B_1 = 1,\:\: B_2 = 2,\:\: B_3 = 5,\:\: B_4 = 15,\:\: B_5 = 52, . . .$
