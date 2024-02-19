---

---

**Eingabe:** eine [[Menge]] $F$ von [[Funktionale Abhängigkeit|funktionalen Abhängigkeiten]] und eine Menge $X$ von Attributen 
**Ausgabe:** die vollständige Menge von Attributen $𝑋^+$ für die gilt $𝑋 → 𝑋^+$ (also die Menge an Attributen die man von $X$ mit allen $F$ herleiten kann)

```pseudo-code
Hülle( F , α ) 
    α+ = α 
   while( Änderung an α+ ) do
      foreach( Abhängigkeit β → γ ∈ F) do
        if ( β ⊆ α+ ) then α+ = α+ ∪ γ 
```

**Angewendet** auf eine konkrete Menge an funktionalen Abhängigkeiten $F$:

$F$ hat die Abhängigkeiten:
	${\displaystyle A,B\rightarrow C}$
	${\displaystyle D\rightarrow E,F}$
	${\displaystyle A\rightarrow G,H}$
	${\displaystyle G\rightarrow B}$

Wir wollen die **Attributhülle** für $A$ bestimmen.

1.  ${\displaystyle A^{+}=A}$

2. Durchlaufen der funktionalen Abhängigkeiten von oben nach unten:

 - ${\displaystyle A,B}$ ist keine Teilmenge von $A$ 
- $D$ ist keine Teilmenge von $A$ 
- $A$  ist Teilmenge von $A$ 
		${\displaystyle A^{+}=A^{+}+G,H}$
- $G$ ist Teilmenge von $A , G , H$ 
		${\displaystyle A^{+}=A^{+}+B}$
- Neuer Durchlauf:
- $A , B$  ist Teilmenge von $A , G , H , B$
		${\displaystyle A^{+}=A^{+}+C}$
* ...danach ändert sich nichts mehr an der Menge ${\displaystyle A^{+}=A,G,H,B,C}$

