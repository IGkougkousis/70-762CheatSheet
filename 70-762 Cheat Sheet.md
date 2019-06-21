# Exam 70-762: Developing SQL Databases Cheat Sheet

Related questions from the pdf are in superscript like this<sup>1</sup>.

Questions with the same scenario:

- 89-91 Azure SQL Database Tiers.
- 92-94, 117 Query using nonclustered index takes too long to complete.
- 111, 114 `TODO: This is similar to questions before 89, need to update`
- 115 `TODO: This is similar to questions before 89, need to update`
- 116 `TODO: This is similar to questions before 89, need to update`

Unique questions:

- 95 Transaction, ALLOW_SNAPSHOT_ISOLATION, READ_COMMITED SNAPSHOT etc
- 96 Transaction, DELAYED_DURABILITY, explicit/implicit transaction
- 97 Index, UNIQUE, IGNORE_DUP_KEY, ONLINE
- 98 Stored Procedure, Table-Valued Parameters, ADO .NET table
- 99 Deadlocks, trace flags
- 100 Stored procedure, return data
- 101 Triggers, LOGON, INSTEAD OF INSERT, DDL
- 102 Nonclustered Index syntax
- 103 Transaction, Isolation Levels
- 104 SQL Server with .NET
- 105 disk vs memory-optimized tables, modules, functions /stored procedures
- 106 sp, transactions, isolation levels
- 107 Index, clustered columnstore
- 108 Syntax for stored procedure
- 109 query store execution plan
- 110 sys.dm_exec_sessions, SQL permisisons
- 118 Describe constraints
- 119 Create Indexed View
- 120 Make queries faster
- 121 Make reports faster, showing only committed
- 122 Same as 120
- 123 Abort transaction if error occurs
- 124 After insert trigger syntax
- 125 Create view that adds rows to table
- 126 Create Index
- 127 Optimize ETL process
- 128 Stored Procedure, Transactions
- 129 Stored Procedure, syntax
- 130 Constraint

## Glossary Of Terms

SQL: Structured Query Language
OLTP: On Line Transaction Processing
OLAP: On Line Analytics Processing
CLR: Common Language Runtime
SSRS: SQL Server Reporting Services
SSIS: SQL Server Integration Services
ETL: Extract, Transform, Load

## Tables

Links

