---

---

**Autorisierung**
Vergabe / Spezifikation von Berechtigungen 

**Zugriffskontrolle**
Durchsetzung dieser Berechtigungen

Häufig werden Autorisierung und Zugriffskontrolle zusammengefasst 

- Handelnde werden als Subjekt bezeichnet 
- Berechtigungen werden an Subjekte erteilt 
- Berechtigungen gelten für Objekte 
- Objekte sind die schützenswerten Einheiten im System

![[Pasted image 20240224022830.png]]

### Klassifikation
**DAC** (*Discretionary Access Control*) 
- Basieren auf dem Eigentümerprinzip 
- Eigentümer spezifiziert Berechtigungen an seinen Objekten 
- Zugriffsrechte auf Basis der Objekte vergeben 

**MAC** (*Mandatory Access Control*) 
- Regelbasierte Festlegung der Rechte 
- Systemglobal 
- Z.B. Bell-LaPadula; Regeln werden über Sicherheitsklassen (unklassifiziert, vertraulich, geheim, streng geheim) spezifiziert 

**RBAC** (*Role-based Access Control*) 
- Trennung von Subjekt und Aufgabe 
- Berechtigungen werden nicht mehr an Subjekt, sondern an bestimmte Aufgabe geknüpft 
- Subjekte erhalten Berechtigung über Rollenmitgliedschaft(en)

![[Pasted image 20240224023216.png]]

#### Zugriffsmatrix
Schutzzustand eines Systems zum Zeitpunkt $t$ wird durch Matrix $M(t)$ modelliert: 
- $M(t) = S(t) \times  O(t)$ ; es gilt $M(t): S(t) \times O(t) \rightarrow 2^R$ 
- $R$ ist die Menge der Zugriffsrechte 
- Subjekte $S$ bilden die Zeilen der Matrix 
- Objekte $O$ bilden die Spalten 
- Ein Eintrag $M(t,s,o) = \{r_1,r_2,...,r_n\}$ beschreibt die Menge der Rechte des Subjekts $s$ zum Zeitpunkt $t$ am Objekt $o$
![[Pasted image 20240224023456.png]]

Implementierung „spaltenweise“: Zugriffskontrolllisten (z.B. UNIX) 
Implementierung „zeilenweise“: Capabilities

#### Referenzmonitor
Zur Realisierung der Zugriffskontrolle ist eine sichere, „vertrauenswürdige“ Systemkomponente erforderlich 

Häufig als Referenzmonitor oder Access Control Monitor bezeichnet 

Erfüllt folgende Anforderungen: 
- Zugriff auf Objekte nur über den Monitor möglich 
- Monitor kann Aufrufenden (Subjekt) zweifelsfrei identifizieren (Authentisierung) 
- Monitor kann Objektzugriff unterbrechen bzw. verhindern