Eine Sprache $L = (\mathcal C,\mathcal F,\mathcal P)$ __erster Stufe__ ist gegeben durch: 

- Eine [[Menge]] $\mathcal C$ von _Konstantensymbolen_ 
- Eine _Menge_ $\mathcal F$ von _Funktionssymbolen_ jedes Funktionssymbol $f ∈ \mathcal F$ hat eine Stelligkeit $k = k(f ) ∈\mathbb  N$. 
- Eine _Menge_ $\mathcal P$ von _Prädikatensymbole_ jedes Prädikatensymbol $P ∈\mathcal P$ hat eine Stelligkeit $k = k(P) ∈\mathbb N$.

### Formeln
Formeln der Sprache $L$ sind definiert durch:

- Ist $P ∈\mathcal P$ ein Prädikatensymbol der _Stelligkeit_ $k$, 
	und sind $t_1, . . . ,t_k$ [[Term]]e, 
	dann ist $P(t_1, . . . ,t_k)$ eine __atomare Formel__
	
- Sind $F$ und $G$ Formeln, dann auch $¬F, F ∧ G, F ∨ G$ und $F → G$ 

- Ist $F$ eine _Formel_ und $x ∈ X$ eine Variable, 
	dann sind $∀x F$ und $∃x F$ _Formeln_. 

Ein __Quantor__ $∀x$ bindet alle Vorkommen der Variablen $x$ in der Formel $∀x F$. 

Variablen, die durch keinen Quantor gebunden sind, sind __freie Variable__. 

Eine Formel ist __geschlossen__, wenn sie keine freien Variablen enthält.

### Substitution

Ist $F$ eine _Formel_, $x$ eine _Variable_ und $t$ ein _Term_, 
dann bezeichnet $F[x : t]$ die Formel, in der alle freien Vorkommen von $x$ durch $t$ ersetzt werden. 

Interessanter Fall in der Definition bei Quantoren: 
- $(∀x F)[x : t] = ∀x F$ 
- $(∀y F)[x : t]$ wird wie folgt definiert: 
	Umbenennung von $y$ in eine Variable $z \ne x$, die in $t$ nicht vorkommt, 
	anschließend Ersetzung aller freien Vorkommen von $x$ in $F$ durch $t$. 
- Analog für $∃$

### Semantik: Interpretation

Eine Interpretation $A$ einer Sprache erster Ordnung $L = (\mathcal C,\mathcal F,\mathcal P)$ besteht aus:

- einer nichtleeren [[Menge]] $M_A \ne ∅$ 
- für jedes _Konstantensymbol_ $c ∈\mathcal C$ ein Element $c_A ∈ M_A$
- für jedes k-stellige _Funktionssymbol_ $f ∈ \mathcal F$ eine [[Funktion]] $f_A : (M_A)^k → M_A$ 
- für jedes $k$-stellige _Prädikatensymbol_ $P ∈ \mathcal P$ eine Relation $P_A ⊆ (M_A)^k$

![[Kompaktheitssatz]]
