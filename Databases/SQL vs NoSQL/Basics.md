[SQL vs NoSQL](https://circleci.com/blog/sql-vs-nosql-databases/)
### SQL databases
The SQL language is an ANSI standard, with some dialects, like PL/SQL (in Oracle) and T-SQL (in Microsoft SQL Server). The advantage of writing ANSI-compatible SQL is that the scripts can be easily transferred to another SQL DB.

Popular SQL databases:
- Oracle
- MySQL
- Microsoft SQL Server
- PostgreSQL

### What does the "relational" term mean in the context of SQL

The term does not mean that we can define relationships between records using foreign keys. It comes from the mathematical concept of "relation", which is a collection of unique tuples. A tuple is an ordered collection of values.
In an SQL DB, a relation is represented as a table, with each tuple in the relation making up a row (commonly called a record) in the table. The data should be normalized by not storing it redundantly. In the past, storage was expensive, and normalizing it saved storage.

### SQL is robust

A DB with a schema has pros and cons. On the one hand, we always know the entities and values our app expects. On the other hand, it's not good at dealing with dynamic data.
Having a schema means the data can be validated. For example, the ID field must be unique and may not be NULL. We can also force a foreign key relationship, meaning that a record can't reference a record that doesn't exist in our DB.

---

### NoSQL databases

A common misconception about NoSQL databases is that the "No" means no SQL is used int the DB at all. The "No" stands for "not only".
Another source of confusion is that there is no single definition of a NoSQL DB. In fact, there are four broad categories of NoSQL DB:
- Document stores
- Graph databases
- Key-value stores
- Wide-column data stores

