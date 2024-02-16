---
aliases: DDL
---
In the context of SQL, data definition or data description language (*DDL*) is a syntax for creating and modifying database objects such as tables, indices, and users. DDL statements are similar to a computer programming language for defining data structures, especially database schemas. Common examples of DDL statements include `CREATE`, `ALTER`, and `DROP`.

### CREATE TABLE statement

A commonly used _CREATE_ command is the _CREATE TABLE_ command. The typical usage is:

```SQL
CREATE TABLE [tableName] ( [column definitions] ) [tableParameters]
```

*The column definitions are:*
- A comma-separated list consisting of any of the following
- Column definition: `[column name] [data type] {NULL | NOT NULL} {column options}`
- [[Primary key]] definition: `PRIMARY KEY ( [comma separated column list] )`
- Constraints: `{CONSTRAINT} [constraint definition]`
- RDBMS (relational database management system) specific functionality

`[data type]` *examples:*
- CHAR(n) – String der festen Länge n 
- VARCHAR(n) – String variabler Länge (maximal n)
- INT – ganze Zahl (positive oder negative natürliche Zahl) 
- DECIMAL(n, m) – Festkommazahl mit n Stellen insgesamt, m davon hinter dem Komma 
- FLOAT – Gleitkommazahl, Kommazahl aber egal wie viele Stellen vor oder hinter dem Komma

`{CONSTRAINT}` *examples:* 
- NOT NULL – Attribut muss gefüllt werden 
- UNIQUE – Attribut darf nicht doppelt vorkommen 
- PRIMARY KEY – Attribut ist alleiniger Primärer Schlüssel 
- CHECK(b) – Attribut muss Bedingung b erfüllen (z.B. CHECK attribut$_i$ > 0) 
- DEFAULT x – Wenn nicht gefüllt, dann Default wert x 
- REFERENCES t(a) – Fremdschlüssel der auf Attribut a in Tabelle t verweist

`PRIMARY KEY(a1, … ak)` – Zusammengesetzter Primärere Schlüssel 
`FOREIGN KEY(a1, … ak) REFERENCES t(b1, … bk)` – Wenn mehrere Fremdschlüssel auf eine Tabelle verweisen 
See also: [[Foreign key]] , [[Primary key]] 

An example statement to create a table named _employees_ with a few columns is:

```sql
CREATE TABLE employees (
    id            INTEGER       PRIMARY KEY,
    first_name    VARCHAR(50)   not null,
    last_name     VARCHAR(75)   not null,
    mid_name      VARCHAR(50)   not null,
    dateofbirth   DATE          not null
);
```

Some forms of _CREATE TABLE DDL_ may incorporate DML ([[data manipulation language]])-like constructs, such as the `CREATE TABLE AS SELECT` (CTaS) syntax of SQL

### DROP statement

The `DROP` statement destroys an existing database, table, index, or view.

```sql
DROP objecttype objectname
```

For example, the command to drop a table named **employees** is:

```sql
DROP TABLE employees;
```

Wenn Tabelle *ABC* auf Tabelle *A* verweist, darf Tabelle *A* nicht zuerst gelöscht werden, da die Verweise dann in der Luft hängen (dangling references).

The `DROP` statement is distinct from the [DELETE](https://en.wikipedia.org/wiki/Delete_(SQL) "Delete (SQL)") and [TRUNCATE](https://en.wikipedia.org/wiki/Truncate_(SQL) "Truncate (SQL)") statements, in that _DELETE_ and _TRUNCATE_ do not remove the table itself. For example, a `DELETE` statement might delete some (or all) data from a table while leaving the table itself in the database, whereas a `DROP` statement removes the entire table from the database.

### ALTER statement

The `ALTER` statement modifies an existing database object.

```sql
ALTER objecttype objectname parameters
```

`ADD` (attribut datentyp) – Hinzufügen eines Attributs 
`MODIFY` (attribut neuer_datentyp) – Ändern eines Attributs 
`DROP` (attribut) – Löschen eines Attributs 
`ADD CONSTRAINT` (constraint_name constraint) – Hinzufügen eines constraint mit Name = constraint_name

For example, the command to add (then remove) a column named **bubbles** for an existing table named **sink** is:

```sql
ALTER TABLE sink ADD bubbles INTEGER;
ALTER TABLE sink DROP COLUMN bubbles;
```




