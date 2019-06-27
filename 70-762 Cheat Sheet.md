# Exam 70-762: Developing SQL Databases Cheat Sheet

All the links below are useful for questions that have appeared in past exams.

## Glossary Of Terms

- SQL: Structured Query Language
- OLTP: On Line Transaction Processing
- OLAP: On Line Analytics Processing
- CLR: Common Language Runtime
- SSRS: SQL Server Reporting Services
- SSIS: SQL Server Integration Services
- ETL: Extract, Transform, Load
- ETW: Event Tracing for Windows
- DML: Data Manipulation Language
- DDL: Data Definition Language

## Links

### Tables

- [Tables](https://docs.microsoft.com/en-us/sql/relational-databases/tables/tables?view=sql-server-2017)
- [Partitioned Tables and Indexes](https://docs.microsoft.com/en-us/sql/relational-databases/partitions/partitioned-tables-and-indexes?view=sql-server-2017)
- [Understanding the SQL Server NOLOCK hint](https://www.mssqltips.com/sqlservertip/2470/understanding-the-sql-server-nolock-hint/)
- [Faster temp table and table variable by using memory optimization](https://docs.microsoft.com/en-us/sql/relational-databases/in-memory-oltp/faster-temp-table-and-table-variable-by-using-memory-optimization?view=sql-server-2017)
- [A Guide to Query Processing for Memory-Optimized Tables](https://docs.microsoft.com/en-us/sql/relational-databases/in-memory-oltp/a-guide-to-query-processing-for-memory-optimized-tables?view=sql-server-2017), [Sample Database for In-Memory OLTP](https://docs.microsoft.com/en-us/sql/relational-databases/in-memory-oltp/sample-database-for-in-memory-oltp?view=sql-server-2017)

---

### Indexes

- [Clustered and Nonclustered Indexes Described](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/clustered-and-nonclustered-indexes-described?view=sql-server-2017)
- [SQL Server Index Architecture and Design Guide](https://docs.microsoft.com/en-us/sql/relational-databases/sql-server-index-design-guide?view=sql-server-2017)
- [CREATE INDEX (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-index-transact-sql?view=sql-server-2017)
- [Reorganize and Rebuild Indexes](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/reorganize-and-rebuild-indexes?view=sql-server-2017)
- [Columnstore indexes: Overview](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/columnstore-indexes-overview?view=sql-server-2017)
- [Create Filtered Indexes](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/create-filtered-indexes?view=sql-server-2017)
- [UPDATE STATISTICS (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/update-statistics-transact-sql?view=sql-server-2017)

---

### Triggers

- [CREATE TRIGGER (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-trigger-transact-sql?view=sql-server-2017)
- [Logon Triggers](https://docs.microsoft.com/en-us/sql/relational-databases/triggers/logon-triggers?view=sql-server-2017)

---

### Transactions

- [Manage the size of the transaction log file](https://docs.microsoft.com/en-us/sql/relational-databases/logs/manage-the-size-of-the-transaction-log-file?view=sql-server-2017)
- Isolation Levels, Row versioning
  - [Transaction Locking and Row Versioning Guide](https://docs.microsoft.com/en-us/sql/relational-databases/sql-server-transaction-locking-and-row-versioning-guide?view=sql-server-2017)
  - [SET TRANSACTION ISOLATION LEVEL (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-transaction-isolation-level-transact-sql?view=sql-server-2017)
- [Transactions with Memory-Optimized Tables](https://docs.microsoft.com/en-us/sql/relational-databases/in-memory-oltp/transactions-with-memory-optimized-tables?view=sql-server-2017)
- [SAVE TRANSACTION (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/save-transaction-transact-sql?view=sql-server-2017&viewFallbackFrom=sql-ser)
- [SET IMPLICIT_TRANSACTIONS (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-implicit-transactions-transact-sql?view=sql-server-2017)

---

### Functions / Stored Procedures

- [CREATE FUNCTION (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-function-transact-sql?view=sql-server-2017)
- [User Defined Functions and Stored Procedures](https://docs.microsoft.com/en-us/sql/analysis-services/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures?view=sql-server-2017)
- <sup>98</sup> [Use Table-Valued Parameters (Database Engine)](https://docs.microsoft.com/en-us/sql/relational-databases/tables/use-table-valued-parameters-database-engine?view=sql-server-2017)
- <sup>100</sup> [Return Data from a Stored Procedure](https://docs.microsoft.com/en-us/sql/relational-databases/stored-procedures/return-data-from-a-stored-procedure?view=sql-server-2017)
- <sup>105</sup> [A Guide to Query Processing for Memory-Optimized Tables](https://docs.microsoft.com/en-us/sql/relational-databases/in-memory-oltp/a-guide-to-query-processing-for-memory-optimized-tables?view=sql-server-2017)
- <sup>135</sup> [Using a Stored Procedure with Output Parameters](https://docs.microsoft.com/en-us/sql/connect/jdbc/using-a-stored-procedure-with-output-parameters?view=sql-server-2017)

---

### Constraints

- [Unique Constraints and Check Constraints](https://docs.microsoft.com/en-us/sql/relational-databases/tables/unique-constraints-and-check-constraints?view=sql-server-2017)
- [Commonly used SQL Server Constraints: FOREIGN KEY, CHECK and DEFAULT](https://www.sqlshack.com/commonly-used-sql-server-constraints-foreign-key-check-default/)

---

### Data types

Integers:

| Data Type | Range | Storage |
|-----------|-------|---------|
|BIGINT|-2<sup>63</sup>(-9,223,372,036,854,775,808) to 2<sup>63</sup>-1 (9,223,372,036,854,775,807)|8 Bytes|
|INT|-2<sup>31</sup> (-2,147,483,648) to 2<sup>31</sup>-1 (2,147,483,647)|4 Bytes|
|SMALLINT|-2<sup>15</sup> (-32,768) to 2<sup>15</sup>-1 (32,767)|2 Bytes|
|TINYINT|0 to 255|1 Byte|

Date/Time:

- **datetime** Defines a date that is combined with a time of day with fractional seconds that is based on a 24-hour clock. *Use the time, date, datetime2 and datetimeoffset data types for new work. These types align with the SQL Standard*.
- **time** Defines a time of a day. The time is without time zone awareness and is based on a 24-hour clock.
- **date** Defines a date in SQL Server. Default string literal format: YYYY-MM-DD.
- **datetime2** Defines a date that is combined with a time of day that is based on 24-hour clock. datetime2 can be considered as an extension of the existing datetime type that has a larger date range, a larger default fractional precision, and optional user-specified precision.
- **datetimeoffset** Defines a date that is combined with a time of a day that has time zone awareness and is based on a 24-hour clock. By default, has 7 decimal seconds precision. Can be defined like datetimeoffset(n), n in [0,7] to override.

---

### Views

- [CREATE VIEW (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-view-transact-sql?view=sql-server-2017)
- [Create Indexed Views](https://docs.microsoft.com/en-us/sql/relational-databases/views/create-indexed-views?view=sql-server-2017)
- [Creating and Optimizing Views in SQL Server](http://www.informit.com/articles/article.aspx?p=130855&seqNum=4)

---

### Other

If many related entries appear, they can be merged into a single category.

- **WRITELOG**:
  - [WRITELOG waittype - Implicit vs. Explicit Transaction: disk or coding issue?](https://sqltouch.blogspot.com/2013/05/writelog-waittype-implicit-vs-explicit.html)
- **QUERY_STORE**:
  - [Monitoring performance by using the Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/monitoring-performance-by-using-the-query-store?view=sql-server-2017)
  - [Best Practice with the Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/best-practice-with-the-query-store?view=sql-server-2017)
- You need to evaluate schema locking issues, plan cache memory pressure points, and backup I/O.
  - [Activity Monitor](https://docs.microsoft.com/en-us/sql/relational-databases/performance-monitor/activity-monitor?view=sql-server-2017)
- Deadlocks
  - [SET DEADLOCK_PRIORITY (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-deadlock-priority-transact-sql?view=sql-server-2017)
  - [Analyze Deadlocks with SQL Server Profiler](https://docs.microsoft.com/en-us/sql/tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler?view=sql-server-2017)
  - [Trace Flags](https://docs.microsoft.com/en-us/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql?view=sql-server-2017)
- Files and Filegroups
  - [Database Files and Filegroups](https://docs.microsoft.com/en-us/sql/relational-databases/databases/database-files-and-filegroups?view=sql-server-2017)
- Azure SQL Database
  - [Service tiers in the DTU-based purchase model](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tiers-dtu)
- [Introduction to SQL Server CLR Integration](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/introduction-to-sql-server-clr-integration)
- [sys.dm_exec_sessions (Transact-SQL)](https://docs.microsoft.com/en-us/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql?view=sql-server-2017)
- [SQL Server Profiler](https://docs.microsoft.com/en-us/sql/tools/sql-server-profiler/sql-server-profiler?view=sql-server-2017)
- [Performance Statistics Event Class](https://docs.microsoft.com/en-us/sql/relational-databases/event-classes/performance-statistics-event-class?view=sql-server-2017)
- [SET ANSI_DEFAULTS (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-ansi-defaults-transact-sql?view=sql-server-2017). When enabled (ON), this option enables SET IMPLICIT_TRANSACTIONS (and some other options).
- [Extended events overview](https://docs.microsoft.com/en-us/sql/relational-databases/extended-events/extended-events?view=sql-server-2017)
- [sys.dm_tran_locks (Transact-SQL)](https://docs.microsoft.com/en-us/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql?view=sql-server-2017)
- [Set Operators - UNION (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017)
- [SQL Server Extended Events Targets](https://docs.microsoft.com/en-us/sql/database-engine/sql-server-extended-events-targets?view=sql-server-2014)
- [Dynamic Data Masking](https://docs.microsoft.com/en-us/sql/relational-databases/security/dynamic-data-masking?view=sql-server-2017)
- [SET SHOWPLAN_ALL (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/statements/set-showplan-all-transact-sql?view=sql-server-2017)
- [ALTER DATABASE (Transact-SQL) Compatibility Level](https://docs.microsoft.com/en-us/sql/t-sql/statements/alter-database-transact-sql-compatibility-level?view=sql-server-2017)
- [Explanation of SQL Server IO and Latches](https://www.mssqltips.com/sqlservertip/3088/explanation-of-sql-server-io-and-latches/)
- [Always On availability groups: a high-availability and disaster-recovery solution](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/always-on-availability-groups-sql-server)
