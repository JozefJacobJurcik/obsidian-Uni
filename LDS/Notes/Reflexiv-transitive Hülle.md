---
aliases: reflexiv-transitiven Abschluss
modul: "LDS"
klausur: 1
---
Die reflexiv-transitive Hülle $R^{{*}}$ ergibt sich durch
$$x\ R^{*}\ y:\Leftrightarrow x=y\lor x\ R^{+}\ y$$

Die [[Reflexiv-transitive Hülle]] bzw. den **reflexiv-transitiven Abschluss** der Relation erhält man, indem man zur transitiven Hülle die für [[Reflexivität]] noch fehlenden Paare auf der Diagonalen hinzufügt.

###### Beispiele:
Ist $R$ gegeben durch die zwei Paare $(a,b)$ und $(b,c)$, dann enthält $R^{+}$ zusätzlich das Paar $(a,c$). Für $R^{{*}}$ kommen die weiteren Paare $(a,a)$, $(b,b)$ und $(c,c)$ dazu.

Ist $R$ die Nachfolgerrelation auf der Menge der natürlichen Zahlen (also $a\,R\,b:\Longleftrightarrow a=b+1$), dann ergibt sich als transitive Hülle von $R$ die Größer-Relation $>$. Die reflexiv-transitive Hülle ist die Größer-Gleich-Relation $\geq$ .

### Vorlesung
$$R^∗ := R^+ ∪ {(a, a) ; a ∈ A }$$

Ist $R^′ ⊇ R$ [[Reflexivität|reflexiv]] und [[Transitivität|transitiv]], dann ist $R^′ ⊇ R^∗$ . 

**Alternative Definition:** $R^∗$ ist die *minimale [[Reflexivität|reflexive]] und [[Transitivität|transitive]] [[Relation]] $R^′ ⊇ R$ 


$R$ ist *azyklisch*, wenn es keine $a_1, a_2, . . . a_k ∈ A$ gibt, mit: $$a_1 \:R\: a_2 ∧ a_2 \:R \:a_3 ∧ . . . ∧ a_{k−1} \:R\: a_k ∧ a_k \:R\: a_1$$ Ist $R$ *azyklisch*, so ist $R^∗$ [[partielle Ordnung]].
