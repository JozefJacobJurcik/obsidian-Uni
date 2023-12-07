---

---

The *Bell–LaPadula Model (BLP)* is a state machine model used for enforcing access control in government and military applications.

The Bell–LaPadula model is an example of a model where there is no clear distinction between protection and security.

The Bell–LaPadula model focuses on data confidentiality and controlled access to classified information, in contrast to the Biba Integrity Model which describes rules for the protection of data integrity. In this formal model, the entities in an information system are divided into subjects and objects. The notion of a "secure state" is defined, and it is proven that each state transition preserves security by moving from secure state to secure state, thereby inductively proving that the system satisfies the security objectives of the model.  The Bell–LaPadula model is built on the concept of a state machine with a set of allowable states in a computer system. The transition from one state to another state is defined by transition functions. A system state is defined to be "secure" if the only permitted access modes of subjects to objects are in accordance with a security policy. To determine whether a specific access mode is allowed, the clearance of a subject is compared to the classification of the object (more precisely, to the combination of classification and set of compartments, making up the security level) to determine if the subject is authorized for the specific access mode. The clearance/classification scheme is expressed in terms of a lattice. The model defines one discretionary access control (DAC) rule and two mandatory access control (MAC) rules with three security properties:

- The Simple Security Property states that a subject at a given security level may not read an object at a higher security level.
- The * (Star) Security Property states that a subject at a given security level may not write to any object at a lower security level.
- The Discretionary Security Property uses an access matrix to specify the discretionary access control.

The transfer of information from a high-sensitivity document to a lower-sensitivity document may happen in the Bell–LaPadula model via the concept of trusted subjects. Trusted Subjects are not restricted by the Star-property. Trusted Subjects must be shown to be trustworthy with regard to the security policy.

The Bell–LaPadula security model is directed toward access control and is characterized by the phrase "write up, read down" (WURD). Compare the Biba model, the Clark–Wilson model, and the Chinese Wall model.

With Bell–LaPadula, users can create content only at or above their own security level (i.e. secret researchers can create secret or top-secret files but may not create public files; no write-down). Conversely, users can view content only at or below their own security level (i.e. secret researchers can view public or secret files, but may not view top-secret files; no read-up). 

### VL:

- *Objekte* werden Zuständigkeitsbereich Z(O) und Einstufung/Klassifikation E(O) zugeordnet, z.B. geheim, intern, ... 
- *Subjekte* werden Zuständigkeitsbereich Z(S) und Ermächtigung (Clearance) E(S) zugeordnet 
- „Zugriff“ auf vertrauliche Objekte erlaubt, wenn 
	- No-read up, d.h. E(S) höher E(O) 
	- No-write down (\*-property), d.h. E(S) kleiner E(O) 
	- Discretionary security matrix (Zugriffsmatrix) 
	- Zu Regel 2: (strong \*-property), d.h. write to the same security level only 

Dominance relation: 
	- security level A dominates level B, wenn E(A) > E(B) (z.B. top-secret dominates secret)