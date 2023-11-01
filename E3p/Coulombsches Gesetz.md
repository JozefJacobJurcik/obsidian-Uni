---

---

Das *coulombsche Gesetz* oder Coulomb-Gesetz ist die Basis der Elektrostatik. Es beschreibt die **zwischen zwei Punktladungen wirkende Kraft**. Es gilt auch für kugelsymmetrisch verteilte elektrische Ladungen, die räumlich getrennt sind. 

Bei mehr als zwei Ladungen werden die einzelnen Kraftvektoren gemäß dem **Superpositionsprinzip** addiert. 

Im Internationalen Einheitensystem, *in skalarer Form und im Vakuum* ist die Kraft demnach
$$\Large{\displaystyle F={\frac {1}{4\pi \varepsilon _{0}}}{\frac {q_{1}\,q_{2}}{r^{2}}}}$$
- $q_{1}$, $q_{2}$  - kugelsymmetrisch verteilte Ladungsmengen
- $r$  - Abstand zwischen den Mittelpunkten der Ladungsmengen
- $\varepsilon _{0}$ - [[elektrische Feldkonstante]] 

### Vektorform

Die vektorielle Notation diskreter Ladungen liefert das *Coulomb-Kraftfeld*, dem eine kugelsymmetrische Probeladung $q_{1}$ im Feld einer zweiten kugelsymmetrischen Ladung q 2 $q_{2}$ ausgesetzt ist, wie folgt:
$${\displaystyle {\vec {F}}_{12}({\vec {r}}_{1})={\frac {q_{1}q_{2}}{4\pi \varepsilon _{0}}}{\frac {{\vec {e}}_{12}}{|{\vec {r}}_{1}-{\vec {r}}_{2}|^{2}}}}$$

- ${\vec {F}}_{{12}}$ - Kraft auf die Probeladung $q_{1}$, hervorgerufen von der Ladung $q_{2}$
- ${\displaystyle {\vec {r}}_{1},{\vec {r}}_{2}}$ - Ortsvektoren der beiden Ladungsmittelpunkte
- ${\displaystyle {\vec {e}}_{12}}$ - Einheitsvektor, der von $q_{2}$ (entlang der Verbindungslinie beider Ladungsmittelpunkte) in Richtung $q_{1}$ zeigt.

Wie zu sehen, müssen sich gleichnamige Ladungen, d. h. solche gleichen Vorzeichens, dabei obiger Festlegung gemäß abstoßen, da die Kraft ${\vec {F}}_{{12}}$ in solchem Fall dieselbe Orientierung wie ${\displaystyle {\vec {e}}_{12}}$ besitzt, während sich Ladungen mit ungleichem Vorzeichen (ungleichnamige Ladungen) anziehen, da die Kraft ${\vec {F}}_{{12}}$ dann (analog zum newtonschen Gravitationsgesetz) die entgegengesetzte Orientierung von ${\displaystyle {\vec {e}}_{12}}$ besitzt.

Eine alternative Formulierung erhält man, indem man| ${\displaystyle {\vec {e}}_{12}={\frac {{\vec {r}}_{1}-{\vec {r}}_{2}}{|{\vec {r}}_{1}-{\vec {r}}_{2}|}}}$ in die Formel einsetzt: $${\displaystyle {\vec {F}}_{12}({\vec {r}}_{1})={\frac {q_{1}q_{2}}{4\pi \varepsilon _{0}}}{\frac {{\vec {r}}_{1}-{\vec {r}}_{2}}{|{\vec {r}}_{1}-{\vec {r}}_{2}|^{3}}}}$$Wird der Koordinatenursprung an die Position der Ladung $q_{2}$ gelegt, vereinfacht sich diese Gleichung zu:
$${\displaystyle {\vec {F}}_{12}({\vec {r}}_{1})=q_{1}\,{\frac {q_{2}}{4\pi \varepsilon _{0}\,|{\vec {r}}_{1}|^{3}}}\ {\vec {r}}_{1}}$$
Weiter ist dann
$${\displaystyle {\vec {E}}({\vec {r}})={\frac {q_{2}}{4\pi \varepsilon _{0}\,r^{3}}}\ {\vec {r}}}
$$
der Vektor der [[Elektrische Feldstärke|Feldstärke]] des von der Zentralladung $q_{2}$ erzeugten elektrischen Feldes an der Stelle ${\vec {r}}$, d. h. im Abstand  $r$  vom Ursprung.

Wirken mehrere diskrete im Raum verteilte Ladungen $q_{j}$ auf die Probeladung $q_{1}$, so erhält man die gesamte auf  $q_{1}$ ausgeübte Kraft durch Vektoraddition:
$${\displaystyle {\vec {F}}_{1}({\vec {r}}_{1})=q_{1}{\frac {1}{4\pi \varepsilon _{0}}}\sum _{j>1}q_{j}{\frac {{\vec {r}}_{1}-{\vec {r}}_{j}}{|{\vec {r}}_{1}-{\vec {r}}_{j}|^{3}}}}$$
Werden die das Feld erzeugenden Ladungen $q_{j}$ durch eine im Raum verteilte Ladungswolke mit Ladungsdichte ${\displaystyle \rho ({\vec {r}}')}$ ersetzt, tritt an die Stelle der Summe ein Volumenintegral:
$${\displaystyle {\vec {F}}_{1}({\vec {r}})=q_{1}{\frac {1}{4\pi \varepsilon _{0}}}\,\int \rho ({\vec {r}}'){\frac {({\vec {r}}-{\vec {r}}')}{|{\vec {r}}-{\vec {r}}'|^{3}}}\,\mathrm {d} ^{3}{\vec {r}}'}$$
Das coulombsche Gesetz in der eingangs gegebenen Form ist dabei als Spezialfall für eine punktförmige Ladungsverteilung in dieser Formel enthalten. Umgekehrt kann mittels Superpositionsprinzip auch diese allgemeinere Form aus dem coulombschen Gesetz hergeleitet werden. 