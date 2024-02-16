---
aliases: Fremdschlüssel
---
A **foreign key** is a set of attributes in a table that refers to the [[Primary key]] of another table, linking these two tables. In the context of relational databases, a *foreign key* is subject to a inclusion dependency constraint that the tuples consisting of the foreign key attributes in one relation, $R$, must also exist in some other (not necessarily distinct) relation, $S$; furthermore that those attributes must also be a *candidate key* in $S$.

In other words, a **foreign key** is a set of attributes that references a *candidate key*. For example, a table called `TEAM` may have an attribute, `MEMBER_NAME`, which is a *foreign key referencing a candidate key*, `PERSON_NAME`, in the `PERSON` table. Since `MEMBER_NAME` is a foreign key, any value existing as the name of a member in `TEAM` must also exist as a person's name in the `PERSON` table; in other words, every member of a `TEAM` is also a `PERSON`.

Important points to note:
- The reference relation should already be created.
- The referenced attribute must be a part of primary key of the referenced relation.
- Data type and size of referenced and referencing attribute must be same.