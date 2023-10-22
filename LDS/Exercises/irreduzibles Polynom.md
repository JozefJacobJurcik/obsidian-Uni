
###### 1.
Zeigen Sie, dass $p$ im [[Körper]] $K := \mathbb Z_3[x]/p(x)$ nicht irreduzibel ist.

---
Dafür reicht es zu zeigen, dass $p$ mindestens eine **Nullstelle** in $K$ hat. 
Zur besseren Verständlichkeit schreiben wir $p(z)$, da $x$ bereits in der Körpermenge verwendet wird. Eine offensichtliche *Nullstelle* ist $z = x$ denn $p(x) ≡ 0 (\operatorname{mod}\: p(x))$, die andere Nullstelle bekommt man durch [[Polynomdivision]] mit $z − x ∈ K[z]$.

###### 2.
Sei $p(x) = 2x^3 + 3x^2 + 1$ über dem [[Körper]] $\mathbb Z_7$ 
Überprüfen Sie, dass $p$ irreduzibel ist.

---
Wenn es in $\mathbb Z_7$ keine **Nullstellen** gibt, dann ist aufgrund des Grads von 3 das Polynom $p$ irreduzibel.

|$x$|0|1|2|3|4|5|6|
|---|---|---|---|---|---|---|---|
|||||||||
|$2x^3$|0|2|2|5 |2 |5 |5 |
|$3x^2$|0| 3|5 |6 |6 |5 |3 |
|||||||||
|$2x^3 + 3x^2 + 1$|1|6 |1 |5 |2 |4 | 2|

