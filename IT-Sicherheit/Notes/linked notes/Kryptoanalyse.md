---
aliases: Kryptanalyse, cryptanalysis
---

Wissenschaft von den Methoden zur Entschlüsselung, **ohne** im Besitz des Schlüssels zu sein (Angriffe auf kryptographische Verfahren)

### Klassen kryptanalytischer Angriffe: 

- [[Brute Force]]; exhaustive search: vollständiges Durchsuchen des Schlüsselraums
- *Angriff auf Chiffren* ([[ciphertext only attack]]): Dem Analytiker stehen mehrere Chiffren zur Verfügung. Ziel: Schlüssel und/oder Klartext berechnen 
- *Bekannter Klartext* ([[known-plaintext attack]]): Analytiker kennt Klartext-/Chiffren Kombinationen, die mit selbem Schlüssel verschlüsselt wurden. *Ziel:* Schlüssel brechen oder Algorithmus finden, der jede mit dem Schlüssel verschlüsselte Nachricht entschlüsseln kann. 
- *Gewählter Klartext* ([[chosen-plaintext attack]]): Analytiker kann selber Klartexte wählen und diese verschlüsseln lassen. 
- Gewählte Chiffre ([[chosen-ciphertext attack]]): Angreifer kann sich zu ausgewählten Chiffren den Klartext berechnen lassen. 

Weitere Informationen: Vgl. F.L. Bauer: Entzifferte Geheimnisse

##### Aufwand für Brute-Force-Angriff

Annahmen, unter denen [[Brute Force]]-Angriff sinnvoll erscheint: 
- Schlüssel ist zufällig gewählt, d.h. alle Schlüssel sind gleich wahrscheinlich 
- Es gibt kein alternatives, schneller Erfolg versprechendes Verfahren

Die Schlüssellänge sei 128 Bit 
Ein Rechner schaffe 3.000.000.000 Schlüssel pro Sekunde 
Der Angreifer habe 1.000 Rechner zur Verfügung 
Schlüsselraum S = 2128 ≈ 3,4⋅1038 
1 Jahr hat 31.557.600 Sekunden 
Maximaldauer D in Jahren: 
	D = S / (3.000.000.000 ⋅ 1.000 ⋅ 31.557.600) = 3,6 ⋅ 1018 Jahre 
	(im Durchschnitt also 1,8 ⋅ $10^{18}$ Jahre) 
Bei Schlüssellänge 256 Bit: D = 1,2 ⋅ $10^{57}$ Jahre