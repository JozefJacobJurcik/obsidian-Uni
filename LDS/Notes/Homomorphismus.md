---
aliases: Homomorphismen
klausur: 2
---
Es seien ${\displaystyle {\boldsymbol {A}}=(A,(f_{i})_{i\in I})}$ und ${\displaystyle {\boldsymbol {B}}=(B,(g_{i})_{i\in I})}$ zwei [[Algebra|algebraischen Struktur]]en vom gleichen Typ (*Signatur*) ${\displaystyle \sigma =(m_{i})_{i\in I}}$  , so dass für jedes $i$ die Zahl $m_{i}\in \mathbb {N} _{0}$ die (übereinstimmende) *Stelligkeit* der fundamentalen Operationen $f_i$ und $g_i$ bezeichnet. Eine Abbildung $\varphi \colon A\to B$ heißt _Homomorphismus_ von $A$ nach $B$ ,wenn für jedes $i$ und für alle $a_{1},\ldots ,a_{m_{i}}\in A$ gilt:  $$\varphi (f_{i}(a_{1},\ldots ,a_{m_{i}}))=g_{i}(\varphi (a_{1}),\ldots ,\varphi (a_{m_{i}}))$$

###### Beispiel:

Klassisches Beispiel von *Homomorphismen* sind *Homomorphismen* zwischen [[Gruppe]]n. Gegeben seien zwei Gruppen $( G , ∗ )$  und $( H , ⋆ )$. Eine [[Funktion]]
$$\phi \colon G\to H$$
heißt **Gruppenhomomorphismus**, wenn für alle Elemente $g_{1},g_{2}\in G$ gilt:
$$\phi (g_{1}*g_{2})=\phi (g_{1})\star \phi (g_{2})$$
Aus dieser Bedingung folgt unmittelbar, dass
$$\phi (e_{G})=e_{H}$$
für die [[neutrales Element|neutrale Elemente]] $e_{G}\in G,e_{H}\in H$ und dann
$$\phi (g^{-1})=\phi (g)^{-1}$$
für alle $g ∈ G$ gelten muss sowie, mittels [[Vollständige Induktion]], dass
$$\phi (g_{1}*\ldots *g_{n})=\phi (g_{1})\star \ldots \star \phi (g_{n})$$
für eine beliebige endliche Anzahl von Faktoren gilt.