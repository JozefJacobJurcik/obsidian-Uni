---
aliases: natural key, surrogate key
---

In the [[Das Relationale Modell|relational model]] of databases, a **primary key** is a specific choice of a minimal set of attributes (columns) that uniquely specify a tuple (row) in a relation (table). Informally, a primary key is *"which attributes identify a record,"* and in simple cases constitute a single attribute: a unique ID. More formally, a primary key is a choice of candidate key (a minimal superkey); any other candidate key is an **alternate key**.

A **primary key** may consist of real-world observables, in which case it is called a **natural key**, while an attribute created to function as a key and not used for identification outside the database is called a **surrogate key**. For example, for a database of people (of a given nationality), time and location of birth could be a natural key. National identification number is another example of an attribute that may be used as a natural key. 

See also: [[Foreign key]] 