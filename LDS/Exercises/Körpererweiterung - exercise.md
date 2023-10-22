###### 1.
Berechnen Sie den Körper $K := \mathbb Z_3[x]/p(x)$, d.h. die Menge, die dem Körper zugrunde liegt; die Verknüpfungstabellen brauchen nicht angegeben zu werden.

---
$\{0, 1, 2, x, x + 1, x + 2, 2x, 2x + 1, 2x + 2\}$

###### 2.
Wir betrachten den [[Körper]] $K := \mathbb Z_7[x]/p(x)$  ,   $p(x) = 2x^3 + 3x^2 + 1$ Wie viele Elemente hat $K$?

---
Alle Elemente von $K$ haben die Form $c_2x^2 + c_1x + c_0$, es gibt für $c_0, c_1, c_2$ je $7$ Möglichkeiten, insgesamt also $7^3 = 343$ Elemente.

###### 3.
Seien $a, b ∈ K\,,\: a = x^2 + 1\, ,\: b = 3x^2 + 2x + 1 \quad (K :=\mathbb Z_7[x]/p(x)\, ,\: p(x) = 2x^3 + 3x^2 + 1)$. Berechnen Sie die Werte $a · b$ sowie $a^2$ in $K$.

---
$$\begin{split} a \cdot b & = (x^2 + 1)(3x^2 + 2x + 1) \\ & = 3x^4 + 2x^3 + x 2 + 3x^2 + 2x + 1 \\ & = 3x^4 + 2x^3 + 4x^2 + 2x + 1\end{split}$$
Tabellarisch $3x^4 + 2x^3 + 4x^2 + 2x + 1$ mod  $2x^3 + 3x^2 + 1$ :

| |$x^4$|$x^3$|$x^2$|$x^1$|$x^0$| |
|---|---|---|---|---|---|---|
||||||||
||3|2|4|2|1||
|-|3|1|0|5|0|$= 5x · (2x^3 + 3x^2 + 1)$|
||||||||
|||1|4|4|1||
|-||1|5|0|4|$=4 · (2x^3 + 3x^2 + 1)$|
||||||||
||||6|4|4||

$⇝ 3x^4 + 2x^3 + 4x^2 + 2x + 1 = (5x + 4) · (2x^3 + 3x^2 + 1) + (6x^2 + 4x + 4)$
$⇝ 3x^4 + 2x^3 + 4x^2 + 2x + 1 ≡ {\color{orchid}6x^2 + 4x + 4} \quad (\operatorname{mod} \: 2x^3 + 3x^2 + 1)$
---
$a^2 = (x^2 + 1)^2 = x^4 + 2x^2 + 1$

| |$x^4$|$x^3$|$x^2$|$x^1$|$x^0$| |
|---|---|---|---|---|---|---|
||||||||
||1|0|2|0|1||
|-|1|5|0|4|0|$= 4x · (2x^3 + 3x^2 + 1)$|
||||||||
|||2|2|3|1||
|-||2|3|0|1|$=1 · (2x^3 + 3x^2 + 1)$|
||||||||
||||6|3|0||

$⇝ x^4 + 2x^2 + 1 = (4x + 1) · (2x^3 + 3x^2 + 1) + (6x^2 + 3x)$
$⇝ x^4 + 2x^2 + 1 ≡ {\color{orchid}6x^2 + 3x} \quad (\operatorname{mod} \: 2x 3 + 3x 2 + 1)$
