---
klausur: 2
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
	- $𝑅 (𝑡) , \:𝑡.𝐴\:𝜃\:𝑠. 𝐵 \:,\: 𝑡. 𝐴𝜃𝑐 \: (𝜃 ∈ \{<, ≤, ≥, >, = , ≠\})$ (wobei $t$ und $s$ Tupelvariablen, $A$ und $B$ Relationen und $c$ Konstanten sind)

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
(more in Tutorium 6)

###### How i understand it:
I would learn [[SQL]] first.

**Start with**:
Schema(`name of an attribute in this case"r1"`) = Schema(`name of the relation 1 in this case "R1"`)
Schema(`name of an attribute - "r2"` ) = Schema(`name of the relation 2 - "R2"`)

This is analogue to the FROM statement in SQL so you have to name *every* relation from which you are SELECT-ing from and give a name to an attribute of it. Lets say you need to select the "Name" from `r1` and "Number" from `r2` - then:

Schema(`r1`) = Schema(`R1`)
Schema(`r2` ) = Schema(`R2`)
{ \[`r1.Name,r2.Number`] | `R1(r1)` $\wedge$ `R2(r2)` $\wedge$ `extra` ... }

in the \[ ] goes your SELECT and then you have to specify that `r1` is an attribute of `R1` AND `r2` is from `R2` you can do it like this `R1(r1)` or (`r1` $\in$ `R1`) - I think they are interchangeable but idk.

For every variable you need to use that is not in `R1` or in `R2` (That you declared in the "Schema") you have to add to the `extra` something like this:

... $\wedge$ ($\exists$ `r3` $\in$ `R3` : `r1.Name = r3.Name` ) $\wedge$ ...

in this example the names must match, but it can be any logic with a boolean type after the ":" . If you need more variables from more relations here is an example from 6.1.b :

𝑆𝑐ℎ𝑒𝑚𝑎 (𝑣𝑒𝑟) = 𝑆𝑐ℎ𝑒𝑚𝑎 (𝑉𝑒𝑟𝑘𝑎𝑢𝑓) 
{\[𝑣𝑒𝑟. 𝑁𝑢𝑚𝑚𝑒𝑟, 𝑣𝑒𝑟. 𝐷𝑎𝑡𝑢𝑚] | 𝑣𝑒𝑟 ∈ Verkauf ∧ ==(== ∃𝑎𝑏 ∈ Abteilung, 𝑎𝑟𝑡 ∈ Artikel, 𝑙 ∈ Lieferant ==)== *(* 𝑣𝑒𝑟. 𝐴𝑏𝑡𝑒𝑖𝑙𝑢𝑛𝑔 = 𝑎𝑏. 𝑁𝑢𝑚𝑚𝑒𝑟 ∧ 𝑣𝑒𝑟. 𝐴𝑟𝑡𝑖𝑘𝑒𝑙 = 𝑎𝑟𝑡. 𝑁𝑢𝑚𝑚𝑒𝑟 ∧ 𝑎𝑟𝑡. 𝐿𝑖𝑒𝑓𝑒𝑟𝑎𝑛𝑡 = 𝑙. 𝑁𝑢𝑚𝑚𝑒𝑟 ∧ 𝑎𝑏. 𝑆𝑡𝑜𝑐𝑘 = 3 ∧ (𝑙.Land = ′Italien′ ∨ 𝑙.Land = ′Frankreich′)*)*}

Basically you put all of the $\exists$ in one ==( )== and the logic goes into a *( )* right after it. As far as i know you use either ":" or "( )" but not both.

If I understand it correctly... and you need to alter the relation - you need more or less columns than you started with you have to define it in the "Schema" part with "dom" -> refer to  [[tutorium_06.pdf#page=26|tutorium_06, page 26]]

This is how I understand it so take it with a grain of salt.

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

###### How i understand it:
Again, I  would learn [[SQL]] first.

Bereichskalkül goes something like this:

{ `1st part` | `2nd part` : `3rd part`}

---
`1st part` you have to write aliases for the attributes you want to SELECT. Basically if you wanted to do something like this in SQL: `SELECT Name AS na , Department_Number AS nr` you would write `na,nr` into the `1st part` in Bereichskalkül. 

I will skip the `2nd part` and come back to it later.

---
In `3rd part` you have to specify where from are you taking the attributes in the `1st part` . If you needed the  "Name" FROM the relation "Employee" that looked like this: 

Employee(Personal_Nr *(primary key)*, Name, Department *(foreign key)*, Salary)

You would write it like this: 

{ `na` | Employee( \_ , `na` , \_ , \_  )  }

The position in the relation defines the attribute and every one that is not needed you just put "\_" in its place.

---
If you need to use a different variable that is not in the `1st part` or you need to use a variable and you don't already have the primary key for its relation ... you will have to add the `2nd part`. 

Its just: 
`∃ variable_you_need, another_ one : ` 

in this example from 6.1.c it is needed to add `AbNr` so you can get to `FilNr`:

{𝐴𝑛𝑁𝑟, 𝐴𝑛𝑁𝑎𝑚𝑒, 𝐴𝑏𝑁𝑎𝑚𝑒 | ∃𝐴𝑏𝑁𝑟, 𝐹𝑖𝑙𝑁𝑟: 𝐴𝑛𝑔𝑒𝑠𝑡𝑒𝑙𝑙𝑡𝑒𝑟(𝐴𝑛𝑁𝑟, 𝐴𝑛𝑁𝑎𝑚𝑒, \_, 𝐴𝑏𝑁𝑟, \_ , \_) ∧ 𝐴𝑏𝑡𝑒𝑖𝑙𝑢𝑛𝑔( 𝐴𝑏𝑁𝑟, 𝐴𝑏𝑁𝑎𝑚𝑒, 𝐹𝑖𝑙𝑁𝑟, \_ , \_ ) ∧ 𝐹𝑖𝑙𝑖𝑎𝑙𝑒(𝐹𝑖𝑙𝑁𝑟, ′𝐾𝑜𝑒𝑙𝑛′, \_ )

you also have to add the `3rd part` for every extra variable from the `2nd part`. 

---
If you have to match something it is easiest to just write it into the `3rd part` 
e.g. Department name has to be "HR" :  

{ `na,nr` | Employee( \_ , `na` , \_ , \_  )  $\wedge$ Department( *"HR"*, `nr`) }

If its something like > you do it like this:

{ `na,nr` | $\exists$ s : Employee( \_ , `na` , \_ , s  )  $\wedge$ Department( *"HR"*, `nr`) $\wedge$ (s < 2000) }

### May be Klausurrelevant:
![[tutorium_06.pdf#page=20|tutorium_06, page 20]]