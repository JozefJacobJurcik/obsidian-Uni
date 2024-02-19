---
klausur: 3
---
## SQL Anfragen
...  bestehen immer aus: 
1. `SELECT` … 
2. `FROM`…

#### `SELECT` 
- wird zum Auswählen (Projizieren) von Attributen/Spalten verwendet 
- Kommt immer als erstes

**Optionen:** 
1. `SELECT *` -> Anzeigen aller Attribute/Spalten 
2. `SELECT attr_1, …, attr_n` -> Anzeigen der angegebenen Attribute/Spalten 
3. `SELECT DISTINCT attr_1, …, attr_n` -> wie 2. nur mit Duplikat Eliminierung

#### `FROM` 
- wird zum Auswählen von Relationen und Ausführen von Joins verwendet 
- Kommt immer nach `SELECT` 

**Optionen**: 
1. Relation_1, …, Relation_n oder Relation_1 `CROSS JOIN` Relation_n 
	-> Kreuzprodukt der angegebenen Relationen 
	
2. Relation_1 `NATURAL JOIN` Relation_2 … `NATURAL JOIN` Relation_n 
	-> Natural Join (alle gleichnamigen Attribute) der angegebenen Relationen 
	-> Nur eine Kopie der gleichnamigen Attribute bleibt 
	-> Wenn keine gleichnamigen Attribute, dann Kreuzprodukt
	
3. Relation_1 `JOIN` Relation_2 `ON` Relation_1.attribut_i `Θ` Relation_2.attribut_j 
	-> Theta Join mit Θ ∈ =, ≤, <, >, ≥, ≠ 
	-> Wenn Θ ∈ {=}, dann Equi Join (Attribute werden nicht eliminiert) 
	
4. Relation_1 `JOIN` Relation_2 `USING` (attribut_i) 
	-> attribut_i muss bei beiden Relationen gleich heißen 

-  Es können auch immer mehrere Joins kombiniert werden 
	-> Dann aber immer Klammern um die Joins setzen
##### Unterabfragen
In `FROM` können Unterabfragen verwendet werden 
- Ergebnis der Unterabfrage ist wie eine Relation 
- **WICHTIG**: Ergebnis braucht ein „alias“: `(SELECT … FROM … )` **as** `xy` • Alias darf nicht der Name einer existierenden Relation/Attributes/SQL-Befehls sein (z.B. (select … From … ) as count)

#### `WHERE`
In `WHERE` kann man Bedingungen an Tupel aus der aus `FROM` resultierenden Relation stellen (Selektion) **Optionen (Beispiele):** 
1. Relation_1.attr_i `Θ` Relation_2.attr_j 
	-> mit Θ ∈ =, ≤, <, >, ≥, ≠ 
	-> Gleicher Datentyp von attr_i und attr_j 
2.  attr_j = 5 
3. attr_k = „Hallo“ 

=> Verknüpfung mehrerer Bedingungen mit `AND` und `OR` möglich (Achte auf Klammersetzung)

`DISTINCT` soll nur verwendet werden, falls es notwendig ist

##### Unterabfragen
Deutlich gängiger sind Unterabfragen in der `WHERE` Klausel 
- Attribute können mit Ergebnis der Unterabfrage verglichen werden 
- Nachbildung des Existenzquantors möglich (aber nicht des Allquantors) 
	-> Allquantor kann durch Negation in Existenzquantor umgewandelt werden

###### Vergleich mit EINEM Wert

```sql
WHERE ausdruck 𝜃 (SELECT … FROM …) (𝜃 ∈ {<, ≤, ≥, >, =, ≠})
```

**Aufpassen**: Unterabfrage darf nur einen einzelnen Wert (ein Attribut von einem Tupel) liefern. Das Ergebnis der Unterabfrage wird mit dem Ausdruck verglichen.

**Bsp. :**
```sql
SELECT tnr
FROM LTP
WHERE Inr = (SELECT Inr FROM L WHERE Iname = "MEIER");
```

###### Attribut in Liste enthalten

```sql
WHERE ausdruck [NOT] IN (SELECT … FROM …)
```

Ausdruck gleicht keinem bzw. Mindestens einem Wert der Unterabfrage 
**Aufpassen**: Unterabfrage darf mehrere Tupel aber nur ein Attribut enthalten

```sql
SELECT DISTINCT tnr
FROM LTP
WHERE Inr IN (SELECT Inr FROM L WHERE Iname LIKE "m%");
```

###### Vergleich mit mindestens einem Wert muss stimmen

```sql
WHERE ausdruck 𝜃 ANY | SOME (SELECT … FROM …)
```

Bedingung muss für mindestens einen Wert der Unterabfrage erfüllt sein 
< ANY: weniger als das Maximum 
\> ANY: mehr als das Minimum 
= ANY: die selbe Bedeutung wie `IN`

