---
aliases: Ordnung eines Gruppenelementes, Gruppenordnung, ord
--- 
In der Gruppentheorie versteht man unter der *Ordnung eines Gruppenelementes* oder *Elementordnung* eines Elements $g$ einer [Gruppe](Gruppe.md) $( G , ⋅ )$ die kleinste natürliche Zahl $n > 0$ , für die $g^n = e$ gilt, wobei $e$ das [neutrales Element](neutrales%20Element.md) der Gruppe ist. Gibt es keine derartige Zahl, so sagt man, $g$ habe _unendliche Ordnung_. In Formeln:
$${\displaystyle \operatorname {Ord} (g)={\begin{cases}\min\{n\in \mathbb {N} ^{+}:g^{n}=e\}&{\text{falls }}n{\text{ existiert}},\\\infty &{\text{sonst}}.\end{cases}}}$$
Elemente endlicher Ordnung werden auch [Torsionselemente](https://de.wikipedia.org/wiki/Torsion_(Algebra) "Torsion (Algebra)") genannt. Die Ordnung wird mit $\operatorname {ord}(g)$ bezeichnet.

Die Potenz $g^n$ eines Gruppenelementes $g$ ist dabei für natürliche Exponenten $n ≥ 0$ induktiv definiert:

- $g^0 := e$ 
- $g^{k + 1} := g^k ⋅ g$ für alle natürlichen $k ≥ 0$

Die Zahl ${\displaystyle \exp(G):=\operatorname {kgV} \left\{\operatorname {ord} (g)\,|\,g\in G\right\}}$ wird, wenn sie endlich ist, *Gruppenexponent* genannt.

>[!tip] Lemma 
>Ist $G$ endlich, so ist $\operatorname {ord} (a)$ endlich für alle $a ∈ G$.

>[!tip] Lemma 
>Ist $a ∈ G$ mit $\operatorname {ord} (a)$ endlich, so gilt: $a^k = e$ gdw. $\operatorname {ord} (a) \:| \:k$ 

