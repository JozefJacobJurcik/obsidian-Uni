##### OPT (Optimalstrategie)
Lagert jeweils diejenige Seite mit dem größten Vorwärtsabstand aus, also diejenige Seite, die am längsten nicht mehr gebraucht wird. Dieses Verfahren verursacht theoretisch die wenigsten Seitenfehler, man sagt: Die geringsten Kosten. Praktisch ist es jedoch nur in Ausnahmefällen realisierbar. 
Als Approximation kann man den Vorwärtsabstand aufgrund bisheriger Beobachtungen schätzen. 
Wenn man dieses Verfahren im Nachhinein auf eine Abarbeitung von Prozessen anwendet, erhält man ein Maß, um die Güte anderer Verfahren bewerten zu können.

![[Pasted image 20240205180708.png]]

##### First In First Out (FIFO-Strategie)
Ordnet Seiten nach dem Alter, im Bedarfsfall wird die älteste Seite, d.h. die Seite, die sich bereits am längsten im Hauptspeicher befindet, ausgelagert.

![[Pasted image 20240205181001.png]]

##### Least Recently Used (LRU-Strategie)
Verdrängt Seiten nach dem Alter, d.h. die am längsten nicht mehr benutzte Seite wird aus dem Hauptspeicher ausgelagert. Die zugrundeliegende Idee besteht in der Lokalität, d.h. die Seite, die gerade gebraucht wurde, wird wahrscheinlich wieder gebraucht. Diese Strategie kommt der Optimalstrategie relativ nahe.

![[Pasted image 20240205181044.png]]

##### LFU (Least Frequently Used)
Bei diesem Verfahren soll diejenige Seite mit niedrigster Nutzungshäufigkeit ausgetauscht werden, so dass die am häufigsten genutzten Seiten im HS bleiben. Dazu muss jedoch für jeden Frame die Anzahl an Zugriffen verwaltet werden. Dieses Verfahren wird im wesentlichen in drei Varianten verwendet, die sich nach der Dauer der Zählung der Seitenzugriffe unterscheiden: 

Die Seitenzugriffe können gezählt werden 
	(a) seit Laden der Seite 
	(b) innerhalb der letzten h Zugriffe oder 
	(c) seit dem letzten Seitenfehler. Diese Variante ist nur bei starker Lokalität geeignet, d.h., wenn zwischen 2 Seitenfehlern ein hinreichend großer Abstand liegt. Dies ist etwa der Fall, wenn mehr Seiten genutzt werden, als Frames in den Hauptspeicher passen.

Bei diesem Verfahren ist jedoch wie auch bei LRU, bei jedem Speicherzugriff ein zusätzlicher Verwaltungsaufwand notwendig. Der Aufwand ist in der Praxis so groß, dass *das Verfahren kaum genutzt wird*.

##### Climb (Aufstieg bei Bewährung)
Hierbei steigt eine Seite bei jedem Aufruf eine Position höher, wenn sie bereits im Speicher vorhanden ist, d.h. sie tauscht ihre Position mit der vor ihr stehenden Seite.

![[Pasted image 20240205181425.png]]

##### Clock-Strategie:
Im Folgenden soll die Verwaltung von Seiten in einer zyklischen Liste betrachtet werden, die die Form einer Uhr darstellt. Der Zeiger der Uhr zeigt dabei auf die älteste Seite. Ein zusätzliches Bit pro Seite wird auch als Use Bit bezeichnet. Wird eine Seite das erste mal in ein Frame des Hauptspeichers geladen, so wird dieses Use Bit auf 1 gesetzt. Bei einer nachfolgenden Referenzierung erfolgt ebenfalls ein Setzen auf 1. Ist es nötig, eine Seite zu ersetzen, so wird der Speicher durchsucht, um ein Frame mit einem Use Bit = 0 zu finden. Trifft er dabei auf ein Frame mit einem Use Bit = 1, so wird dieses auf den Wert 0 zurückgesetzt. Haben alle Frames Use Bits = 0, so wird das erste Frame, auf das der Zeiger zeigt, für die Ersetzung gewählt. Haben andererseits alle Frames ein Use Bit = 1, so durchläuft der Zeiger einen kompletten Zyklus durch den Speicher, setzt alle Use Bits auf 0 und stoppt dann an der ursprünglichen Stelle. Das Frame wird genutzt, um eine Seite zu ersetzen, woraufhin der Zeiger um eins erhöht wird. Dieser Algorithmus ähnelt FIFO, allerdings mit der Ausnahme, dass Frames mit einem Use Bit = 1 durch den Algorithmus übersprungen werden.

![[Pasted image 20240205181531.png]]

![[Pasted image 20240205181549.png]]

