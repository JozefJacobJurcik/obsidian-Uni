In der abstrakten Algebra bezeichnet man als **Körpererweiterung** ein Paar $L$ und $K$ , geschrieben als $L / K$,  wobei $K$ ein _Unterkörper_ eines _Oberkörpers_ $L$ ist, also eine Teilmenge $K ⊆ L$ , die 0 und 1 enthält und mit den auf $K$ eingeschränkten Verknüpfungen selbst ein [[Körper]] ist. Zum Beispiel ist der Körper $\mathbb C$ der komplexen Zahlen ein Oberkörper des Körpers $\mathbb R$ der reellen Zahlen und daher $\mathbb C / \mathbb R$  eine Körpererweiterung.

Sei $K$ ein [[Körper]] und $p(x) ∈ K[x]$ 

Die [[Menge]] 
	$K[x]/p(x) := \{ q(x) ∈ K[x] ; \operatorname{deg}\: q(x) < \operatorname{deg}\: p(x)\}$ 
ist *Vertretersystem* für die [[Äquivalenzklassen]] von  $K[x]$ [[modulo]] $p(x)$

>[!info] Theorem 
>Ist $p(x)$ *irreduzibel*, so bildet $K[x]/p(x)$ mit der Addition und Multiplikation [[modulo]] $p(x)$ einen [[Körper]].

Der Körper $K[x]/p(x)$ enthält $K$ als *Unterkörper*.

##### Endliche Körper 

>[!info] Theorem 
>Für jede Primzahlpotenz $p^n$ gibt es einen 
>(bis auf [[Isomorphismus|Isomorphie]] eindeutigen) 
>Körper $K$ mit [[Charakteristik|char]]$(K)= p$ und $|K| = p^n$ . 


Konstruktion: 
- Wähle Primkörper $\mathbb Z_p$ 
- sei $p(x)$ *irreduzibel* in $\mathbb Z_p[x]$ vom Grad deg $p(x) = n$ 
- der gesuchte Körper ist $K = \mathbb Z_p[x]/p(x)$

