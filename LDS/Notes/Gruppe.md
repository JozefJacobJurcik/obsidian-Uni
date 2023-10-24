---
klausur: 2
---

### Definition 1:
Ein [[Monoid]] $H = (M, \circ)$ mit [[neutrales Element|neutralem Element]] $e$ heißt *Gruppe*, wenn es zu jedem $a ∈ M$ ein [[inverses Element|inverse Element]] $a^{−1} ∈ M$ gibt.

### Definition 2:
Eine *Gruppe* ist ein Paar $( G , ∗ )$ bestehend aus einer [[Menge]] $G$ und einer inneren zweistelligen Verknüpfung $*$ auf $G$. Dabei erfüllt die (in Infixnotation geschriebene) Abbildung
$${\displaystyle *\colon \,{\begin{cases}G\times G&\to &G\\(a,b)&\mapsto &a*b\end{cases}}}$$
die folgenden, *Gruppenaxiome* genannten, Forderungen:

- Für alle $a, b, c\in G$ gilt: ([[Assoziativgesetz|Assoziativität]])
$${\displaystyle (a*b)*c=a*(b*c)}$$
- Es gibt ein (einziges) [[neutrales Element]] $e\in G$, mit dem für alle $a\in G$ gilt: (Existenz des neutralen Elements)
$${\displaystyle a*e=e*a=a}$$
- Zu jedem $a\in G$ existiert ein (einziges) [[inverses Element]] (Existenz des inversen Elements)
$$a^{-1}\in G \quad\operatorname{mit}\quad  a*a^{-1}=a^{-1}*a=e$$
Eine *Gruppe* ist also ein [[Monoid]], in dem jedes Element ein Inverses hat.

Wenn $(G,*)$ eine *Gruppe* ist, heißen die Elemente der [[Menge]] $G$ Elemente der Gruppe, kurz *Gruppenelemente*. 

##### Schwache Gruppenaxiome
Die Gruppenaxiome können formal abgeschwächt werden, indem man die Axiome für die Existenz des [neutralen Element](neutrales%20Element.md) und der [inverse Element](inverses%20Element.md)e folgendermaßen ersetzt:

Es gibt ein $e ∈ G$, so dass gilt:

- Für alle $a ∈ G$ gilt: $e ∗ a = a$ – hiermit heißt $e$ _linksneutrales Element._
- Zu jedem $a ∈ G$ existiert ein $b ∈ G$ mit $b ∗ a = e$ – so ein Element $b$  heißt _zum Element_ $a$ _linksinverses Element_ (bezüglich des linksneutralen Elements $e$)_._

Diese formal schwächere Definition ist äquivalent zu der ursprünglichen Definition.
### ![[Abelsche Gruppe]]
### Rechenregeln in Gruppen
In allen *Gruppen* gelten die folgenden Rechenregeln und -gesetze:

- [[Involution|Involutionsgesetz]]: $(a^{−1} )^{−1} = a$

- Kürzungsregeln:
	aus $a \circ b = c \circ b$ folgt $a = c$ 
	aus $a \circ b = a \circ c$ folgt $b = c$

- Lösbarkeit linearer Gleichungen:
	aus $a \circ x = b$ folgt $x = a^{−1} \circ b$ 
	aus $x \circ a = b$ folgt $x = b \circ a^{−1}$

- [[Injektivität]] von $\circ$ :
	$a \ne b$    gdw.    $a \circ c \ne b \circ c$    gdw.    $c \circ a \ne c \circ b$

- [[Surjektivität]] von $\circ$ :
	es gibt $x$ mit $a \circ x = b$ und $y$ mit $y \circ a = b$

##### Potenzen
Für $z ∈ \mathbb Z$ definiere die Potenz $a^z$ durch: 
- $a^0 = e$ 
- $a^{i+1} = a^i \circ a$ für  $i ≥ 0$ 
- $a^{−k} = (a^{−1} )^k$ für  $k ≥ 1$

**Potenzgesetze:**
- $a^m \circ a^n = a^{m+n}$
- $(a^m)^n = a^{mn}$
- aus $a^m = a^n$ folgt $a^{m−n} = e$


 ![[Ordnung]]

![[Zyklische Gruppe]]



###### Beispiele:
- $(\mathbb N_0, +)$ ist ein [[Monoid]], aber keine Gruppe
- $(\mathbb Z, +)$ ist eine [[Abelsche Gruppe]] 
- $(\mathbb Z, ·)$ und $(\mathbb Q, ·)$ sind keine Gruppen
- $(\mathbb Q \setminus {0}, ·)$ ist eine [[Abelsche Gruppe]] 
- $(\mathbb Z_n, +)$ ist eine abelsche Gruppe
- $(\mathbb Z_6 \setminus {0}, ·)$ ist keine Gruppe. 
- $\mathbb Z^∗_n := \{ x ∈ Zn \setminus {0} ; \operatorname{ggT}(x, n) = 1 \}$ 
	$(Z^∗_n , ·)$ ist eine abelsche Gruppe. 
	Insbesondere ist $(\mathbb Z_p \setminus \{0\}, ·)$ eine Gruppe, für jede [Primzahl](Primzahlen.md) $p$. 
	
- $S_n$ ist die [[Menge]] der [[Permutation]]en von $[n]$, 
	also der [bijektiv](Bijektivität.md)en [[Funktion]]en $π : [n] → [n]$ 
	
	$(S_n, \circ)$ ist eine Gruppe, die *symmetrische Gruppe* vom Grad n. Für  n ≥ 3 ist $S_n$ nicht abelsch.