---

---


![[Pasted image 20240223224322.png]]
## Fehlerarten
Biometrische Systeme sind fehlerbehaftet 

*Fehlerarten*: 
- Falsch Positiv / Falschakzeptanzrate (Mallet wird als Alice authentisiert) 
- Falsch Negativ / Falschrückweisungsrate (Alice wird nicht als Alice identifiziert) 

-> Fehler sind abhängig von Schwellwerteinstellungen

![[Pasted image 20240223225659.png]]
#### Fehlerraten 
Abschätzung der Fehlerraten: 

$N$: Anzahl der Identitäten 
$FP$ : Falsch Positiv (Falschakzept.) 
$FN$: Falsch Negativ (Falschrückw.) 

Es gilt:

$FN (N) \cong FN$
$FP(N) \cong 1 - (1- FP)^N \cong N \times FP$ 
falls
$N \times FP < 0,1$

###### Anwendungsbeispiel: 
$N$ = 10.000 
$FP$ = 0,00001 (0,001 %) 
Damit $FP(N)$ = 0,1 

D.h. Fehlerrate von *10 %*
Angreifer probiert seine 10 Finger und hat nennenswerte Chance 
Praxisforderung: $FP(N) < 1/100.000$ 

### Fingerabdruck
- Identifikation anhand des Fingerabdrucks hat lange Geschichte 
- Merkmale von Fingerabdrücken sind gut klassifiziert
![[Pasted image 20240223224705.png]]

#### Merkmalsextraktion
Die vorgestellten Klassen lassen sich leicht unterscheiden 
Extraktion sogenannter *Minuzien* (Minutiae): 
- Repräsentation basierend auf charakteristischen Rillenstrukturen 
- Problem der Invarianz bei unterschiedlicher Belichtung oder unterschiedlichem Druck Folgende Beispiele sind äquivalent (entstanden durch untersch. Druck) 
![[Pasted image 20240223224841.png]]
- Solche äquivalente Rillenstrukturen werden zu einer Minuzie zusammen-gefasst

*Merkmale*: Lage der Minuzien 
- Absolut bezüglich des Abdrucks und relativ zueinander 
- Orientierung bzw. Richtung

#### Angriffe
Sicherheit hängt auch von der Art des Sensors ab 
- Optische Sensoren (Lichtreflexion) 
- Kapazitive Sensoren (elektrische Leitfähigkeit, Kapazität) 
- Temperatur, Ultraschall,......

Optische Sensoren können einfach „betrogen“ werden 
- Finger-Form mit Hilfe von warmem Plastik abnehmen 
- Form mit Silikon oder Gummi ausgießen 
- Gummi-Finger verwenden 
- Akzeptanzrate bei vielen optischen Sensoren über 80 % 
- Finger-Form kann auch mit einem Fingerabdruck auf Glas erzeugt werden, d.h. der „Original-Finger“ ist nicht erforderlich

Kapazitive Sensoren weisen Gummi-Finger i.d.R. zurück 
-> Verbesserung durch kombinierte Sensoren

#### Lebenderkennung 
- Puls 
- Tiefenmuster 
- Wärmebild 
- totes Gewebe absorbiert Infrarotlicht 
- Blutzirkulation 
- Messen der Sauerstoff-Sättigung 
- Messen des elektrischen Widerstands 
- Feuchtigkeit

