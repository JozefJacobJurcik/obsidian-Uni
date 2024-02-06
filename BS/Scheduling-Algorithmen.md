### Nicht-preemptive

##### First Come First Served (FCFS)
First Come First Served (FCFS), auch bekannt als First In First Out (FIFO), ist der einfachste nicht-preemptive Scheduling-Algorithmus. Ein rechenbereiter Prozess stellt sich in der Ready-Queue einfach hinten an, und bei frei werdendem Prozessor kann der jeweils älteste Prozess in den Zustand “running” überführt werden.

![[Pasted image 20240205123803.png]]

##### Shortest Process Next (SPN) / Shortest Job First (SJF)
Shortest Process Next (SPN), auch bekannt als Shortest Job First (SJF), gehört zu den nonpreemptiven Modi. Dabei wird jeweils der Auftrag ausgewählt, bei dem die kürzeste Abarbeitungszeit erwartet wird.

![[Pasted image 20240205123918.png]]

SJF ist optimal bei nicht-preemptiven Scheduling-Algorithmen bzgl. der mittleren Verweildauer.

### Preemptive Scheduling-Algorithmen

##### Shortest Remaining Processing Time (SRPT)
Diese Strategie wird in mancher Literatur auch nur als SRT bezeichnet und ist die preemptive Variante zu SPN/SJF. Zu jedem beliebigen Zeitpunkt kann der Prozess unterbrochen werden, der aktuell dem Prozessor zugeteilt ist. Dies erfolgt mit dem Ziel, dem Prozessor einen anderen Prozess zuzuweisen, der eine kürzere Restbedienzeit hat. Insbesondere heißt dies: wenn ein neuer Auftrag ankommt, dann muss geprüft werden, ob dieser Auftrag kürzer ist als der gerade in Abarbeitung befindliche.

![[Pasted image 20240205124631.png]]

##### Round Robin

Round Robin (RR) nutzt Uhren-basierte Unterbrechungen, d.h. in periodischen Intervallen werden Prozesse in ihrer Abarbeitung unterbrochen, bis sie wieder ein Zeitquantum Q für die Abarbeitung erhalten. Dieses Verfahren wird auch als Zeitscheibenverfahren bezeichnet. Als problematisch beim Design des Verfahren erweist sich hierbei die Wahl der Länge einer Zeitscheibe. Ist die Zeitscheibe zu klein, dann ist der Aufwand für das Dispatching zu groß - ist sie zu groß, kommt FCFS zustande. Dies ist dann der Fall, wenn Q mindestens so groß ist wie der längste Prozess, der abgearbeitet werden soll.

Die Wirkungsweise von RR kann an folgendem Beispiel mit Q = 1 nachvollzogen werden

![[Pasted image 20240205124757.png]]

RR ist bezüglich der mittleren Verweildauer besser als FCFS, aber schlechter als SJF und als SRPT. Im Gegensatz zu SJF und SRPT ist RR jedoch fair in der Hinsicht, dass kein Verhungern vorkommt und praktisch implementierbar

### Multilevel Feedback Queueing

![[Pasted image 20240205125049.png]]

