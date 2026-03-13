# SQL Index Hints for Primary Key

How different databases specify an optimizer hint to use the primary key index.

## MySQL / MariaDB

```sql
SELECT * FROM t FORCE INDEX (PRIMARY) WHERE ...;
```

MySQL uses the special keyword `PRIMARY` to refer to the PK index.

## Oracle

```sql
SELECT /*+ INDEX(t t_pk) */ * FROM t WHERE ...;
```

Uses the actual PK constraint/index name. There is no special "primary key"
keyword in hints.

## SQL Server

```sql
SELECT * FROM t WITH (INDEX(1)) WHERE ...;
-- Or by name:
SELECT * FROM t WITH (INDEX(PK_t)) WHERE ...;
```

Index ID 1 is always the clustered index (usually the PK).

## PostgreSQL (pg_hint_plan extension)

```sql
SELECT /*+ IndexScan(t t_pkey) */ * FROM t WHERE ...;
```

PostgreSQL has no built-in hints. The `pg_hint_plan` extension adds
Oracle-style hints. PG auto-names PK indexes as `<table>_pkey`.

## SQLite

```sql
SELECT * FROM t INDEXED BY sqlite_autoindex_t_1 WHERE ...;
```

For `INTEGER PRIMARY KEY`, there is no separate index — it is the rowid
itself. For other PK types, SQLite creates `sqlite_autoindex_<table>_1`.
`WITHOUT ROWID` tables use the PK as the clustered index with no separate
index name. `INDEXED BY` will error (not silently fall back) if the index
can't be used.

## DB2

```sql
SELECT * FROM t USE INDEX (t_pk) WHERE ...;
```

Uses the actual index/constraint name.

## Summary

| Approach | Databases |
|---|---|
| Special `PRIMARY` keyword | MySQL, MariaDB |
| Well-known index ID (`1`) | SQL Server |
| Must use actual index/constraint name | Oracle, PostgreSQL, DB2, SQLite |
