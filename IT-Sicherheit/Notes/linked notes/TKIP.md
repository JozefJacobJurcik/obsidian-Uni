---
aliases: Temporal Key Integrity Protocol
---
TKIP verwendet Schlüsselhierarchie, um kurzlebige Schlüssel zu erzeugen 

**Drei Hierarchiestufen** (von unten nach oben): 

1. Temporäre Schlüssel (Temporal Key, TK) 
	- In jede Richtung (AP zu STA, STA zu AP) eigene Schlüssel: 
		- zur Verschlüsselung (128 Bit) 
		- zur Integritätssicherung (64 Bit) 
	- Erneuerung des Schlüsselmaterials durch `rekey key` Nachricht 
	- `rekey key` Nachricht enthält Material, damit STA und AP neue Sitzungsschlüssel ableiten können; Nachricht verschlüsselt mit 
2. Pairwise Transient Key (PTK) 
	- Sichern die Übertragung temporärer Schlüssel
	- 1 Schlüssel zur Sicherung des Schlüsselmaterials 
	- 1 Schlüssel zur Sicherung der `rekey key` Nachricht
3. Pairwise Master Key (PMK) 
	- Höchster Schlüssel innerhalb der Hierarchie 
	- Erzeugt vom 802.1X Authentication Server und vom AP an STA weitergereicht 
	- Individuell pro Endgerät (AP) 
	- Falls 802.1X Setup „zu komplex“; Preshared Keys möglich (d.h. in der Praxis: Passwörter) 
	- Master Key wird zur Sicherung der key-encryption Keys genutzt 
	- Damit Aufbau einer Sitzungsstruktur möglich; von der Authentisierung über 802.1X bis 
		- Widerruf des Schlüssels 
		- Ablauf des Schlüssels 
		- STA verliert Kontakt zum AP 

**Achtung**: Kompromittierung des Master Key führt zur Kompromittierung der gesamten Hierarchie!