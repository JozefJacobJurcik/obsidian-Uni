---

---
Transaktion: Folge von Befehlen (read, write), die die Datenbank von einem **konsistenten** Zustand in einen anderen **konsistenten** Zustand überführt

-> Einheit integritätserhaltender Zustandsänderung einer Datenbank

##### **Hauptaufgaben** von Transaktionen: 
- Synchronisation (Koordination mehrerer Benutzerprozesse) 
- Recovery (Beheben von Fehlersituationen)

##### **Eigenschaften** von Transaktionen:
- Atomicity 
- Consistency 
- Isolation 
- Durability
	-> [[ACID-Prinzip]]

##### Warum Transaktionen?
- Datenbanken werden selten von nur einem Benutzer benutzt 
	-> mehrere Nutzer arbeiten gleichzeitig auf den Daten 

 - Die Nutzer sollen nichts von den anderen Nutzern mitbekommen 
	 -> logischer Einnutzerbetrieb 

 - Pseudoparallele Ausführung der Transaktionen 
	 -> bessere Auslastung des Systems 
 
 - Ohne Kontrolle des Ablaufs von TAs 
	 -> Anomalien können auftreten

### Anomalien

#### Lost Update
Verloren gegangene Änderung 
Zwei Transaktionen: $𝑇_1, 𝑇_2$ 

- $𝑇_2$ ändert Objekt $x$ -> Änderung wird durch $𝑇_1$ überschrieben 

- Änderung von $𝑇_2$ geht verloren 
	$\Rightarrow$ Verstoß gegen *Durability*

![[Pasted image 20240219022143.png]]

#### Dirty Read / Dirty Write
Zugriff auf „schmutzige“ (nicht dauerhaft gültige) Daten 
Zwei Transaktionen: $𝑇_1, 𝑇_2$ 

- $𝑇_1$ verändert Objekt $x$ zwei mal 
- Zwischen den Änderungen liest $𝑇_2$ den Wert von $x$ (dieser Wert bleibt aber nicht dauerhaft gültig) 
	$\Rightarrow$ Verstoß gegen *Consistency*

![[Pasted image 20240219022353.png]]

#### Non-Repeatable Read
Eine Transaktion sieht während ihrer Ausführung zwei unterschiedliche Werte von einem Objekt 

- $𝑇_1$ liest beim ersten Auslesen von $x$ einen anderen Wert als beim zweiten, da $𝑇_2$ den Wert von $x$ verändert 
	$\Rightarrow$ Verstoß gegen *Isolation* 

 $\Rightarrow$ Transaktionen müssen so Ausgeführt werden, dass das [[ACID-Prinzip]] nicht verletzt wird

![[Schedule]]