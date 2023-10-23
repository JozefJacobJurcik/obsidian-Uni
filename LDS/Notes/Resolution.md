---
aliases: Resolvant
---

**Resolvant** : For any 2 [[Klausel|clauses]] $C_1$ and $C_2$, if  $C_1$ has a [[literal]] $L_1$ and $C_2$ has $L_2$ which is the complement of literal $L_1$, then delete $L_1$ and $L_2$ from $C_1$ and $C_2$ and construct the [[DNF|disjunction]] of remaining literals. The result so obtained is called the **resolvant** of $C_1$ and $C_2$. 

Example: Let us suppose that
$C_1 = P ∨ Q ∨ R$
$C_2= ¬P ∨ S ∨ T$

$P$ and $¬P$ are complementary to each other. According to the definition of resolvant, delete $P$ and $¬P$ and take the disjunction of the remaining literals i.e. $S ∨ T ∨ Q ∨ R$ 


### Resolutionbeweis:

Consider an argument with premises $P_1,\:P_2,\:...,\:P_n$ and conclusion $C$.
To prove whether an argument is valid, put all the premises in clause form and add $¬C$ to it.
From the sequence, if the **empty clause** can be derived, then the argument is *valid*. 

This way you can prove an argument in the form of a [[KNF]] by "resolving" the particular clauses of the KNF.
###### Beispiele: 

![[Resolution -exercise]]