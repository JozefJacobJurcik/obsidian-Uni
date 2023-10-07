---
aliases: größte gemeinsame Teiler
tags: math
---
### Berechnung

**Alternativ:** [[Euklidische Algorithmus]]

Man kann den *ggT* über die [Primfaktorzerlegung](https://de.wikipedia.org/wiki/Primfaktorzerlegung "Primfaktorzerlegung") der beiden gegebenen Zahlen bestimmen. Beispiel:

- ${\displaystyle 3528=2^{\color {Red}3}\cdot 3^{\color {Red}2}\cdot 5^{\color {Red}0}\cdot 7^{\color {Red}2}}$ 
- ${\displaystyle 3780=2^{\color {OliveGreen}2}\cdot 3^{\color {OliveGreen}3}\cdot 5^{\color {OliveGreen}1}\cdot 7^{\color {OliveGreen}1}}$ 

Für den *ggT* nimmt man die Primfaktoren, die in beiden Zerlegungen vorkommen, und als zugehörigen Exponenten den jeweils kleineren der Ausgangsexponenten:
$${\displaystyle \operatorname {ggT} (3528,3780)=2^{\color {OliveGreen}2}\cdot 3^{\color {Red}2}\cdot 5^{\color {Red}0}\cdot 7^{\color {OliveGreen}1}=252}$$
### Allgemein

Der *ggT* ist die größte natürliche Zahl, durch die sich zwei ganze Zahlen ohne Rest teilen lassen. Der *ggT*  zweier ganzer Zahlen $a$ und $b$ ist eine ganze Zahl $m$ mit der Eigenschaft, dass sie Teiler sowohl von $a$ als auch von $b$ ist und dass jede ganze Zahl, die ebenfalls die Zahlen $a$ und $b$ teilt, auch Teiler von $m$ ist.

Für $a, b ∈ \mathbb Z$ definiere: $$\operatorname {ggT}(a, b) := \operatorname{max} \{ k ∈ N \:;\: k \:|\: a\: \operatorname{und} \:k \:| \:b \}$$
>[!info] Theorem (Lemma von Bézout)
> Für  $a, b ∈ \mathbb N$ gibt es $s,t ∈ \mathbb Z$, so dass gilt: $\operatorname{ggT}(a, b) = s · a + t · b$

###### Beispiel:
- 12 ist durch die folgenden Zahlen ohne Rest teilbar: 1, 2, 3, 4, 6, 12.
- 18 hat diese Teiler: 1, 2, 3, 6, 9, 18.
- Die gemeinsamen Teiler von 12 und 18 sind also 1, 2, 3, 6 und der größte von diesen ist 6 – in Zeichen:
$$\operatorname {ggT} (12,18)=6$$