```sql
SELECT tname
FROM T
WHERE gewicht < ANY (SELECT gewicht FROM T)
```

###### Vergleich mit allen Werten muss stimmen

```sql
WHERE ausdruck 𝜃 ALL (SELECT … FROM …)
```

Bedingung muss für alle Werte der Unterabfrage erfüllt sein 
< ALL: weniger als das Minimum 
<= ALL: weniger oder gleich dem Minimum -> Minimum bestimmen 
\>= ALL: mehr oder gleich dem Maximum -> Maximum bestimmen

```sql
SELECT tname, gewicht
FROM T
WHERE gewicht <= ALL (SELECT gewicht FROM T)
```

###### Existenzquantor simulieren

```sql
WHERE [NOT] EXISTS (SELECT … FROM … )
```

Bedingung ist erfüllt, genau dann wenn Ergebnis der Subquery \[leer] nicht leer ist 
- Meistens in Folge mit Koppelung aus Relationen aus der Außenabfrage

```sql
SELECT *
FROM P AS p1
WHERE EXISTS (SELECT * FROM LTP AS ltp1 WHERE p1.pnr = ltp1.pnr AND ltp1.tnr = "T1")
```
-> Alle Projektinformationen wo das Teil T1 geliefert wird

### Änderungsoperationen

```sql
INSERT INTO Relation [(attr_1, …, attr_n)] 
VALUES (value_1, …, value_n), (value_2, …, value_m)
``` 
	
- Erlaubt einfügen von nicht vollständigen Tupeln
- Erlaubt einfügen von mehreren Tupeln auf einmal

```sql
UPDATE Relation 
SET attr_1=wert_1 [, attr_2=wert_2 …] 
[WHERE Bedingung]
```

- Erlaubt das aktualisieren von bestimmten Tupeln (Bedingung) 
- Bedingung ist optional, wird aber fast immer verwendet 
- Bedingung in WHERE ist gleich zu den Anfragen

```sql
DELETE FROM Relation 
[WHERE Bedingung] 
```
- Löscht alle Tupel, die Bedingung erfüllen 
- Bedingung ist optional wird aber eigentlich immer verwendet

- Die Fremdschlüssel wurden mit on delete cascade definiert 
	-> Tupel die auf Primärschlüssel referenzieren werden automatisch gelöscht wenn der referenzierte Primärschlüssel gelöscht wird 
-  Manchmal ist die Reihenfolge der Operationen wichtig 
- Datenbank entspricht der bekannten Beispielausprägung

### Sortierung der Ergebnisrelation

```sql
ORDER BY attribut_1 [, attribute_2, …] ASC | DESC
```

Legt die aufsteigende / absteigende Reihenfolge fest, in der die Ergebniszeilen ausgegeben werden
	-> wenn sich zwei Tupel in attribut_1 Gleichen werden sie nach attribute_2 sortiert

### Gruppierung
Wird benutzt um Informationen über Gruppen in der Relation zu erhalten wie z.B.:

- `AVG(x)` - Mittelwert 
- `COUNT(x)` - Anzahl der nicht-NULL Werte 
- `COUNT(DISTINCT x)` - Anzahl der verschiedenen nicht-NULL Werte 
- `MAX(x)` - Maximum 
- `MIN(x)` - Minimum 
- `SUM(x)` - Summe aller Werte

Diese Funktionen nennt man **Aggregatsfunktionen**

```sql
… GROUP BY attribute_1 [, attribute_2, …] 
```

Teilt die Zeilen einer Tabelle in Gruppen auf 
- **WICHTIG**: Alle Attribute in der `SELECT`-Liste, die keine Aggregatfunktion sind, müssen in der `GROUP BY`-Liste enthalten sein 

```SQL
… HAVING ausdruck 
```

In der `WHERE`-Klausel können keine Aggregatsfunktionen verwendet werden 
- Wenn man Bedingungen auf Gruppen definieren will, benutzt die `HAVING`-Klausel

```sql
SELECT Inr, Iname, SUM(menge) as teile_ gesamt
FROM LTP NATURAL JOIN L
GROUP BY Inr, Iname
HAVING teile_gesamt >= 1000;
```

![[Pasted image 20240218114912.png]]
# Syntax

The most common operation in SQL, the query, makes use of the declarative `SELECT` statement.  `SELECT` retrieves data from one or more tables, or expressions. Standard `SELECT` statements have no persistent effects on the database. Some non-standard implementations of `SELECT` can have persistent effects, such as the `SELECT INTO` syntax provided in some databases.

Queries allow the user to describe desired data, leaving the database management system to carry out planning, optimizing, and performing the physical operations necessary to produce that result as it chooses.

