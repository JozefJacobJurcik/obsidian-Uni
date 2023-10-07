---
aliases: kleinste gemeinsame Vielfache
tags: math
---

### Berechnung

Man kann das *kgV* über die [Primfaktorzerlegung](https://de.wikipedia.org/wiki/Primfaktorzerlegung "Primfaktorzerlegung") der beiden gegebenen Zahlen bestimmen. Beispiel:

$3528=2^{\color {Red}3}\cdot 3^{\color {Red}2}\cdot 7^{\color {Red}2}$ 
$3780=2^{\color {OliveGreen}2}\cdot 3^{\color {OliveGreen}3}\cdot 5^{\color {OliveGreen}1}\cdot 7^{\color {OliveGreen}1}$

Für das *kgV* nimmt man die Primfaktoren, die in mindestens einer der beiden Zerlegungen vorkommen, und als zugehörigen Exponenten den jeweils größeren der Ausgangsexponenten:
$$\operatorname {kgV}(3528,3780)=2^{{\color {Red}3}}\cdot 3^{{\color {OliveGreen}3}}\cdot 5^{{\color {OliveGreen}1}}\cdot 7^{{\color {Red}2}}=52.920$$

### Allgemein

Das *kleinste gemeinsame Vielfache* zweier ganzer Zahlen $m$ und $n$ ist die kleinste positive natürliche Zahl, die sowohl Vielfaches von $m$ als auch Vielfaches von $n$ ist. Zusätzlich wird für den Fall $m = 0$ oder $n = 0$ das *kgV* definiert als ${\displaystyle \operatorname {kgV} (m,\,n):=0}$

Für $a, b ∈ \mathbb Z$ definiere: $$\operatorname {kgV}(a, b) := \operatorname{min} \{ k ∈ N \:;\: a \:|\: k\: \operatorname{und} \:b \:| \:k \}$$
