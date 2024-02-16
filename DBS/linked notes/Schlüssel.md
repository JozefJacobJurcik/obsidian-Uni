---

---

Teil[[menge]] $S$ der Attribute eines [[Das Relationale Modell|Relationenschema]]s $R$ heißt *Schlüssel*, falls gilt 
1. **Eindeutigkeit:** keine zwei Tupel dürfen sich in allen Attributen von $S$ gleichen 
2. **Minimalität:** keine echte Teilmenge von $S$ erfüllt die Eindeutigkeit 

*Trivial:* Schlüssel mit nur einem Attribut sind immer minimal Wenn zusammengesetzt: Prüfe jede Teilmenge von $S$ auf Eindeutigkeit

Oft wird eine fortlaufende ID als Schlüssel eingesetzt –> Einfach, nur ein Attribut, Eindeutig für jedes Tupel

### Fremdschlüssel
 - Attribut das auf einen Schlüssel einer anderen Relation verweist, heißt Fremdschlüssel 
 - Fremdschlüssel braucht einen gültigen Partner in der anderen Tabelle
 - Vorsicht beim Löschen von Tupeln auf die (von einer anderen Tabelle) verwiesen wird

###### Beispiel:
![[tutorium_03.pdf#page=5|tutorium_03, page 5]]


See also: [[Primary key]] , [[Foreign key]]
