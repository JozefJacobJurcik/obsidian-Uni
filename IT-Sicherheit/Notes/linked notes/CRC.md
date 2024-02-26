---
aliases: Cyclic Redundancy Check
---
A cyclic redundancy check (CRC) is an error-detecting code commonly used in digital networks and storage devices to *detect accidental changes to digital data*. Blocks of data entering these systems get a short *check value attached*, based on the *remainder of a polynomial division of their contents*. On retrieval, the calculation is repeated and, in the event the check values do not match, corrective action can be taken against data corruption. CRCs can be used for error correction.


Cyclic Redundancy Check (CRC) ist ein **Fehlererkennungcode** 

Entwickelt, um Übertragungsfehler u.a. in Ethernet zu erkennen 

Mathematische Grundlagen: 
- Bit-String wird als Polynom mit Koeffizienten 0 und 1 aufgefasst 
- Nachricht M wird interpretiert als Polynom M(x) 
- Berechnungen modulo 2; d.h. Addition und Subtraktion identisch mit XOR

