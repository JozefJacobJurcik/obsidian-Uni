---
aliases: Zerlegung, Klasseneinteilung
---

In der Mengenlehre ist eine *Partition* (auch Zerlegung oder Klasseneinteilung) einer [[Menge]] $M$ eine Menge $P$, deren Elemente nichtleere Teilmengen von $M$ sind, sodass jedes Element von $M$ in genau einem Element von $P$ enthalten ist. 

Anders gesagt: Eine *Partition* einer Menge ist eine Zerlegung dieser Menge in nichtleere paarweise [[Disjunktheit|disjunkte]] Teilmengen. Insbesondere ist jede Partition einer Menge auch eine Überdeckung der Menge. 

$Part(M)$ ist die [[Menge]] aller Partitionen von $M$.
###### Beispiele: 

Das Mengensystem (= die Mengenfamilie) 
$P=\left\{\left\{3,5\right\},\left\{2,4,6\right\},\left\{7,8,9\right\}\right\}$ ist eine Partition der Menge 
$M=\left\{2,3,4,5,6,7,8,9\right\}$ . Die Elemente von $P$ sind dabei paarweise [[Disjunktheit|disjunkte]] Teilmengen von $M$.
$P$ ist jedoch keine Partition der Menge $N=\left\{1,2,3,4,5,6,7,8,9\right\}$ , weil 1 zwar in $N$ , aber in keinem Element von $P$ enthalten ist.

Die Mengenfamilie { { 1 , 2 } , { 2 , 3 } }  ist keine Partition irgendeiner Menge, weil { 1 , 2 } und { 2 , 3 } mit 2 ein gemeinsames Element enthalten, also _nicht_ [[Disjunktheit|disjunkt]] sind.

Die Menge { 1 , 2 , 3 } hat genau 5 Partitionen:

- { { 1 , 2 , 3 } }
- { { 1 } , { 2 , 3 } }
- { { 2 } , { 3 , 1 } } 
- { { 3 } , { 1 , 2 } } 
- { { 1 } , { 2 } , { 3 } } 

Die einzige Partition der leeren Menge ist die leere Menge.

Jede einelementige Menge { x } hat genau eine Partition, nämlich {{ x }} .

Jede nichtleere Menge $M$ hat genau eine einelementige Partition { $M$ } , man nennt sie die „*triviale Partition*“.