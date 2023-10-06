---
aliases: Absorption
---

Das *Absorptionsgesetz* der Aussagenlogik besagt, dass eine Aussage absorbiert wird, d. h., dass ihre Belegung für die Auswertung der Gesamtformel irrelevant ist, wenn sie hintereinander konjunktiv und disjunktiv mit einer anderen Aussage verknüpft wird, wobei die Reihenfolge der Verknüpfungen keine Rolle spielt.

Die Wahrheitswertentwicklung von Aussageformen, die die Aussagen a und b direkt aufeinanderfolgend konjunktiv und disjunktiv oder disjunktiv und konjunktiv verknüpfen, entspricht also dem Wahrheitswert von a.

$a\lor(a\land b)=a$ und $a\land(a\lor b)=a$ #

**In Worten:** Die Konjunktion $a\land b$ kann nur wahr sein, wenn a wahr ist. Dann ist aber auch jede Disjunktion mit $a$ wahr, unabhängig von $b$. Umgekehrt kann die Disjunktion nur dann falsch sein, wenn $a$ falsch ist. Somit ist dann auch die Konjunktion $a\land b$ falsch und damit der gesamte Ausdruck unabhängig von $b$. Analog bei vertauschten Junktoren. Der Beweis erfolgt über Wahrheitstafeln:

|a |b|( a ∧ b )|( a ∨ b )|a ∨ ( a ∧ b ) = a|a ∧ ( a ∨ b ) = a|
|---|---|---|---|---|---|
|**0**|0|0|0|**0**|**0**|
|**0**|1|0|1|**0**|**0**|
|**1**|0|0|1|**1**|**1**|
|**1**|1|1|1|**1**|**1**|
