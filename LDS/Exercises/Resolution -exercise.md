
###### 1.
Zeigen Sie durch einen Resolutionsbeweis, dass die folgende Formel unerfüllbar ist $(\overline x_1 ∨\overline x_2) ∧ (\overline x_1 ∨ x_2) ∧ (\overline x_0 ∨ x_1 ∨ x_2) ∧ (x_0 ∨ x1) ∧ (\overline x_0 ∨\overline x_2)$ 

---
Wir befüllen die Sequenzenfolge erstmal mit den bekannten Klauseln 
0. $(\overline x_1 ∨ \overline x_2)$ 
1. $(\overline x_1 ∨ x_2)$ 
2. $(\overline x_0 ∨ x_1 ∨ x_2)$ 
3. $(x_0 ∨ x_1)$ 
4. $(\overline x_0 ∨ \overline x_2)$

und hängen dann herleitbare Klauseln an Dabei gibt es mehrere Lösungsmöglichkeiten, insbesondere auch unterschiedlich lange, etwa:

5. $(\overline x_1)$ aus (0,1) 
6. $(x_0)$ aus (3,5) 
7. $(\overline x_2)$ aus (4,6) 
8. $(x_1 ∨ x_2)$ aus (2,6) 
9. $(x_2)$ aus (8,5) 
10. $()$ aus (7,9) 

oder alternative Herleitung: 

5. $(\overline x_1)$ aus (0,1) 
6. $(\overline x_0 ∨ x_1)$ aus (2,4) 
7. $(x_1)$ aus (3,6) 
8. $()$ aus (5,7