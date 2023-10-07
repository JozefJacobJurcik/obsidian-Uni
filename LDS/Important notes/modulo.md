---
aliases: mod, Ganzzahlige Division mit Rest
---

Für alle  $a, b ∈ \mathbb Z$ mit $b \ne 0$ gibt es eindeutig bestimmte $q,r ∈ \mathbb Z$ mit $0 ≤ r < |b|$ und $a = q · b + r$ 

*Notation:*  $q = \lfloor\frac{a}{b}\rfloor$ und $r = a \operatorname{mod} b$ 

Für  $a, b ∈ \mathbb Z$ ist *definiert*: 
$b \:|\: a$    gdw.    $a \operatorname{mod} b = 0$    gdw.    $a = q \cdot b$   für ein  $q ∈ \mathbb Z$ 

Jedes $a ∈ \mathbb Z$  mit  $a \:|\: b$ ist ein *Teiler* von $b$. 

Für alle  $a ∈ \mathbb Z$ gilt:
$1 \:|\: a$    und    $a \:|\: a$ 

Auf $\mathbb N$ ist die [[Relation]] | eine [[partielle Ordnung]].

**See also:** [[Restklasse]]

### Modulares Rechnen

>[!tip] Lemma 
>Für alle $a, b, m ∈ \mathbb Z$ und $m ≥ 2$ gilt: 
>- $(a + b)$ mod $m$ = ($a$ mod $m + b$ mod $m$) mod $m$ 
>- $(a · b)$ mod $m$ = ($a$ mod $m · b$ mod $m$) mod $m$

##### Schnelle Exponentiation:
Berechne $a^b\: mod\: m$ wie folgt:
-  ??????????????????????????
- https://en.wikipedia.org/wiki/Modular_exponentiation