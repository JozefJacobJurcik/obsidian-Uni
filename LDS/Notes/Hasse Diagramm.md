---
klausur: 1
---

In der Mathematik ist ein *Hasse-Diagramm* (auch Ordnungs- oder einfach Liniendiagramm genannt) eine bestimmte graphische Darstellung endlicher [[Partielle Ordnung|halbgeordneter]] [[Menge]]n. Solche Diagramme werden nach dem Mathematiker Helmut Hasse benannt.

Das Hasse-Diagramm für eine [[Partielle Ordnung|Halbordnung]] $(M,\leq )$ ergibt sich als Darstellung eines gerichteten Graphen, wobei die Elemente von $M$ die Knoten bilden. Zwei Knoten $a$ und $b$ werden durch eine Kante verbunden, wenn $a < b$ gilt und es keinen Knoten $c$ gibt mit $a < c < b$ . (Hierbei ist $a < b$ als $a\leq b$ und $a \not= b$ zu verstehen.) Die Einschränkung auf solche $a,b$ nennt man *transitive Reduktion der Halbordnung*. Die Richtung der Kante wird dadurch zum Ausdruck gebracht, dass sich der Knoten $b$ oberhalb von $a$ befindet. Solch eine Anordnung lässt sich erreichen, da das Hasse-Diagramm zyklenfrei ist. 

Schleifen bei Reflexivität werden weggelassen. 

###### Beispiele:
Die Teiler einer natürlichen Zahl lassen sich mittels eines Hasse-Diagramms darstellen, da sie bezüglich der Teilbarkeitsrelation eine halbgeordnete Menge, den Teiler[[verband]], bilden. Das Diagramm heißt in diesem Falle auch *Teilerbild*. Das folgende Bild zeigt das Hasse-Diagramm der Teiler von 60.
![[Pasted image 20231020174427.png]]


Die Menge der [[Partition]]en der [[Menge]] {1, 2, 3, 4} mit der Feinheit als Halbordnung.
![[Pasted image 20231020174547.png]]

Die $2^{n}$-elementige [[Potenzmenge]] einer $n$-elementigen [[Menge]] mit der Mengeninklusion lässt sich als *Hasse-Diagramm* darstellen. Dabei bilden die Elemente der Potenzmenge die Knoten und zwei Elemente sind durch eine Kante verbunden, wenn sie in einer Teilmengen[[relation]] stehen. Die durch den untersten Knoten dargestellte leere Menge ist eine Teilmenge aller Elemente; das durch den obersten Knoten dargestellte Universum ist eine Obermenge aller Elemente.

Besonders übersichtlich und verbreitet ist die Anordnung der Mengen, die gleich viele Elemente enthalten, in derselben Ebene des Hasse-Diagramms. Ebenso ist es üblich und empfehlenswert, die Mengen in den Ebenen von links nach rechts lexikographisch zu ordnen.

Ein kleines Beispiel für ein Hasse-Diagramm einer Potenzmenge liefert die Menge $\{ x, y, z \}$
![[Pasted image 20231020174828.png]]
