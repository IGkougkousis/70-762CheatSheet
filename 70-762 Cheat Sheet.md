# Exam 70-762: Developing SQL Databases Cheat Sheet

Related questions from the pdf are in superscript like this<sup>1</sup>.

## Views

- Using **WITH ENCRYPTION** prevents the view from being published as part of SQL Server replication.
- When **SCHEMABINDING** is specified, the base table or tables cannot be modified in a way that would affect the view definition.
- Using **VIEW_METADATA** specifies that the instance of SQL Server will return to the DB-Library, ODBC, and OLE DB APIs the metadata information about the view, instead of the base table or tables, when browse-mode metadata is being requested for a query that references the view.
- Using **CHECK OPTION** forces all data modification statements executed against the view to follow the criteria set within select_statement. When a row is modified through a view, the WITH CHECK OPTION makes sure the data remains visible through the view after the modification is committed.

## Indexes <sup>62,63,64</sup>

## Triggers <sup>68</sup>

- FOR UPDATE

## Transactions <sup>65,66</sup>

- **XACT_STATE** Is a scalar function that reports the user transaction state of a current running request. XACT_STATE indicates whether the request has an active user transaction, and whether the transaction is capable of being committed. **XACT_ABORT** must be ON to rollback transactions. Values:
  - 1: The current request has an active user transaction. The request can perform any actions, including writing data and committing the transaction.
  - 0: There is no active user transaction for the current request.
  - -1: The current request has an active user transaction, but an error has occurred that has caused the transaction to be classified as an uncommittable transaction.
- a

## Constraints <sup>67</sup>

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

## Data types <sup></sup>

Date/Time: <sup>59,60,61</sup>

- **datetime** Defines a date that is combined with a time of day with fractional seconds that is based on a 24-hour clock. *Use the time, date, datetime2 and datetimeoffset data types for new work. These types align with the SQL Standard*.
- **time** Defines a time of a day. The time is without time zone awareness and is based on a 24-hour clock.
- **date** Defines a date in SQL Server. Default string literal format: YYYY-MM-DD.
- **datetime2** Defines a date that is combined with a time of day that is based on 24-hour clock. datetime2 can be considered as an extension of the existing datetime type that has a larger date range, a larger default fractional precision, and optional user-specified precision.
- **datetimeoffset** Defines a date that is combined with a time of a day that has time zone awareness and is based on a 24-hour clock. By default, has 7 decimal seconds precision. Can be defined like datetimeoffset(n), n in [0,7] to override.
