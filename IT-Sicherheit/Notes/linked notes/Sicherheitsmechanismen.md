---

---

## [[Vertraulichkeit]] (Confidentiality) 
- Schutz der Daten vor unberechtigter Offenlegung 
- Wie kann Vertraulichkeit realisiert werden? 
	- Durch Verschlüsselung (Encryption) 
	- Mallet kann Chiffrentext mangels Kenntnis des Schlüssels nicht nutzen

![[Pasted image 20240223204551.png]]

## [[Integrität]]

- Erkennung von Modifikationen, Einfügungen, Löschungen, Umordnung, Duplikaten oder Wiedereinspielung von Daten 
- Wie kann Integrität gewährleistet werden? 
	- Modifikation, Einfügung, Löschung, Umordnung? 
		- Kryptographischer Hash-Wert über die Daten
	- Duplikate, Wiedereinspielung von Daten?  
		- Kryptographischer Hash-Wert + „gesicherte“ Sequenznummern und/oder Zeitstempel

### Integrität durch Verschlüsselung?
Ist Verschlüsselung ein Mechanismus zur Integritätssicherung?  
- In Allgemeinheit NEIN: „Blinde“ Modifikation des [[Ciphertext]] möglich 
- Abhängig vom Verschlüsselungsverfahren und den Daten kann es passieren, dass die Veränderung nicht automatisch erkannt wird 
- Auch mit semantischem Wissen kann Veränderung unbemerkt bleiben 
- Unwahrscheinliches aber mögliches Bsp.: Angreifer kippt Bit in verschlüsselter Überweisung; Entschlüsselung liefert 1000 statt 10 €

### Angriff auf Mechanismen zur Integritätssicherung 
Angreifer verändert unbemerkt Daten und Hash-Wert 

Deshalb: Hash-Wert und ggf. Sequenznummern müssen vor Veränderungen geschützt werden 
- Sequenznummern oder Timestamp als Teil der geschützten Daten werden (automatisch) durch Hash geschützt 
- Sequenznummern im Protokoll-Header sind gesondert (durch Hash) zu schützen 
- Hash selbst wird z.B. durch Verschlüsselung geschützt 
	- In diesem (Spezial-)Fall ist Verschlüsselung ein wichtiger Beitrag zur Integritätssicherung 
	- Bei verschlüsselten Hashes lassen sich „blinde“ Veränderungen am Chiffrentext automatisch erkennen 
	- Übertragen wird < m, E(H(m)) > 
	- Test beim Empfänger: Ist D(E(H(m))) gleich dem selbst berechneten Wert von H(m)?

# [[Authentisierung]]

# [[Autorisierung und Zugriffskontrolle]]

# [[Identifikation]]
