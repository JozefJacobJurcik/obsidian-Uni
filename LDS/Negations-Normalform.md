---
aliases: NNF
---
Eine logische Formel ist in *Negationsnormalform* (NNF), falls die *Negationsoperatoren* in ihr nur direkt über atomaren Aussagen vorkommen.

In klassischer Logik kann jede Formel in diese Form gebracht werden, indem man wie folgt vorgeht:

- Man löst die in ihr vorkommenden materialen Implikationen und [Bikonditionale](https://de.wikipedia.org/wiki/Bikonditional "Bikonditional") mittels der für diese geltenden Äquivalenzgesetze auf. Beispiele sind :
    - $P → Q ≡ ¬ P ∨ Q$
    - $¬ ( P → Q ) ≡ P ∧ ¬ Q$ 
    - $P ↔ Q ≡ ( P ∧ Q ) ∨ ( ¬ P ∧ ¬ Q )$ 

- Man verschiebt mittels der [[De Morganschen Gesetze]] die Negationen nach innen und beseitigt dabei zugleich gegebenenfalls auftretende doppelte Negationen
### Vorlesung
Formeln in *Negations-Normalform (NNF)* sind definiert durch:

- $0, 1$ und [[Literal]]e sind in *NNF*, 
- sind $F$ und $G$ in *NNF*, dann auch $F ∧ G$ und $F ∨ G$. 

**Also:** $F$ ist in *NNF*, wenn keine Implikationen und Negationen nur vor Variablen vorkommen.

>[!info] Theorem 
>Für jede Formel $F$ gibt es $n(F)$  in *NNF* mit $n(F) ≡ F$.
![[Pasted image 20231012191734.png]]

See also: [[Disjunktive und Konjunktive Normalform]]
