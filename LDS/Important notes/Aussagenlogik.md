### Syntax:
Sei $X$ eine [[Menge]] von Variablen. 

Aussagenlogische Formeln über $X$ sind induktiv definiert: 
- die Konstanten 0 und 1 sind Formeln 
- jede Variable $x ∈ X$ ist eine Formel 
- ist $F$ eine Formel, dann auch $¬F$ 
- sind $F$ und $G$ Formeln, dann auch $(F ∧ G)$ 
- sind $F$ und $G$ Formeln, dann auch $(F ∨ G)$ 
- sind $F$ und $G$ Formeln, dann auch $(F → G)$ 

Notation: (F ↔ G) steht für  $((A → B) ∧ (B → A))$

##### informelle Bedeutung

**Variablen:** elementare Aussagen, die wahr oder falsch sein können
- 1 ist wahr, 0 ist falsch. 
- $¬A$ ist wahr gdw. $A$ ist falsch.
- $(A ∧ B)$ ist wahr gdw. $A$ ist wahr und $B$ ist wahr. 
- $(A ∨ B)$ ist wahr gdw. $A$ ist wahr oder $B$ ist wahr. 
- $(A → B)$ ist wahr, gdw. $B$ folgt aus $A$. 

Damit: $(A ↔ B)$ ist wahr, gdw. A und B sind äquivalent.

##### Algebra der Wahrheitswerte
Die Menge der Wahrheitswerte ist $\mathbb B = {0, 1}$, mit $0 \:\widehat{=}$ falsch, $1 \:\widehat{=}$ wahr. Auf der [[Menge]] $\mathbb B$ sind die Operationen $¬, ∧, ∨, →$ definiert durch:
![[Pasted image 20231011214444.png]]
$∧$ und $∨$ sind [[Infimum und Supremum]] in der Ordnung 0 ≤ 1.
	Rechenregeln im [[Verband]] gelten.

### Formale Semantik

Sein $α : X → \mathbb B$ eine Bewertung der Variablen $X$. 

Induktiv ist der Wert $[\![ F ]\!]α$ αeiner Formel $F$ definiert: 
- $[\![ 0 ]\!]α = 0$ und $[\![ 1 ]\!]α = 1$ 
- $[\![ 0 ]\!]α = α(x)$
- $[\![ ¬F ]\!]α = ¬[\![ F ]\!]α$ 
- $[\![ (F ∧ G) ]\!]α = [\![ F ]\!]α∧[\![ G ]\!]α$ 
- $[\![ (F ∨ G) ]\!]α = [\![ F ]\!]α∨[\![ G ]\!]α$ 
- $[\![ (F → G) ]\!]α = [\![ F ]\!]α→[\![ G ]\!]α$

**Definition**: $α$ *erfüllt* $F$, wenn $[\![ F ]\!]α = 1$ ist. 
Man schreibt dafür auch  $α \:|\!\!\!= F$ 

##### Semantik

$F$ ist [[Tautologie]], wenn $α \:|\!\!\!= F$ für alle $α$ gilt. 

$F$ ist [[erfüllbar]], wenn es eine Bewertung $α$ gibt mit $α \:|\!\!\!= F$. 

$F$ und $G$ sind *äquivalent*, $F ≡ G$, wenn für jede Bewertung $α$ gilt $[\![ F ]\!]α =[\![ G ]\!]α$ 

>[!tip] Lemma 
>$F$ ist [[Tautologie]] gdw. $¬F$ unerfüllbar ist. 
>$F ≡ G$ gdw. $F ↔ G$ Tautologie ist. 
>$F$ ist Tautologie gdw. $F ≡ 1$ ist.

### Substitution

Sind $F$ und $G$ Formeln und $x ∈ X$, dann bezeichne $F[x : G]$ die Formel $F$, wo jedes Vorkommen von $x$ durch $G$ ersetzt ist.

$[\![ \:F[x : G]\: ]\!]α = [\![ F ]\!]α^′$ , wobei $α^′$ definiert ist durch: 
	$α^′ (x) = [\![ G ]\!]α$   und   $α ′ (y) = α(y)$   für alle   $y \ne x$.

Sind $F, G, H$ Formeln mit $F ≡ G$, dann gilt: 
	$F[x : H] ≡ G[x : H]$   und   $H[x : F] ≡ H[x : G]$ 

*Beispiel*: für alle Formeln $F, G, H$ gilt: 
	$F ∧ (G ∨ H) ≡ (F ∧ G) ∨ (F ∧ H)$

![[Literal]]

![[Negations-Normalform]]


![[De Morganschen Gesetze]]


![[Negation]]


![[Disjunktive und Konjunktive Normalform]]

![[Sequenzenkalkül]]