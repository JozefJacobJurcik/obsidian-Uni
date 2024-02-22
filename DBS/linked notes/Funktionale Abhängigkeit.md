---
aliases: funktionalen Abhängigkeiten
---

Seien $𝑋, 𝑌$ Attributmengen des Relationenschemas $𝑅$ , d.h. $𝑋, 𝑌 ⊆ 𝑅$  

$Y$ ist von $X$ *funktional abhängig* (oder $X$ *bestimmt* $Y$ *funktional*), 
	d.h. $𝑋 → 𝑌 ⇔$ für alle möglichen Ausprägungen von $R$ gilt: 
		Zu jedem Wert in $X$ existiert genau ein Wert in $Y$ 

**Formal:** 
$$𝑋 → 𝑌 ⇔ ∀𝑟_1, 𝑟_2 ∈ 𝑅: 𝑟_1. 𝑋 = 𝑟_2. 𝑋 ⇒ 𝑟_1. 𝑌 = 𝑟_2. 𝑌$$
###### Beispiel: 
Passnummer → Name

Suppose one is designing a system to track vehicles and the capacity of their engines. Each vehicle has a unique vehicle identification number (VIN). One would write VIN → EngineCapacity because it would be inappropriate for a vehicle's engine to have more than one capacity. (Assuming, in this case, that vehicles only have one engine.) On the other hand, EngineCapacity → VIN is incorrect because there could be many vehicles with the same engine capacity. 


![[Triviale funktionale Abhängigkeit]]

![[Voll funktionale Abhängigkeit]]

![[Partiell funktionale Abhängigkeit]]

![[Transitive funktionale Abhängigkeit]]
