---
modul: "LDS"
---

Die *transitive Hülle* $R^{+}$ einer zweistelligen [[Relation]] $R$ auf einer [[Menge]] $M$ ist gegeben durch:
$$x\ R^{+}\ y:\Leftrightarrow \exists n\geq 0\ \exists x_{1},\dots ,x_{n}\in M:x\,R\,x_{1}\,R\,x_{2}\,R\dots \,R\,x_{n}\,R\,y$$
Die [[Reflexiv-transitive Hülle]] $R^{{*}}$ ergibt sich dann durch
$$x\ R^{*}\ y:\Leftrightarrow x=y\lor x\ R^{+}\ y$$

Die **transitive Hülle** bzw. der **transitive Abschluss** einer (zweistelligen) [[Relation]] ist eine Erweiterung dieser Relation, die – vereinfacht gesagt – zusätzlich alle indirekt erreichbaren Paare enthält (und damit [[Transitivität|transitiv]] ist). Die transitive Hülle kann mit dem [[Warshall-Algorithmus]] berechnet werden.

###### Beispiel:
Gegeben sei eine Relation „Direkter-Vorgesetzter“ mit folgenden Beziehungen:

- C ist direkter Vorgesetzter von D und E
- B ist direkter Vorgesetzter von C
- A ist direkter Vorgesetzter von B

Die transitive Hülle dieser Relation enthält nun zusätzlich auch die indirekten Vorgesetzten:

- A ist Vorgesetzter von B, C, D, E
- B ist Vorgesetzter von C, D, E
- C ist Vorgesetzter von D und E

![[Pasted image 20231006135947.png|300]]
> Illustration des Beispiels: durchgezogene Pfeile zeigen direkte Beziehungen an, gestrichelte Pfeile die in der transitiven Hülle dazu kommenden Relationen


### Vorlesung

Relation $R$ auf A 
	$\to$ transitive Hülle $R^+$

$a \: R^+ \: b$ gdw. es gibt $x_1, . . . , x_k ∈ A$ mit 
- $a\: R\: x_1$ 
- $x_i \: R \: x_{i+1}$ für alle $i < k$ 
- $x_k \:R \:b$ 

**Eigenschaft:** $R^+$ ist transitiv, und $R^+ ⊇ R$. 

Ist $R^′ ⊇ R$ *transitiv*, dann ist $R^′ ⊇ R^+$. 

**Alternative Definition:** 
- $R^+$ ist die *minimale transitive Relation* $R^′ ⊇ R$

