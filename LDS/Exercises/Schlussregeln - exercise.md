
###### 1.
Wir betrachten die Logischen Schlussregeln, erweitert um die [[Schlussregeln|Schlussregel]] $$\frac{Γ ⇒ A → B} {Γ ⇒ ¬A → ¬B} (BUG)$$ Zeigen Sie, dass diese Schlussregel die Korrektheit nicht erfüllt.

---
Hierdurch lässt sich etwa herleiten: 
1. $A → B ⇒ A → B$ (Axiom) 
2. $A → B ⇒ ¬A → ¬B$ (BUG) aus 1 
Nun erfüllt die Variablenbewertung $α$ mit $α(A) = 0, α(B) = 1$ die Prämisse von 2 $(A → B)$, aber nicht die Konklusion von 2 $(¬A → ¬B)$. Also ist diese Regel *nicht korrekt*.

###### 2.
Zeigen Sie, dass die Logischen [[Schlussregeln]] erweitert um folgende Regel immer noch korrekt sind $$\frac {Γ ⇒ ∆, A, B A, B, Γ ⇒ ∆} {Γ ⇒ ∆, A \operatorname {xor} B} (XOR-R)$$
Dabei bezeichnet xor wie üblich die [[Funktion]]:

|x|y|x xor y|
|---|---|---|
||||
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|

---
Durch Analyse der Belegungen, wie in der Vorlesung, oder durch Betrachtung folgender Teilfolge an Sequenzen 

1. $Γ ⇒ ∆, A, B$ 
2. $A, B, Γ ⇒ ∆$ 
3. $Γ ⇒ ∆, A ∨ B$ (∨-R) aus 1 
4. $B, Γ ⇒ ∆, ¬A$ (¬-R) aus 2 
5. $Γ ⇒ ∆, ¬A, ¬B$ (¬-R) aus 4 
6. $Γ ⇒ ∆, ¬A ∨ ¬B$ (∨-R) aus 5 
7. $Γ ⇒ ∆,(¬A ∨ ¬B) ∧ (A ∨ B)$ (∧-R) aus 3,6 

Man beachte hierbei, dass die ersten beiden Zeilen den Voraussetzungen der XOR-R Regel entsprechen. Da $(¬A ∨ ¬B) ∧ (A ∨ B)$ die gleiche Wertetabelle wie xor hat, diese Funktionen also äquivalent sind, kann man jeden Beweis, der die XOR-R-Regel verwendet also umschreiben zu einem, der nur die Normalen Logikregeln verwendet und eine äquivalente Formel erzeugt. 

Es muss das Hinzufügen der Regel XOR-R also *die Korrektheit erhalten*.