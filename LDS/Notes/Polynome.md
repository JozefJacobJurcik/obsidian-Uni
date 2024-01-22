---
aliases: Polynom, polynomial
---
Sei $K$ ein [[Körper]] und $x$ eine Variable.

Ein **Polynom** über $K$ in $x$ ist ein Ausdruck
$$p(x) = a_nx^n + a_{n−1}x^{n−1} + . . . + a_1x + a_0$$
für $n ∈ \mathbb N_0$ und $a_i ∈ K$ für $i = 0, . . . , n$ .

$K[x]$ bezeichnet die [[Menge]] der **Polynome** über $K$ in $x$ .


Ein *Polynom* definiert $p(x)$ definiert eine [[Funktion]] $f_p : K → K$
$$f_p(b) := a_n · b^n + a_{n−1} · b^{n−1} + . . . + a_1 · b + a_0 $$
Für $f_p(b)$ schreiben wir auch $p(b)$

### Grad
Der *Grad* von $p(x)$ ist $\operatorname{deg} p(x) = \operatorname{max} \{ d ∈ \mathbb N ; a_d \ne 0 \}$ 
*Ausnahme:* das Polynom $p(x) = 0$ hat Grad $\operatorname{deg} p(x) = -1$.

### Auswertung von Polynomen

Es gilt: $p(b)$ lässt sich berechnen als:
$$\begin{split}p(b) & = a_n · b^n + a_{n−1} · b^{n−1} + . . . + a_1 · b + a_0 \\ &= ((. . .((a_nb + a_{n−1})b + a_{n−2})b + . . .)b + a_1)b + a_0\end{split}$$
Dieses *Horner-Schema* als Algorithmus:

```pseudocode
p := a_n 
for i := (n − 1) to 0 do
	p := p · b + a_i 
return p
```

### Rechnen mit Polynomen

Seien $a(x) = a_nx^n + . . . + a_1x + a_0$  und  $b(x) = b_mx^m + . . . b_1x + b_0$

*Die Summe* $c(x) = a(x) + b(x)$   ist   $c(x) = c_kx^k + . . . c_1x + c_0$   mit
	$k = \operatorname{max}(n, m)$   und   $c_i = a_i + b_i$   für    $i = 0, . . . , k$.

*Das Produkt* $c(x) = a(x) · b(x)$   ist   $c(x) = c_k x^k + . . . c_1x + c_0$   mit 
	$k = n + m$   und   $c_i = \sum^i_{j=0} a_jb_{i−j}$   fur    $i = 0, . . . , k$

$K[x]$ bildet mit diesen Operationen $+$ und $·$ einen [[Kommutativgesetz|kommutativ]]en [[Ring]].
- [[Neutrales Element]] bzgl. $+$ : Nullpolynom $p(x) = 0$
- Neutrales Element bzgl. $·$ : Konstantes Polynom $p(x) = 1$

##### Polynomdivision
See also [[Polynomdivision]]

>[!info] Theorem 
>Für  $a(x), b(x) ∈ K[x]$ gibt es eindeutige $q(x),r(x) ∈ K[x]$ mit 
>	$r(x) = 0\quad$   oder   $\quad\operatorname{deg} r(x) < \operatorname{deg} b(x)\quad$   und   $\quad a(x) = q(x) · b(x) + r(x)$

Damit lassen sich Begriffe der Zahlentheorie auf Polynome übertragen:

- *Teilbarkeit:*
	$d(x)$ ist Teiler von $p(x)$, wenn $p(x) = d(x) · t(x)$ für ein $t(x)$

- *Äquivalenz:*
	$a(x) ≡ b(x)\quad (\operatorname{mod}\: m(x))$   wenn   $m(x)$   teilt   $a(x) − b(x)$

### [[ggT]] und Irreduzibilität

See also: [[ggT Polynome]], [[irreduzibles Polynom]] 

>[!tip]
>Ein irreduzibles Polynom vom Grad ≥ 1 hat keine Nullstellen, da bei einer Nullstelle a das Polynom x − a ein Teiler wäre.

##### Vorlesung:

Seien $p(x), q(x) ∈ K[x]$

$d(x) ∈ K[x]$ heißt [[ggT]] von $p(x)$ und $q(x)$, wenn gilt:
- $d(x)$ teilt $p(x)$ und $q(x)$
- für jedes  $d^′ (x)$, das $p(x)$ und $q(x)$ teilt, ist $d^′ (x)$ Teiler von $d(x)$

Der [[erweiterte Euklidische Algorithmus]] berechnet:
- einen [[ggT]] $d(x)$ von $p(x), q(x)$ 
- $s(x),t(x)$ mit $d(x) = s(x)p(x) + t(x)q(x)$

$p(x) ∈ K[x]$ mit $\operatorname{deg} p(x) > 0$ heißt **irreduzibel**, wenn gilt: 
	Ist $p(x) = a(x)b(x)$, dann ist    $\operatorname{deg} a(x) = 0$    oder   $\operatorname{deg} b(x) = 0$.

### Nullstellen
Ein $a ∈ K$ mit $p(a) = 0$ heißt **Nullstelle** von $p(x)$.

>[!tip] Lemma
>$a$ ist *Nullstelle* von $p(x)$    gdw.    $(x − a)$  Teiler von $p(x)$ ist.

>[!info] Theorem
>Ein Polynom $p(x) \ne 0$ mit $\operatorname{deg} p(x) = n$ hat höchstens $n$ Nullstellen.

>[!info] Theorem (Fundamentalsatz der Algebra) 
>Jedes Polynom $0 \ne p(x) ∈ \mathbb C[x]$ mit $\operatorname{deg} p(x) > 0$ hat mindestens eine Nullstelle.

![[Körpererweiterung]]