---
klausur: 1
---

Eine Aussage in der [[Prädikatenlogik erster Stufe]] befindet sich in Pränexform, wenn alle Quantoren (Beschreibungen des Geltungsbereichs) außerhalb bzw. vor der eigentlichen Formel stehen.

###### Beispiel:
See also: [[Pränexnormalform -exercise]]

Die Ausgangsformel lautet:
$${\displaystyle \forall x.P(x)\land \forall y.Q(y)\land \forall z.R(z,y)}$$
Es kommt die Variable $y$ sowohl gebunden als auch frei vor. Dies darf in der Pränexform aber nicht sein. Deshalb wird eine neue Variable eingeführt: $w$. Nach der Anpassung sieht das nun so aus: $${\displaystyle \forall x.P(x)\land \forall w.Q(w)\land \forall z.R(z,y)}$$
Nun kommt jede Variable entweder gebunden oder frei vor und somit können wir die Quantoren alle nach vorn „ziehen“, was dann folgendermaßen aussieht:$${\displaystyle \forall x.\forall w.\forall z.(P(x)\land Q(w)\land R(z,y))}$$
