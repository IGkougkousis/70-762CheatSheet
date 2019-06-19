# Exam 70-762: Developing SQL Databases Cheat Sheet

Related questions from the pdf are in superscript like this<sup>1</sup>.

Questions with the same scenario: `TODO`

## Tables

Links

- [Tables](https://docs.microsoft.com/en-us/sql/relational-databases/tables/tables?view=sql-server-2017)

Related Questions: <sup>80</sup>

## Options

- <sup>78</sup> **WITH ENCRYPTION**: Converts the original text of the CREATE PROCEDURE statement to an obfuscated format and prevents it from being published as part of SQL Server replication.
- **SCHEMABINDING**: Ensures that tables that are referenced by a procedure cannot be dropped or altered.
- **VIEW_METADATA**: (Applies to views). Specifies that the instance of SQL Server will return to the DB-Library, ODBC, and OLE DB APIs the metadata information about the view, instead of the base table or tables, when browse-mode metadata is being requested for a query that references the view.
- **CHECK OPTION**: (Applies to views). Forces all data modification statements executed against the view to follow the criteria set within select_statement. When a row is modified through a view, the WITH CHECK OPTION makes sure the data remains visible through the view after the modification is committed.

## Indexes

Links:

- [Clustered and Nonclustered Indexes Described](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/clustered-and-nonclustered-indexes-described?view=sql-server-2017)
- [SQL Server Index Architecture and Design Guide](https://docs.microsoft.com/en-us/sql/relational-databases/sql-server-index-design-guide?view=sql-server-2017)
- [CREATE INDEX (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-index-transact-sql?view=sql-server-2017)

Related Questions: <sup>62,63,64,70,72,77,81</sup>

## Triggers

Related Questions: <sup>68,78</sup>

- FOR UPDATE

## Transactions

Related Questions: <sup>65,66</sup>

- **XACT_STATE** Is a scalar function that reports the user transaction state of a current running request. XACT_STATE indicates whether the request has an active user transaction, and whether the transaction is capable of being committed. **XACT_ABORT** must be ON to rollback transactions. Values:
  - 1: The current request has an active user transaction. The request can perform any actions, including writing data and committing the transaction.
  - 0: There is no active user transaction for the current request.
  - -1: The current request has an active user transaction, but an error has occurred that has caused the transaction to be classified as an uncommittable transaction.
- a

## Functions / Stored Procedures

Links:

- [CREATE FUNCTION (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-function-transact-sql?view=sql-server-2017)
- [User Defined Functions and Stored Procedures](https://docs.microsoft.com/en-us/sql/analysis-services/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures?view=sql-server-2017)

Related Questions: <sup>73,74,75,79</sup>

## Constraints

Related Questions: <sup>67, 69</sup>

- **CHECK**: The CHECK constraint is used to limit the value range that can be placed in a column. If you define a CHECK constraint on a single column it allows only certain values for this column. If you define a CHECK constraint on a table it can limit the values in certain columns based on values in other columns in the row. Examples:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int CHECK (Age>=18)
);
```

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255),
    CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
);
```

```sql
ALTER TABLE Persons
ADD CHECK (Age>=18);
```

- **Cascading Referential Integrity**: Are the foreign key constraints which tell SQL Server to perform certain actions whenever a user attempts to delete or update a primary key to which an existing foreign keys point. Default: NO ACTION. Other available actions: SET NULL, CASCADE, SET DEFAULT

## Data types <sup></sup>

Related Questions: <sup>59,60,61</sup>

Integers:

| Data Type | Range | Storage |
|-----------|-------|---------|
|BIGINT|-2<sup>63</sup>(-9,223,372,036,854,775,808) to 2<sup>63</sup>-1 (9,223,372,036,854,775,807)|8 Bytes|
|INT|-2<sup>31</sup> (-2,147,483,648) to 2<sup>31</sup>-1 (2,147,483,647)|4 Bytes|
|SMALLINT|-2<sup>15</sup> (-32,768) to 2<sup>15</sup>-1 (32,767)|2 Bytes|
|TINYINT|0 to 255|1 Byte|

Date/Time: <sup>59,60,61</sup>

- **datetime** Defines a date that is combined with a time of day with fractional seconds that is based on a 24-hour clock. *Use the time, date, datetime2 and datetimeoffset data types for new work. These types align with the SQL Standard*.
- **time** Defines a time of a day. The time is without time zone awareness and is based on a 24-hour clock.
- **date** Defines a date in SQL Server. Default string literal format: YYYY-MM-DD.
- **datetime2** Defines a date that is combined with a time of day that is based on 24-hour clock. datetime2 can be considered as an extension of the existing datetime type that has a larger date range, a larger default fractional precision, and optional user-specified precision.
- **datetimeoffset** Defines a date that is combined with a time of a day that has time zone awareness and is based on a 24-hour clock. By default, has 7 decimal seconds precision. Can be defined like datetimeoffset(n), n in [0,7] to override.

## Views

Links:

- [CREATE VIEW (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-view-transact-sql?view=sql-server-2017)

Related Questions: <sup>83</sup>

## Other

Related Questions: <sup>71,75,76,82,84</sup>

If many related entries appear, they can be merged into a single category.

- <sup>71</sup> **WRITELOG**: `TODO: Write Summary of link`
  - [WRITELOG waittype - Implicit vs. Explicit Transaction: disk or coding issue? ](https://sqltouch.blogspot.com/2013/05/writelog-waittype-implicit-vs-explicit.html)
- <sup>75</sup> **QUERY_STORE**: `TODO Write Summary of link`
  - [Monitoring performance by using the Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/monitoring-performance-by-using-the-query-store?view=sql-server-2017)
  - [Best Practice with the Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/best-practice-with-the-query-store?view=sql-server-2017)
- <sup>76</sup> You need to evaluate schema locking issues, plan cache memory pressure points, and backup I/O.
  - [Activity Monitor](https://docs.microsoft.com/en-us/sql/relational-databases/performance-monitor/activity-monitor?view=sql-server-2017)
- <sup>82,84</sup> Transactions, Isolation Levels, Row versioning
  - [Transaction Locking and Row Versioning Guide](https://docs.microsoft.com/en-us/sql/relational-databases/sql-server-transaction-locking-and-row-versioning-guide?view=sql-server-2017)
  - [SET TRANSACTION ISOLATION LEVEL (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-transaction-isolation-level-transact-sql?view=sql-server-2017)
- <sup>85</sup>Deadlocks
  - [SET DEADLOCK_PRIORITY (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-deadlock-priority-transact-sql?view=sql-server-2017)
  - [Analyze Deadlocks with SQL Server Profiler](https://docs.microsoft.com/en-us/sql/tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler?view=sql-server-2017)
