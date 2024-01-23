---
aliases: extended Euclidean algorithm
klausur: 1
---

Der Algorithmus berechnet für $m, n ∈ \mathbb N$ mit $m ≤ n$ Zahlen $s,t ∈ \mathbb Z$ mit [[ggT]]$(m, n) = sm + tn$.

```Pseudocode
Eingabe: m,n ∈ N mit m ≤ n
Ausgabe: s,t ∈ Z mit ggT(m,n) = sm + tn

ErwEuklid(m,n)
	if m | n then
		return (1 , 0)
	else 
		(s′ , t′) := ErwEuklid(n mod m,m)
		s = t′ − s′ ⌊n/m⌋ 
		t = s′ 
		return (s,t)
```

```Python
# Python - extended Euclidean algorithm

def extended_gcd(a, b):
    if a == 0:
        return b, 0, 1
    else:
        gcd, x, y = extended_gcd(b % a, a)
        return gcd, y - (b // a) * x, x
        
if __name__ == '__main__':
    gcd, x, y = extended_gcd(30, 50)
    print('The GCD is', gcd)
    print(f'x = {x}, y = {y}')
```

###### Beispiel:
https://youtu.be/YYU0o-nv4ec?si=2BqVcmpOoVIr0O-u

$\operatorname{ggT}({\color{cyan}31},{\color{orange}26})$

|i|a|b|r|q| $\quad$|x|y| |
|---|---|---|---|---|---|---|---|---|
|1|${\color{cyan}31}$|${\color{orange}26}$|5|1||${\color{YellowGreen}-5}$|6|$\leftarrow {\color{CarnationPink}x} - q \cdot {\color{YellowGreen}y}$|
| ||$\overset{\downarrow}{\swarrow}$|$\overset{\downarrow}{\swarrow}$|||$\overset{\nearrow}{\uparrow}$|$\overset{\nwarrow \uparrow}{\uparrow}$||
|2|${\color{cyan}26}$|${\color{orange}5}$|${\color{lime}1}$|5||${\color{CarnationPink}1}$|${\color{YellowGreen}-5}$|$\leftarrow {\color{Emerald}x} - q \cdot {\color{CarnationPink}y}$|
| ||$\overset{\downarrow}{\swarrow}$|$\overset{\downarrow}{\swarrow}$|||$\overset{\nearrow}{\uparrow}$|$\overset{\nwarrow \uparrow}{\uparrow}$||
|3|${\color{cyan}5}$|${\color{orange}1}$|${\color{red}0}$|5| |${\color{Emerald}0}$|${\color{CarnationPink}1}$|immer 0 und 1|

$\operatorname{ggT}({\color{cyan}23},{\color{orange}17})$

|i|a|b|r|q| $\quad$|x|y| |
|---|---|---|---|---|---|---|---|---|
|1|${\color{cyan}23}$|${\color{orange}17}$|6|1||${\color{Apricot}3}$|$-4$|$\leftarrow {\color{YellowGreen}x} - q \cdot {\color{Apricot}y}$|
| ||$\overset{\downarrow}{\swarrow}$|$\overset{\downarrow}{\swarrow}$|||$\overset{\nearrow}{\uparrow}$|$\overset{\nwarrow \uparrow}{\uparrow}$||
|2|${\color{cyan}17}$|${\color{orange}6}$|5|2||${\color{YellowGreen}-1}$|${\color{Apricot}3}$|$\leftarrow {\color{CarnationPink}x} - q \cdot {\color{YellowGreen}y}$|
| ||$\overset{\downarrow}{\swarrow}$|$\overset{\downarrow}{\swarrow}$|||$\overset{\nearrow}{\uparrow}$|$\overset{\nwarrow \uparrow}{\uparrow}$||
|3|${\color{cyan}6}$|${\color{orange}5}$|${\color{lime}1}$|1| |${\color{CarnationPink}1}$|${\color{YellowGreen}-1}$|$\leftarrow {\color{Emerald}x} - q \cdot {\color{CarnationPink}y}$|
| ||$\overset{\downarrow}{\swarrow}$|$\overset{\downarrow}{\swarrow}$|||$\overset{\nearrow}{\uparrow}$|$\overset{\nwarrow \uparrow}{\uparrow}$||
|4|${\color{cyan}5}$|${\color{orange}1}$|${\color{red}0}$|5||${\color{Emerald}0}$|${\color{CarnationPink}1}$|immer 0 und 1|


$\operatorname{ggT}({\color{cyan}345},{\color{orange}42})$

|i|a|b|r|q| $\quad$|x|y| |
|---|---|---|---|---|---|---|---|---|
|1|${\color{cyan}345}$|${\color{orange}42}$|9|8||${\color{Apricot}5}$|$-41$|$\leftarrow {\color{YellowGreen}x} - q \cdot {\color{Apricot}y}$|
| ||$\overset{\downarrow}{\swarrow}$|$\overset{\downarrow}{\swarrow}$|||$\overset{\nearrow}{\uparrow}$|$\overset{\nwarrow \uparrow}{\uparrow}$||
|2|${\color{cyan}42}$|${\color{orange}9}$|6|4||${\color{YellowGreen}-1}$|${\color{Apricot}5}$|$\leftarrow {\color{CarnationPink}x} - q \cdot {\color{YellowGreen}y}$|
| ||$\overset{\downarrow}{\swarrow}$|$\overset{\downarrow}{\swarrow}$|||$\overset{\nearrow}{\uparrow}$|$\overset{\nwarrow \uparrow}{\uparrow}$||
|3|${\color{cyan}9}$|${\color{orange}6}$|${\color{lime}3}$|1| |${\color{CarnationPink}1}$|${\color{YellowGreen}-1}$|$\leftarrow {\color{Emerald}x} - q \cdot {\color{CarnationPink}y}$|
| ||$\overset{\downarrow}{\swarrow}$|$\overset{\downarrow}{\swarrow}$|||$\overset{\nearrow}{\uparrow}$|$\overset{\nwarrow \uparrow}{\uparrow}$||
|4|${\color{cyan}6}$|${\color{orange}3}$|${\color{red}0}$|2||${\color{Emerald}0}$|${\color{CarnationPink}1}$|immer 0 und 1|


$i =$ Iterationsschritt
$\operatorname{ggT}(a,b) = a\cdot x+b\cdot y$ 
$q = a \://\: b$ = wie oft b in a passt
$r = a \operatorname{mod} b$
${\color{red}r} = 0 \Rightarrow$ terminates and the ${\color{lime}r}$ before is the *ggT*
