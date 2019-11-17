# DBMS
The database management system (DBMS) is the software that interacts with end users, applications, and the database itself to capture and analyze the data. The DBMS software additionally encompasses the core facilities provided to administer the database. The sum total of the database, the DBMS and the associated applications can be referred to as a "database system". Often the term "database" is also used to loosely refer to any of the DBMS, the database system or an application associated with the database.

# [What is transaction](https://www.tutorialspoint.com/sql/sql-transactions.htm)
A transaction is a unit of work that is performed against a database. Transactions are units or sequences of work accomplished in a logical order, whether in a manual fashion by a user or automatically by some sort of a database program.
A transaction begins with the first executable SQL statement. A transaction ends when it is committed or rolled back, either explicitly with a `COMMIT` or `ROLLBACK` statement or implicitly when a DDL statement is issued.

# Properties of Transactions
Transactions have the following four standard properties, usually referred to by the acronym ACID.
- **Atomicity** − ensures that all operations within the work unit are completed successfully. Otherwise, the transaction is aborted at the point of failure and all the previous operations are rolled back to their former state.
- **Consistency** − ensures that the database properly changes states upon a successfully committed transaction.
- **Isolation** − enables transactions to operate independently of and transparent to each other.
- **Durability** − ensures that the result or effect of a committed transaction persists in case of a system failure.

# Transaction Control
The following commands are used to control transactions.

- **COMMIT** − to save the changes.
- **ROLLBACK** − to roll back the changes.
- **SAVEPOINT** − creates points within the groups of transactions in which to ROLLBACK.
- **SET TRANSACTION** − Places a name on a transaction.

# Isolation
As we know that, in order to maintain consistency in a database, it follows ACID properties. Among these four properties (Atomicity, Consistency, Isolation and Durability) Isolation determines how transaction integrity is visible to other users and systems. It means that a transaction should take place in a system in such a way that it is the only transaction that is accessing the resources in a database system.
Isolation levels define the degree to which a transaction must be isolated from the data modifications made by any other transaction in the database system. A transaction isolation level is defined by the following phenomena –

- **Dirty Read** – A Dirty read is the situation when a transaction reads a data that has not yet been committed. For example, Let’s say transaction 1 updates a row and leaves it uncommitted, meanwhile, Transaction 2 reads the updated row. If transaction 1 rolls back the change, transaction 2 will have read data that is considered never to have existed.
- **Non Repeatable** read – Non Repeatable read occurs when a transaction reads same row twice, and get a different value each time. For example, suppose transaction T1 reads data. Due to concurrency, another transaction T2 updates the same data and commit, Now if transaction T1 rereads the same data, it will retrieve a different value.
- **Phantom Read** – Phantom Read occurs when two same queries are executed, but the rows retrieved by the two, are different. For example, suppose transaction T1 retrieves a set of rows that satisfy some search criteria. Now, Transaction T2 generates some new rows that match the search criteria for transaction T1. If transaction T1 re-executes the statement that reads the rows, it gets a different set of rows this time.
 
Based on these phenomena, The SQL standard defines four isolation levels :

- **Read Uncommitted** – Read Uncommitted is the lowest isolation level. In this level, one transaction may read not yet committed changes made by other transaction, thereby allowing dirty reads. In this level, transactions are not isolated from each other.
- **Read Committed** – This isolation level guarantees that any data read is committed at the moment it is read. Thus it does not allows dirty read. The transaction holds a read or write lock on the current row, and thus prevent other transactions from reading, updating or deleting it.
- **Repeatable Read** – This is the most restrictive isolation level. The transaction holds read locks on all rows it references and writes locks on all rows it inserts, updates, or deletes. Since other transaction cannot read, update or delete these rows, consequently it avoids non-repeatable read.
- **Serializable** – This is the Highest isolation level. A serializable execution is guaranteed to be serializable. Serializable execution is defined to be an execution of operations in which concurrently executing transactions appears to be serially executing.

| Isolation Level | Dirty reads | Non-repeatable reads | Phantoms |
|-----------------|-------------|----------------------|----------|
| Read Uncommited | May Occur | May Occur | May Occur |
| Read Committed | Don't Occur | May Occur | May Occur |
| Repeatable Read | Don't Occur | Don't Occur | May Occur |
| Serializable | Don't Occur | Don't Occur | Don't Occur |

# What is a Database Cursor?
A cursor is a temporary work area created in the system memory when a SQL statement is executed. A cursor contains information on a select statement and the rows of data accessed by it.

# [Difference Between MySQL and PostgreSQL](https://techdifferences.com/difference-between-mysql-and-postgresql.html)
Key Differences Between MySQL and PostgreSQL
1. The architectural difference between MySQL and PostgreSQL is that MySQL is a relational database management system whereas, PostgresSQL is object-relational database management system.
2. MySQL is supported by the following operating system, Windows, Mac OS X, Linux, BSD, UNIX, z/OS, Symbian, AmigaOS. However, the PostgreSQL  is supported by Windows, Mac OS X, Linux and BSD but not by UNIX, z/OS, Symbian, AmigaOS.
3. MySQL is the product of Oracle Corporation while PostgreSQL is a product of Global Development Group.
4. My SQL programming language is not extensible whereas, the programming language PostgreSQL is highly extensible.
5. In MySQL, the phpMyAdmin tool provides GUI and SQL interface. However, in PostgreSQL, the pgAdmin tool provides GUI and SQL interface.
6. In MySQL, Mysqldump, and XtraBackup tools provides backup. On the other hands, PostgresSQL provides complete backup online.
7. MySQL provides temporary tables but does not provide materialized view. However, PostgreSQL provides temporary table and also the materialized view.
8. MySQL does not offers data domain object whereas, PostgreSQL provide data domain object.

# [What is VACUUM in PostgreSQL](https://www.postgresql.org/docs/12/sql-vacuum.html)
VACUUM — garbage-collect and optionally analyze a database

# [What is EXPLAIN](https://www.postgresql.org/docs/12/sql-explain.html)
EXPLAIN — show the execution plan of a statement
