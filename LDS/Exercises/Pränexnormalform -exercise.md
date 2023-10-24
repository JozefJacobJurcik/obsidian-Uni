
###### 1.
Bringen Sie die folgende Formel in Pränex-Normalform: $$(∀x(S(y, x)) ∧ ∃x(T(y, x))) → U(y)$$

---
$¬(∀x(S(y, x)) ∧ ∃x(T(y, x))) ∨ U(y)$ 
$¬∀x(S(y, x)) ∨ ¬∃x(T(y, x)) ∨ U(y)$ 
$∃x(¬S(y, x)) ∨ ∀x(¬T(y, x)) ∨ U(y)$ 
$∃x(¬S(y, x)) ∨ ∀z(¬T(y, z)) ∨ U(y)$ 
$∃x∀z(¬S(y, x) ∨ ¬T(y, z) ∨ U(y))$

###### 2.
Bringen Sie die Formel $ψ = ∃x(P(x, f(x)))∨∃x∀y((R(y) → R(x))∧¬(∀z(P(f(z), g(x, y)))))$ in Pränex-Normalform. Geben Sie alle Zwischenschritte explizit an.

---
![[Pasted image 20231024181825.png]]
