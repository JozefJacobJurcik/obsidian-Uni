---

---

**Relationale Algebra** ist eine prozedurale Sprache: **wie** *wird etwas berechnet* 

**Relationenkalkül** ist deklarative Sprache: **was** *wird berechnet* 

**Kalkül:** logischer Formalismus zur Ableitung von Ergebnissen 

###### Aufbau von jedem Kalkül: 
1. *Syntax*: Wie sind die Ausdrücke aufgebaut? 
2. *Semantik*: Was bedeuten die Ausdrücke? 



### Tupelkalkül

##### Formeln
- Es dreht sich alles um Tupel 
- $t$ ist eine Tupelvariable bzgl. Schema $S$ = Schema($t$) 

- Kleinste Bestandteile einer Formel im Tupelkalkül sind die *Atome*: 
	- $𝑅 (𝑡) , \:𝑡. 𝐴𝜃𝑠. 𝐵 \:,\: 𝑡. 𝐴𝜃𝑐 \: (𝜃 ∈ \{<, ≤, ≥, >, = , ≠\})$ (wobei $t$ und $s$ Tupelvariablen, $A$ und $B$ Relationen und $c$ Konstanten sind)

- Formeln im Tupelkalkül sind Induktiv definiert: 
	- Jedes Atom ist eine Formel 
	- $𝜑_1$ und $𝜑_2$ Formeln $𝜑_1 ∧ 𝜑_2 \:,\: 𝜑_1 ∨ 𝜑_2, ¬𝜑_1$ auch Formeln 
	- $𝜑$ Formel und $𝑡$ frei in $𝜑 ⇒ ∃𝑡𝜑$ und $∀𝑡𝜑$ auch Formel 

##### Ausdrücke
Es gibt zwei verschiedene Alternativen Ausdrücke zu formulieren 

1. $\{𝑡 | 𝜑(𝑡)\}$, wobei $t$ einzige freie Tupelvariable in $𝜑$ ist. 
2. $\{[𝑡_1.𝐴_1, … , 𝑡_𝑛.𝐴_𝑛]\: |\: 𝜑(𝑡_1, … , 𝑡_𝑛)\},$ wobei $𝑡1, … , 𝑡𝑛$ die einzigen freie Tupelvariablen in 𝜑 sind 

=> Die Schemata von $𝑡$ und $𝑡_1, … , 𝑡_𝑛$ müssen explizit angegeben warden 

*Bsp.:* 
Schema ($𝑡$) = Schema (𝐴𝑛𝑔𝑒𝑠𝑡𝑒𝑙𝑙𝑡𝑒𝑟) ; { \[t.Name] | t ∈ 𝐴𝑛𝑔𝑒𝑠𝑡𝑒𝑙𝑙𝑡𝑒𝑟} -> Namen aller Angestellten zurück

### Bereichskalkül

##### Formeln
- Es dreht sich um die einzelnen Bereiche von Relationen (Domänen) 
- Bereichsvariablen $𝑥_1: 𝐷_1, … , 𝑥_𝑘: 𝐷_𝑘$ für einzelne Attribute 

- Kleinste Bestandteile sind wieder die *Atome*: 
	- $𝑅( 𝑥_1, … , 𝑥_𝑘) , 𝑥𝜃𝑦 , (𝜃 ∈ \{<, ≤, ≥, >, = , ≠ \}), 𝑥, 𝑦$ sind Bereichsvariablen/Konstanten 

- Induktive Definition analog zum Tupelkalkül

##### Ausdrücke
- Ausdrücke: 
	- $\{𝑥_1, … , 𝑥_𝑘 \:|\:𝜑(𝑥1, … , 𝑥𝑘)\}$, wobei $𝑥_1, … , 𝑥_𝑘$ die einzig freien Variablen in $𝜑$ ist 

- Syntaxerweiterung: 
	- Ein Unterstrich als Platzhalter genutzt werden, falls ein Attribut einer Relation nicht benötigt wird

Bsp.: 
$\{ 𝑙𝑎𝑛𝑑 \:|\: ∃ 𝑛 𝑟, 𝑠𝑡: \operatorname{Filiale} (𝑛𝑟, 𝑠𝑡, 𝑙𝑎𝑛𝑑 )\} = \{ 𝑙𝑎𝑛𝑑 | \operatorname{Filiale} (\_, \_ , 𝑙𝑎𝑛𝑑) \}$ -> alle Länder wo Filialen sind