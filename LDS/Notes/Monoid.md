Ein Monoid ist ein Tripel $( M , ∗ , e )$ bestehend aus einer [[Menge]] $M$, einer inneren zweistelligen Verknüpfung: 
$${\displaystyle *\colon M\times M\to M,\quad (a,b)\mapsto a*b}$$
und einem ausgezeichneten Element $e ∈ M$ mit den folgenden Eigenschaften bezüglich der angegebenen Verknüpfung:

1. [[Assoziativgesetz|Assoziativität]] der Verknüpfung:
$${\displaystyle \forall a,b,c\in M\colon (a*b)*c=a*(b*c)}$$
2. $e$ ist ein [[neutrales Element]]:
$${\displaystyle \forall a\in M\colon e*a=a*e=a}$$
Ein Monoid ist also eine [[Halbgruppe]] mit neutralem Element. Jede [[Gruppe]] ist ein *Monoid*, aber ein *Monoid* hat im Gegensatz zur Gruppe *nicht notwendigerweise inverse Elemente*.

###### Beispiel 1:
$M = Σ^∗$ [[Menge]] der Strings über Alphabet $Σ$ 
$*$ ist Konkatenation. 
[[neutrales Element]]: leerer String $ϵ$ 

###### Beispiel 2:
$M = F(M)$ [[Menge]] der [[Funktion]]en $F(M) = \{ f ; f : M → M \}$ 
$*$ ist Komposition. 
[[neutrales Element]]: Identität $\operatorname{id}$ 

