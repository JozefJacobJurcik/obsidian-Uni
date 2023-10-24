See: [[Schlussregeln]] 
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
Durch Analyse der Belegungen, wie in der Vorlesung, oder durch Betrachtung folgender Teilfolge an Sequenzen **(viel leichter mit einem Baum herzuleiten)**

1. $Γ ⇒ ∆, A, B$ 
2. $A, B, Γ ⇒ ∆$ 
3. $Γ ⇒ ∆, A ∨ B$ (∨-R) aus 1 
4. $B, Γ ⇒ ∆, ¬A$ (¬-R) aus 2 
5. $Γ ⇒ ∆, ¬A, ¬B$ (¬-R) aus 4 
6. $Γ ⇒ ∆, ¬A ∨ ¬B$ (∨-R) aus 5 
7. $Γ ⇒ ∆,(¬A ∨ ¬B) ∧ (A ∨ B)$ (∧-R) aus 3,6 

Man beachte hierbei, dass die ersten beiden Zeilen den Voraussetzungen der XOR-R Regel entsprechen. Da $(¬A ∨ ¬B) ∧ (A ∨ B)$ die gleiche Wertetabelle wie xor hat, diese Funktionen also äquivalent sind, kann man jeden Beweis, der die XOR-R-Regel verwendet also umschreiben zu einem, der nur die Normalen Logikregeln verwendet und eine äquivalente Formel erzeugt. 

Es muss das Hinzufügen der Regel XOR-R also *die Korrektheit erhalten*.

###### 3. 
Zeigen Sie, dass im Sequenzenkalkül die Sequenz $(x ∧ y) ∧ z ⇒ x ∧ (y ∧ z)$ herleitbar ist; geben Sie dazu eine Herleitung im Sequenzenkalkül an.

---
See: [[Schlussregeln]] 
**(viel leichter mit einem Baum herzuleiten)**

1. $(x ∧ y), z ⇒ z$ ([[Axiom]]) 
2. $(x ∧ y) ∧ z ⇒ z$ (∧-L) aus 1 
3. $x, y, z ⇒ y$ (Axiom) 
4. $(x ∧ y), z ⇒ y$ (∧-L) aus 3 
5. $(x ∧ y) ∧ z ⇒ y$ (∧-L) aus 4 
6. $(x ∧ y), z ⇒ (y ∧ z)$ (∧-R) aus 5,2 
7. $x, y, z ⇒ x$ (Axiom) 
8. $(x ∧ y), z ⇒ x$ (∧-L) aus 7 
9. $(x ∧ y) ∧ z ⇒ x$ (∧-L) aus 8 
10. $(x ∧ y) ∧ z ⇒ x ∧ (y ∧ z)$ (∧-R) aus 9,6

###### 4.
Zeigen Sie, dass im Sequenzenkalkül die Sequenz $¬(x → y) ∨ (y ∧ z) ⇒ (x ∨ z)$ herleitbar ist; geben Sie dazu eine Herleitung im Sequenzenkalkül an.

$${\Huge \frac{\frac{y, z ⇒ x, z}{y ∧ z ⇒ x, z}{\small(∧-L)} \quad \frac{\frac{ x ⇒ x, z, y}{⇒  x, z, x → y}(→-R)}{¬(x → y) ⇒ x, z}{\small(∨-L)}}{\frac{¬(x → y) ∨ (y ∧ z) ⇒ x, z}{¬(x → y) ∨ (y ∧ z) ⇒ (x ∨ z)}{\small(∨-R)}}}$$
###### 5.
Zeigen Sie, dass $¬∃x∀y(P(x, y)) ≡ ∀x∃y(¬P(x, y))$ gilt, indem Sie die folgenden beiden Sequenzen im Sequenzenkalkül der Prädikatenlogik herleiten: 

- $(¬∃x∀y(P(x, y))) ⇒ (∀x∃y(¬P(x, y)))$ 
- $(∀x∃y(¬P(x, y))) ⇒ (¬∃x∀y(P(x, y)))$ 

Benennen Sie die angewandten Schlussregeln und die Sequenzen, auf welche diese jeweils angewendet werden, explizit! Achten Sie außerdem darauf, dass die Eigenvariablen-Bedingung bei der Anwendung von Quantor-Regeln nicht verletzt wird.

---

