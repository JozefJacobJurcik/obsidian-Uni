---
aliases: Relationenschema, relational model
---
### Geordnetes Relationenschema: 
-  k-Tupel aus Domains (Attribute) 
- Attribute werden anhand ihrer Position im Tupel referenziert 
- Attribute können auch zusätzlich einen Attributnamen haben 
- $𝑅 = (𝐴_1: 𝐷_1, … 𝐴_𝑘: 𝐷_𝑘) \rightarrow$ Relationenschema 

- **Relation:** Ausprägung eines Relationenschemas
- **Datenbankschema:** Menge von Relationschemata
- **Datenbank:** Menge von Relationen (Ausprägungen)

![[Pasted image 20240216154537.png]]

### Grundoperationen
^4d4306
##### Notation: 
- $R$ und $S$ – Relationen 
- $t$ – Tupel aus einer Relation 
- $A$ und $B$ – Attribute 
- $F$ – Formel 
- $A_i$ – Attribute beim Namen $i$ referenziert

 **[[Menge#^8199b2|Vereinigung]] :** $R \cup S = \{t \:|\: t \in R \:\operatorname{oder}\: t \in S\}$ 
 
 ![[Pasted image 20240216201717.png]]
 
 **[[Menge#^8199b2|Differenz]]:** $𝑅 − 𝑆 = \{𝑡 \:|\: 𝑡 ∈ 𝑅 \:\operatorname{und}\: 𝑡 ∉ 𝑆\}$ 
 
![[Pasted image 20240216201739.png]]

 **[[Kartesisches Produkt]]:** $𝑅 × 𝑆 = \{(𝑎_1, … , 𝑎_𝑟, 𝑎_{𝑟+1}, … 𝑎_{𝑟+𝑠}) | (𝑎_1, … , 𝑎_𝑟) ∈ 𝑅 \:\operatorname{und}\: (𝑎_{𝑟+1}, … 𝑎_{𝑟+𝑠}) ∈ 𝑆\}$
 
 ![[Pasted image 20240216201802.png]]
 
 
**[[Selektion]]**: $𝜎_𝐹 (𝑅) = \{𝑡 | 𝑡 ∈ 𝑅 ∧ 𝑡 \:\operatorname{erfuellt}\: 𝐹\}$ 
	$F$ besteht aus Konstanten, Attributen, Vergleichsoperatoren und Boolschen Operatoren 
	-> *„Selektiere“ Zeilen nach einer Bedingung* 
	
![[Pasted image 20240216201833.png]]


**[[Projektion]]:** $\Pi 𝑎_1, … , 𝑎_𝑚 (𝑅) = \{𝑡 [𝑎_1, … , 𝑎_𝑚] | 𝑡 ∈ 𝑅\}$
	$𝑡 [𝑎_1, … , 𝑎_𝑚]$ bezeichnet ein Tupel aus $R$ was nur die Attributwerte $a_1 – a_m$ enthält 
	-> *„Projiziere“ nur bestimmte Spalten*

![[Pasted image 20240216201903.png]]

**[[Menge#^8199b2|Durchschnitt]]:** $𝑅 ∩ 𝑆 = \{𝑡 |𝑡 ∈ 𝑅 \:\operatorname{und}\: 𝑡 ∈ 𝑆\}$ 

![[Pasted image 20240216201932.png]]

**Theta-Join:** $𝑅 \: \underset{𝐴 𝜃 𝐵}{⋈} \: 𝑆 = 𝜎_{𝐴𝜃𝐵} (𝑅 × 𝑆) (𝜃 ∈ \{=, < ,≤, ≥, >, ≠\})$ 

![[Pasted image 20240216202006.png]]

**Equi-Join:** Gleich mit dem Theta-Join bis auf: $𝜃 ∈ \{=\}$
	Gleichnamige Attribute werden behalten (gibt es dann doppelt) 

 **Natural-Join:** $𝑅 ⋈ 𝑆$, Equi-Join bzgl. Aller gleichnamigen Attribute in $R$ und $S$ 
	 Gleichnamige Attribute werden entfernt (existieren dann nur einmal im Ergebnis) 

 **Quotient:** $𝑅 ÷ 𝑆 = \{𝑡 \:|\: 𝑡 ∈ \Pi_{𝑅−𝑆} (𝑅) ∧ \{𝑡\} × 𝑆 ⊆ 𝑅\}$
	 Ergebnis enthält alle linken Hälften von Tupeln aus $R$, die mit allen rechten Hälften von $S$ kombiniert in $R$ auftreten

![[Pasted image 20240216202109.png]]

