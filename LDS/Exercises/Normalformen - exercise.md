See: [[KNF]] , [[DNF]] and [[Disjunktive und Konjunktive Normalform]]

###### 1.
Berechnen Sie für folgende Formeln eine äquivalente Formel in KNF durch Umformen. 
1.  $(x ∧ y) ∨ (¬y ∧ z)$

$((x ∧ y) ∨ ¬y) ∧ ((x ∧ y) ∨ z)$ [[Distributivgesetz]]
$(x ∨ ¬y) ∧ (y ∨ ¬y) ∧ (x ∨ z) ∧ (y ∨ z)$ [[Distributivgesetz]]
(x ∨ ¬y) ∧ (x ∨ z) ∧ (y ∨ z) [[Tautologie]]

2. $¬((x → y) ∧ z)$

$¬(x → y) ∨ ¬z$ [[Distributivgesetz]]
$¬(¬x ∨ y) ∨ ¬z$ Implikation auflösen [[Negations-Normalform|NNF]]
$(x ∧ ¬y) ∨ ¬z$ [[De Morganschen Gesetze]]
$(x ∨ ¬z) ∧ (¬y ∨ ¬z)$ [[Distributivgesetz]]

###### 2. 
