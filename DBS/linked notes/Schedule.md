---

---

Ein *Schedule* $𝑆$ ist eine Folge von Aktionen für eine Menge $𝑇 = \{𝑇_1, … 𝑇_𝑛\}$ von [[Transaktion]]en. 

$𝑆$ entsteht durch Mischen der Aktionen der TA $𝑇_𝑖$ 
	-> Reihenfolge der Aktionen innerhalb der jeweiligen TA wird beibehalten 

#### Serieller Schedule: 
Ein Schedule ist seriell, wenn die einzelnen Transaktionen $𝑇 = \{𝑇_1, … 𝑇_𝑛\}$ nicht verzahnt werden, sondern blockweise hintereinander ausgeführt werden 
	$\Rightarrow$ [[ACID-Prinzip|Isolation]] ist gegeben, aber *langsam*, da nicht parallel

#### Serialisierbarer Schedule:
Schedule $𝑆$ von $𝑇 = \{𝑇_1, … 𝑇_𝑛\}$ ist serialisierbar, wenn er die gleiche Wirkung hat wie ein beliebiger serieller Schedule von $𝑇 = \{𝑇_1, … 𝑇_𝑛\}$

$\Rightarrow$ Auch hier ist die Isolation nicht verletzt 
$\Rightarrow$ Bessere Performanz als bei seriellen Schedules

$\Rightarrow$ Nur serialisierbare Schedules dürfen zugelassen werden

### Abhängigkeiten in Schedules
$\hookrightarrow$ unterschiedliche Transkationen, gleiches Objekt.

Sei $𝑆$ ein Schedule:

**Schreib-Lese Abhängigkeit** von $𝑇_𝑖 → 𝑇_𝑗$ : 
	Es gibt ein $𝑥$, so dass in $𝑆$  $w_i(𝑥)$  vor  $r_j(𝑥)$  kommt  $\rightarrow wr_{i,j} (𝑥)$ 
	
**Lese-Schreib Abhängigkeit** von $𝑇_𝑖 → 𝑇_𝑗$ : 
	Es gibt ein $𝑥$, so dass in $𝑆$  $𝑟_𝑖(𝑥)$  vor  $𝑤_𝑗 (𝑥)$  kommt  $\rightarrow rw_{i,j} (𝑥)$ 

**Schreib-Schreib Abhängigkeit** von $𝑇_𝑖 → 𝑇_𝑗$ : 
	  Es gibt ein $𝑥$, so dass in $𝑆$  $𝑤_𝑖(𝑥)$  vor  $𝑤_𝑗 (𝑥)$  kommt  $\rightarrow ww_{i,j} (𝑥)$

### Serialisierungsgraph

Ein Serialisierungsgraph $𝐺$ ist ein gerichteter Graph $𝐺 = (𝑉, 𝐸)$ : 
- Mit Knoten $V = \{𝑇_1, … 𝑇_𝑛\}$ (beteiligten Transaktionen) 
- Mit Kanten $𝐸$ = Abhängigkeiten $(𝑇_𝑖 → 𝑇_𝑗)$ zwischen den [[Transaktion]]en

Wenn der Graph **zyklenfrei** ist $\rightarrow$ *serialisierbar*
Wenn der Graph **Zyklen enthält** $\rightarrow$ *nicht serialisierbar*

###### Beispiel
![[Pasted image 20240219024746.png]]

