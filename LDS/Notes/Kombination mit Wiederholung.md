Sollen aus einer [[Menge]] von $n$ Elementen $k$ Elemente ausgewählt werden, wobei ihre Reihenfolge weiterhin ohne Belang sein soll, sie sich aber nun auch wiederholen dürfen, wie das z. B. beim Ziehen mit Zurücklegen möglich ist, ergibt sich für die Zahl der Möglichkeiten folgende Formel:
$$ {\displaystyle {\frac {(n+k-1)!}{(n-1)!\cdot k!}}={\binom {n+k-1}{k}}={\binom {n+k-1}{n-1}}=\left(\!\!{\binom {n}{k}}\!\!\right)} $$
Dies ist ersichtlich, wenn man jedes Ergebnis von $k$ ausgewählten Elementen aus $n$ möglichen Elementen durch eine Folge von $n + k$ Symbolen darstellt, wobei die Symbole N die $n$ Elemente der Auswahlmenge und die Symbole K die $k$ ausgewählten Elemente darstellen. Die Folge beginnt immer mit einem N. Die Anzahl der K vor dem zweiten N entspricht der Häufigkeit, mit der das erste der $n$ Elemente gezogen wurde, die Anzahl der K zwischen dem zweiten und dritten N entspricht der Häufigkeit des zweiten Elements usw. Da bis auf das erste N alle Symbole frei kombiniert werden können, entspricht die Anzahl der Kombinationen und damit die Anzahl der Zugmöglichkeiten der angegebenen Formel.

Beispielsweise entspricht bei der Auswahl von 3 aus den 5 Elementen der Menge $\{ 1 , 2 , 3 , 4 , 5 \}$ mit Zurücklegen das Ergebnis 1, 3, 3 der Symbolfolge NKNNKKNN, das Ergebnis 5, 5, 5 der Folge NNNNNKKK.

Die Symbol-folgen können auch mit senkrechten Strichen und Sternen dargestellt werden. Das Ergebnis 1, 3, 3 entspricht ${\displaystyle \bigstar ||\bigstar \bigstar ||}$ und das Ergebnis (5, 5, 5) entspricht ${\displaystyle ||||\bigstar \bigstar \bigstar }$ . Die 3 Sterne können an 7 verschiedenen Positionen platziert werden.

Es ergeben sich daher $${\displaystyle {\binom {n+k-1}{k}}={\binom {7}{3}}={\frac {7!}{3!\cdot 4!}}=35}$$mögliche Kombinationen.