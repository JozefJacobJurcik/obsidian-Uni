Ist f : A → B [[Bijektivität|bijektiv]], so ist |$f^{−1}$ (b)| = 1 für alle b ∈ B. 
Schreibe $f^{−1}$(b) = a statt $f^{−1}$(b) = {a}   (*Umkehrfunktion*)

Umkehrfunktion ist bijektive Funktion $f^{−1}$ : B → A.

![[Pasted image 20230822152859.png | 200]]
### Definition
Seien A und B nicht-leere [[Menge]]n. 

- Man sucht nach einer Funktion g : B → A, sodass g(f (a)) = a für alle a ∈ A und f (g(b)) = b für alle b ∈ B. Es stellt sich heraus, dass es höchstens **ein** solches g geben kann. Existiert dies, so nennt man f _invertierbar_ und das eindeutig bestimmte g die Umkehrfunktion von f.

- Unter Verwendung der Komposition von [[Funktion]]en kann die vorherige Bedingung auch etwas eleganter formuliert werden, indem man für g : B → A fordert: g ∘ f = $id_A$ und f ∘ g = $id_B$ . Dabei ist $id_A$ die [[Identitätsfunktion|identische Abbildung]] auf der Menge A.

- Man führt zunächst die weiter unten erklärten Begriffe von _Linksinversen_ und _Rechtsinversen_ ein. Dann nennt man eine Funktion _invertierbar_, wenn sie sowohl eine Linksinverse als auch eine Rechtsinverse besitzt. Es zeigt sich, dass in diesem Fall Linksinverse und Rechtsinverse übereinstimmen müssen (womit auch folgt, dass es in diesem Fall davon nicht mehrere gibt). Diese eindeutig bestimmte Links- und Rechtsinverse ist dann die Umkehrfunktion.

- Man bezieht sich bei der Definition darauf, dass eine Funktion von A nach B immer auch eine [[Relation]] von A nach B ist. Daher besitzt sie auf jeden Fall eine Umkehrrelation. Man nennt f _invertierbar_, wenn diese Umkehrrelation eine Funktion von B nach A ist. In diesem Fall wird die Umkehrrelation auch als Umkehrfunktion bezeichnet.

Es stellt sich heraus, dass alle vorgestellten **Invertierbarkeitsbegriffe äquivalent zum Begriff der Bijektivität** sind. Auch führen alle Definitionen der Umkehrfunktion zum gleichen Ergebnis.