A query includes a list of columns to include in the final result, normally immediately following the `SELECT` keyword. An asterisk ("`*`") can be used to specify that the query should return all columns of the queried tables. `SELECT` is the most complex statement in SQL, with optional keywords and clauses that include:

- The `FROM` clause, which indicates the table(s) to retrieve data from. The `FROM` clause can include optional `JOIN` subclauses to specify the rules for joining tables.
- The `WHERE` clause includes a comparison predicate, which restricts the rows returned by the query. The `WHERE` clause eliminates *all rows* from the result set where the comparison predicate does not evaluate to True.
- The `GROUP BY` clause projects rows having common values into a smaller set of rows. `GROUP BY` is often used in conjunction with SQL aggregation functions or to eliminate duplicate rows from a result set. The `WHERE` clause is applied before the `GROUP BY` clause.
- The `HAVING` clause includes a predicate used to filter rows resulting from the `GROUP BY` clause. Because it acts on the results of the `GROUP BY` clause, aggregation functions can be used in the `HAVING` clause predicate.
- The `ORDER BY` clause identifies which column/s to use to sort the resulting data, and in which direction to sort them (ascending or descending). Without an `ORDER BY` clause, the order of rows returned by an SQL query is undefined.
- The `DISTINCT` keyword  eliminates duplicate data.
- The `OFFSET` clause specifies the number of rows to skip before starting to return data.
- The `FETCH FIRST` clause specifies the number of rows to return. Some SQL databases instead have non-standard alternatives, e.g. `LIMIT`, `TOP` or `ROWNUM`.

The clauses of a query have a particular order of execution, which is denoted by the number on the right hand side. It is as follows:

|   |   |
|---|---|
|`SELECT <columns>` |5.|
|`FROM <table>` |1.|
|`WHERE <predicate on rows>` |2.|
|`GROUP BY <columns>` |3.|
|`HAVING <predicate on groups>` |4.|
|`ORDER BY <columns>` |6.|
|`OFFSET`|7.|
|`FETCH FIRST`|8.|

The following example of a `SELECT` query returns a list of expensive books. The query retrieves all rows from the _Book_ table in which the _price_ column contains a value greater than 100.00. The result is sorted in ascending order by _title_. The asterisk (\*) in the _select list_ indicates that all columns of the _Book_ table should be included in the result set.

```sql
SELECT *
 FROM  Book
 WHERE price > 100.00
 ORDER BY title;
```

The example below demonstrates a query of multiple tables, grouping, and aggregation, by returning a list of books and the number of authors associated with each book.

```sql
SELECT Book.title AS Title,
       count(*) AS Authors
 FROM  Book
 JOIN  Book_author
   ON  Book.isbn = Book_author.isbn
 GROUP BY Book.title;
```

Example output might resemble the following:

|Title         |         Authors |
|---------------------- |-------|
|SQL Examples and Guide |4
|The Joy of SQL    |     1
|An Introduction to SQL |2
|Pitfalls of SQL    |    1

Under the precondition that _ISBN_ is the only common column name of the two tables and that a column named _title_ only exists in the _Book_ table, one could re-write the query above in the following form:

```sql
SELECT title,
       count(*) AS Authors
 FROM  Book
 NATURAL JOIN Book_author
 GROUP BY title;
```

*However, many vendors* either do not support this approach, or require certain column-naming conventions for natural joins to work effectively.

SQL includes operators and functions for calculating values on stored values. SQL allows the use of expressions in the _select list_ to project data, as in the following example, which returns a list of books that cost more than 100.00 with an additional _sales_tax_ column containing a sales tax figure calculated at 6% of the _price_.

```sql
SELECT isbn,
       title,
       price,
       price * 0.06 AS sales_tax
 FROM  Book
 WHERE price > 100.00
 ORDER BY title;
```
##### Subqueries

Queries can be nested so that the results of one query can be used in another query via a [relational operator](https://en.wikipedia.org/wiki/Relational_operator "Relational operator") or aggregation function. A nested query is also known as a _subquery_. While joins and other table operations provide computationally superior (i.e. faster) alternatives in many cases, the use of subqueries introduces a hierarchy in execution that can be useful or necessary. In the following example, the aggregation function `AVG` receives as input the result of a subquery:

```sql
SELECT isbn,
       title,
       price
 FROM  Book
 WHERE price < (SELECT AVG(price) FROM Book)
 ORDER BY title;
```

A subquery can use values from the outer query, in which case it is known as a *correlated subquery*.

Since 1999 the SQL standard allows `WITH` clauses for subqueries, i.e. named subqueries, usually called common table expressions (also called subquery factoring). CTEs can also be recursive by referring to themselves; the resulting mechanism allows tree or graph traversals (when represented as relations), and more generally fixpoint computations. 