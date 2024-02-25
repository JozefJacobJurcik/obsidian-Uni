---
aliases: WiFi Protected Access
---
See also: [[WPA2]] [[WPA3]]

WPA zur Verbesserung der Sicherheit eingeführt 
[[WEP]]-Hardware sollte weiter benutzbar bleiben 

[[Vertraulichkeit]]
- Temporal Key Integrity Protocol ([[TKIP]]) 
- Rekeying-Mechanismus zum automatischen Wechseln der Schlüssel 
- Hierarchie von Schlüsseln 
 
[[Integrität]]ssicherung 
- [[TKIP]] Message Integrity Code - MIC (genannt „Michael“); zur Unterscheidung von MAC (Media Access Control) 
- Mit Schlüssel parametrisierte kryptographische Hash-Funktion 
- Verbessert ungeeigneten CRC-Mechanismus von [[WEP]] 
[[Authentisierung]] 
- Nach wie vor Möglichkeit für Pre-Shared Key (PSK) 
- Bietet aber auch 802.1X (insb. in großen IT-Infrastrukturen genutzt)

### WPA und TKIP: Sicherheit
Bei Verwendung von Pre Shared Keys (PSK) hängt die Sicherheit stark von der Stärke des Passworts ab 

Angriff mit [[Rainbow Table]]s (seit 2004) 

Angriff auf PRF Funktion der Schlüsselverteilung (August 2008) 
- nutzt GPUs anstatt CPUs 
- Entwickelt auf NVIDIA-CUDA (Compute Unified Device Architecture) 
	- Compiler und Entwicklungsumgebung 
	- nativer Zugriff auf GPUs auf Grafikkarten 
	- dadurch massive Parallelisierung möglich 
	- damit Speedup von Faktor 30 und mehr möglich 
	- Zeit für „Raten“ eines Passwortes reduziert sich auf 2-3 Tage

##### WPA packet spoofing and decryption
In 2013, Mathy Vanhoef and Frank Piessens significantly improved upon the WPA-TKIP attacks of Erik Tews and Martin Beck. They demonstrated how to inject an arbitrary number of packets, with each packet containing at most 112 bytes of payload. This was demonstrated by implementing a port scanner, which can be executed against any client using WPA-TKIP. Additionally, they showed how to decrypt arbitrary packets sent to a client. They mentioned this can be used to hijack a TCP connection, allowing an attacker to inject malicious JavaScript when the victim visits a website. In contrast, the Beck-Tews attack could only decrypt short packets with mostly known content, such as ARP messages, and only allowed injection of 3 to 7 packets of at most 28 bytes. The Beck-Tews attack also requires quality of service (as defined in 802.11e) to be enabled, while the Vanhoef-Piessens attack does not. Neither attack leads to recovery of the shared session key between the client and Access Point. The authors say using a short rekeying interval can prevent some attacks but not all, and strongly recommend switching from TKIP to AES-based CCMP.

Halvorsen and others show how to modify the Beck-Tews attack to allow injection of 3 to 7 packets having a size of at most 596 bytes. The downside is that their attack requires substantially more time to execute: approximately 18 minutes and 25 seconds. In other work Vanhoef and Piessens showed that, when WPA is used to encrypt broadcast packets, their original attack can also be executed. This is an important extension, as substantially more networks use WPA to protect broadcast packets, than to protect unicast packets. The execution time of this attack is on average around 7 minutes, compared to the 14 minutes of the original Vanhoef-Piessens and Beck-Tews attack.

The vulnerabilities of TKIP are significant because WPA-TKIP had been held before to be an extremely safe combination; indeed, WPA-TKIP is still a configuration option upon a wide variety of wireless routing devices provided by many hardware vendors. A survey in 2013 showed that 71% still allow usage of TKIP, and 19% exclusively support TKIP.

##### WPA-Schlüssel in der Cloud brechen (Jan. 2011) 
Angriff auf WPA-Schlüssel (Pre-Shared Keys) über die Elastic Compute Cloud (EC2) Infrastruktur von Amazon 
- Prinzipiell nichts Neues, nutzt nun aber die Cluster GPU Instances 
- Wörterbuch-Angriff mit 70 Millionen Wörtern; pro Amazon-Maschine rund 50.000 Wörter pro Sekunde 
- Alternative z.B. www.wpacracker.com: $17 für Wörterbuch-Angriff mit mehr als 250 Millionen Wörtern auf 400 „herkömmlichen“ Amazon CPU Instances

![[Pasted image 20240224233246.png]]

