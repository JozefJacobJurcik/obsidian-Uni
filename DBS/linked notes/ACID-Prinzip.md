---
klausur: 3
---
more here: [[DBS Skript.pdf#page=401|Skript, page 401]]
##### **Atomicity** (Atomarität) 
Der Effekt einer Transaktion kommt entweder ganz oder gar nicht zum Tragen.

##### **Consistency** (Konsistenz, Integritätserhaltung) 
Durch eine Transaktion wird ein konsistenter Datenbankzustand wieder in einen konsistenten Datenbankzustand überführt. 
	**referenzieller Integrität** : Zu jedem Attributwert in der abhängigen Relation muss es auch den entsprechenden Schlüsselwert in der referenzierten Relation geben! 
	-> Keine dangling references

##### **Isolation** (Isoliertheit, logischer Einbenutzerbetrieb) 
Innerhalb einer Transaktion nimmt ein Benutzer Änderungen durch andere Benutzer nicht wahr. 

##### **Durability** (Dauerhaftigkeit, Persistenz) 
Der Effekt einer abgeschlossenen Transaktion bleibt dauerhaft in der Datenbank erhalten. 

##### Weitere Forderung: 
TA muss in endlicher Zeit bearbeitet werden können