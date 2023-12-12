---
aliases: DDoS, DoS
---

In computing, a **denial-of-service attack (DoS attack)** is a cyber-attack in which the perpetrator seeks to make a machine or network resource unavailable to its intended users by temporarily or indefinitely disrupting services of a host connected to a network. Denial of service is typically accomplished by *flooding* the targeted machine or resource with superfluous requests in an attempt to overload systems and prevent some or all legitimate requests from being fulfilled.

In a **distributed denial-of-service attack (DDoS attack)**, the incoming traffic flooding the victim originates from many different sources. More sophisticated strategies are required to mitigate this type of attack; simply attempting to block a single source is insufficient as there are multiple sources.

##### Ablauf DDoS:
1. Intruder identifiziert Systeme, die kompromittiert werden können. Festlegung eines Masters, der im folgenden Schritt versucht, weitere Maschine zu kompromittieren, um dort DoS-Tools zu installieren. 
2. Intruder gibt Start-Kommando und Informationen über Ziel des Angriffs an Master, der diese Informationen weiterverteilt. 
3. Zum festgelegten Zeitpunkt startet der DoS-Angriff

##### Lösung:
1. Overprovisioning / Load Balancing 
2. Überwachung offener Ports 
3. Sicherheitsupdates regelmäßig/zeitnah einspielen 
4. Monitoring & Anomaly-based Intrusion Prevention (Überschreitung Schwellenwerte, Verhältnis ein-/ausgehendes Datenvolumen) 
5. Blackholing / Null route → „burn the village in order to save it“



![[SMURF]]

![[DNS Amplification Attack]]

![[SYN flood]]
