Formeln in disjunktiver und konjunktiver Normalform ([[DNF]] und [[KNF]]) sind definiert durch:

- Ein [[Term]] ist eine *Konjunktion* $a_1 \: ∧ . . . ∧ \:a_k$ von [[Literal]]en. 
- Eine [[Klausel]] ist eine *Disjunktion* $a_1 \:∨ . . . ∨ \:a-k$ von [[Literal]]en. 
- Eine Formel in [[DNF]] ist eine *Disjunktion* $T_1 \:∨ . . . ∨ \:T_m$ von [[Term]]en. 
- Eine Formel in [[KNF]] ist eine *Konjunktion* $C_1\: ∧ . . . ∧\: C_m$ von [[Klausel]]n. 

Jede Formel in [[KNF]] oder [[DNF]] ist in [[Negations-Normalform|NNF]].

>[!info] Theorem
> Für jede Formel $F$ gibt es $\hat F$ in [[KNF]] und $\check F$ in [[DNF]] mit $\hat F ≡ \check F ≡ F$ 

### Normalformen und Semantik

Semantische Eigenschaften sind fur [[DNF]] und [[KNF]] einfach:

- Ein [[Term]] $a_1 \: ∧ . . . ∧ \: a_k$ ist [[erfüllbar]],
	gdw. er keine komplementären [[Literal]]e enthält, 
	d.h. für alle $i, j ≤ m$ ist $a_i \ne \overline a_j$ . 

- Eine Formel in [[DNF]] ist [[erfüllbar]], 
	gdw. einer ihrer [[Term]]e [[erfüllbar]] ist. 

- Eine [[Klausel]] $a_1 \: ∨ . . . ∨ \:a_k$ ist [[Tautologie]], 
	gdw. sie komplementäre [[Literal]]e enthält, 
	d.h. es gibt $i, j ≤ m$ mit $a_i = \overline a_j$ . 

- Eine Formel in [[KNF]] ist [[Tautologie]], gdw. jede ihrer [[Klausel]]n [[Tautologie]] ist.


### Exponentieller Blow-Up

>[!info] Theorem 
>Es gibt Formeln $F_n$ in [[KNF]] der Größe $|F_n| = O(n)$ so dass jede Formel $G_n ≡ F_n$ in [[DNF]] die Größe $|G_n| ≥ n2^n$ erfordert.

>[!info] Theorem 
>Es gibt Formeln $F^′_n$ in [[DNF]] der Größe $|F^′_n | = O(n)$ so dass jede Formel $H_n ≡ F_n$ in [[KNF]] die Größe $|H_n| ≥ n2^n$ erfordert.

