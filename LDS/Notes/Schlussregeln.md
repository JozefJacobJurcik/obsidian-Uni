---
aliases: Schlussregel
---

Die **Schlussegeln** des [[Sequenzenkalkül]]s erlauben aus bekannten [[Sequenz]]en (*Prämissen*) eine neue Sequenz (*Konklusion*) herzuleiten.

![[Pasted image 20231012231257.png]]
![[Pasted image 20231012231319.png]]

It looks scarry but its not that hard. The first thing to understand is that *if* the thing on top  of the *inference line* holds (implication) the bottom part also holds (conclusion). $Γ$ and $Δ$ just stand for possible additional arguments. 

The easiest way to work with sequent calculus is to make a tree. Starting at the bottom you will have formula to prove. And using the rules above you will add *inference lines* and and layers to the tree until you reach an [[axiom]]. If every branch ends in an axiom you have proven your formula because you just have axioms $\Rightarrow\Rightarrow...\Rightarrow$ your formula.

A sequent tree can look like this: (Everybody else seems to use the turnstile $\vdash$ instead of $\Rightarrow$)
![[Pasted image 20231023141214.png]]
from: https://en.wikipedia.org/wiki/Sequent_calculus

See also:
https://youtu.be/xLRUofFSq5Y?si=NEaXoK2BDvvSpJ6d