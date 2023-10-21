---
aliases: lineare Ordnung
klausur: 1
---

Relation $R$ auf A die [reflexiv](Reflexivität.md), [transitiv](Transitivität.md) und [antisymmetrisch](Antisymmetrie.md) ist und und für alle 
$a, b ∈ A$ gilt a $R$ b oder b $R$ a.

Eine [[partielle Ordnung]] $\preceq$ auf $A$ ist *lineare (oder totale) Ordnung*, wenn gilt: 
- für alle  $a, b ∈ A$ ist $a \preceq b$ oder $b \preceq a$.
###### Beispiel:
- das übliche $≤$ auf $\mathbb R$ 

### Lineare Erweiterung

>[!info] Theorem
> Jede endliche [[Partielle Ordnung]] hat eine *lineare Erweiterung*.

Ordnung $\leq$ ist *lineare Erweiterung* von $\preceq$, wenn gilt: 

- $\leq$ ist *lineare Ordnung* auf $A$ 
- für alle  $a, b ∈ A$ gilt: ist $a \preceq b$, dann auch $a \leq b$ 

###### Beispiel:
$\leq$ ist lineare Erweiterung von | auf $\mathbb N$
( | ist die Teilbarkeitsrelation )

**AI explanation:**  Die Teilbarkeitsrelation | erfüllt diese Eigenschaften bereits (Reflexivität, Antisymmetrie, Transitivität), aber die Relation ≤ fügt auch Elemente hinzu, die nicht durch Teilbarkeit miteinander verbunden sind. Zum Beispiel gilt 2 ≤ 4 und 4 ≤ 6, aber 2 und 6 sind nicht durch Teilbarkeit miteinander verbunden.

Ein einfaches Beispiel für eine [[Partielle Ordnung|Halbordnung]] ist die Menge {a, b, c} mit der Relation “ist ein Teiler von”. Die ursprüngliche Halbordnung enthält nur die Elemente a, b und c sowie die Relation “ist ein Teiler von”. Eine *lineare Erweiterung* dieser *Halbordnung* ist eine *totale Ordnung*, die alle Elemente in einer bestimmten Reihenfolge anordnet. Es gibt sechs mögliche *lineare Erweiterungen* dieser Halbordnung:

1. a ≤ b ≤ c
2. a ≤ c ≤ b
3. b ≤ a ≤ c
4. b ≤ c ≤ a
5. c ≤ a ≤ b
6. c ≤ b ≤ a