- [Tables](https://docs.microsoft.com/en-us/sql/relational-databases/tables/tables?view=sql-server-2017)
- <sup>85</sup> [Partitioned Tables and Indexes](https://docs.microsoft.com/en-us/sql/relational-databases/partitions/partitioned-tables-and-indexes?view=sql-server-2017)
- <sup>120</sup> [Understanding the SQL Server NOLOCK hint](https://www.mssqltips.com/sqlservertip/2470/understanding-the-sql-server-nolock-hint/)
- <sup>127</sup> [Faster temp table and table variable by using memory optimization](https://docs.microsoft.com/en-us/sql/relational-databases/in-memory-oltp/faster-temp-table-and-table-variable-by-using-memory-optimization?view=sql-server-2017)

Related Questions: <sup>80,86,120,122,127</sup>

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
- [Reorganize and Rebuild Indexes](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/reorganize-and-rebuild-indexes?view=sql-server-2017)
- [Columnstore indexes: Overview](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/columnstore-indexes-overview?view=sql-server-2017)

Related Questions: <sup>62,63,64,70,72,77,81,92,93,94,97,102,107,111,117,126,132</sup>

## Triggers

Links:

- [CREATE TRIGGER (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-trigger-transact-sql?view=sql-server-2017)
- <sup>101</sup> [Logon Triggers](https://docs.microsoft.com/en-us/sql/relational-databases/triggers/logon-triggers?view=sql-server-2017)

Related Questions: <sup>68,78,101,116, 124</sup>

## Transactions

Related Questions: <sup>65,66,82,84,87,95,96,103,106,114,121,123,128,129</sup>

- <sup>123</sup> **XACT_STATE** Is a scalar function that reports the user transaction state of a current running request. XACT_STATE indicates whether the request has an active user transaction, and whether the transaction is capable of being committed. **XACT_ABORT** must be ON to rollback transactions. Values:
  - 1: The current request has an active user transaction. The request can perform any actions, including writing data and committing the transaction.
  - 0: There is no active user transaction for the current request.
  - -1: The current request has an active user transaction, but an error has occurred that has caused the transaction to be classified as an uncommittable transaction.
- <sup>87</sup> [Manage the size of the transaction log file](https://docs.microsoft.com/en-us/sql/relational-databases/logs/manage-the-size-of-the-transaction-log-file?view=sql-server-2017)
- <sup>82,84,95,114,128</sup> Isolation Levels, Row versioning
  - [Transaction Locking and Row Versioning Guide](https://docs.microsoft.com/en-us/sql/relational-databases/sql-server-transaction-locking-and-row-versioning-guide?view=sql-server-2017)
  - [SET TRANSACTION ISOLATION LEVEL (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-transaction-isolation-level-transact-sql?view=sql-server-2017)
- <sup>96</sup> [Transactions with Memory-Optimized Tables](https://docs.microsoft.com/en-us/sql/relational-databases/in-memory-oltp/transactions-with-memory-optimized-tables?view=sql-server-2017)
- [SAVE TRANSACTION (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/save-transaction-transact-sql?view=sql-server-2017&viewFallbackFrom=sql-ser)

## Functions / Stored Procedures

Links:

- [CREATE FUNCTION (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-function-transact-sql?view=sql-server-2017)
- [User Defined Functions and Stored Procedures](https://docs.microsoft.com/en-us/sql/analysis-services/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures?view=sql-server-2017)
- <sup>98</sup> [Use Table-Valued Parameters (Database Engine)](https://docs.microsoft.com/en-us/sql/relational-databases/tables/use-table-valued-parameters-database-engine?view=sql-server-2017)
- <sup>100</sup> [Return Data from a Stored Procedure](https://docs.microsoft.com/en-us/sql/relational-databases/stored-procedures/return-data-from-a-stored-procedure?view=sql-server-2017)
- <sup>105</sup> [A Guide to Query Processing for Memory-Optimized Tables](https://docs.microsoft.com/en-us/sql/relational-databases/in-memory-oltp/a-guide-to-query-processing-for-memory-optimized-tables?view=sql-server-2017)
- <sup>135</sup> [Using a Stored Procedure with Output Parameters](https://docs.microsoft.com/en-us/sql/connect/jdbc/using-a-stored-procedure-with-output-parameters?view=sql-server-2017)

Related Questions: <sup>73,74,75,79,98,100,105,106,108,135</sup>

## Constraints

Links:

- [Unique Constraints and Check Constraints](https://docs.microsoft.com/en-us/sql/relational-databases/tables/unique-constraints-and-check-constraints?view=sql-server-2017)

Related Questions: <sup>67,69,118,130</sup>

- **CHECK**: The CHECK constraint is used to limit the value range that can be placed in a column. If you define a CHECK constraint on a single column it allows only certain values for this column. If you define a CHECK constraint on a table it can limit the values in certain columns based on values in other columns in the row. Examples:
- **Cascading Referential Integrity**: Are the foreign key constraints which tell SQL Server to perform certain actions whenever a user attempts to delete or update a primary key to which an existing foreign keys point. Default: NO ACTION. Other available actions: SET NULL, CASCADE, SET DEFAULT.

## Data types

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
- <sup>119</sup> [Create Indexed Views](https://docs.microsoft.com/en-us/sql/relational-databases/views/create-indexed-views?view=sql-server-2017)
- <sup>125</sup> [Creating and Optimizing Views in SQL Server](http://www.informit.com/articles/article.aspx?p=130855&seqNum=4)

Related Questions: <sup>83,119</sup>

## Other

Related Questions: <sup>71,75,76,82,84,104,112</sup>

If many related entries appear, they can be merged into a single category.

- <sup>71</sup> **WRITELOG**:
  - [WRITELOG waittype - Implicit vs. Explicit Transaction: disk or coding issue? ](https://sqltouch.blogspot.com/2013/05/writelog-waittype-implicit-vs-explicit.html)
- <sup>75,109</sup> **QUERY_STORE**:
  - [Monitoring performance by using the Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/monitoring-performance-by-using-the-query-store?view=sql-server-2017)
  - [Best Practice with the Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/best-practice-with-the-query-store?view=sql-server-2017)
- <sup>76</sup> You need to evaluate schema locking issues, plan cache memory pressure points, and backup I/O.
  - [Activity Monitor](https://docs.microsoft.com/en-us/sql/relational-databases/performance-monitor/activity-monitor?view=sql-server-2017)
- <sup>85,99</sup> Deadlocks
  - [SET DEADLOCK_PRIORITY (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-deadlock-priority-transact-sql?view=sql-server-2017)
  - [Analyze Deadlocks with SQL Server Profiler](https://docs.microsoft.com/en-us/sql/tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler?view=sql-server-2017)
  - <sup>99</sup> [Trace Flags](https://docs.microsoft.com/en-us/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql?view=sql-server-2017)
- Files and Filegroups
  - <sup>88</sup> [Database Files and Filegroups](https://docs.microsoft.com/en-us/sql/relational-databases/databases/database-files-and-filegroups?view=sql-server-2017)
- <sup>89,90,91</sup> Azure SQL Database
  - [Service tiers in the DTU-based purchase model](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tiers-dtu)
- <sup>104,112</sup> [Introduction to SQL Server CLR Integration](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/introduction-to-sql-server-clr-integration)
- <sup>110</sup> [sys.dm_exec_sessions (Transact-SQL)](https://docs.microsoft.com/en-us/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql?view=sql-server-2017)
- [SQL Server Profiler](https://docs.microsoft.com/en-us/sql/tools/sql-server-profiler/sql-server-profiler?view=sql-server-2017)
- <sup>113</sup> [Performance Statistics Event Class](https://docs.microsoft.com/en-us/sql/relational-databases/event-classes/performance-statistics-event-class?view=sql-server-2017)
- <sup>131</sup> [SET ANSI_DEFAULTS (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-ansi-defaults-transact-sql?view=sql-server-2017). When enabled (ON), this option enables SET IMPLICIT_TRANSACTIONS (and some other options).
- <sup>133</sup> [Extended events overview](https://docs.microsoft.com/en-us/sql/relational-databases/extended-events/extended-events?view=sql-server-2017)
- <sup>134</sup> [sys.dm_tran_locks (Transact-SQL)](https://docs.microsoft.com/en-us/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql?view=sql-server-2017)
