# sqlchop

Browser-side SQL formatter and beautifier — paste any SQL query and get it formatted with proper indentation, consistent keyword casing, and clean line breaks.

## What it does

sqlchop takes a SQL query (SELECT, INSERT, UPDATE, DELETE, CREATE TABLE, stored procedures, CTEs, etc.) and reformats it for readability. It supports ten SQL dialects and is configurable for indent size and keyword casing.

## Dialects supported

- `postgresql` — PostgreSQL
- `mysql` — MySQL
- `tsql` — SQL Server (T-SQL)
- `bigquery` — Google BigQuery
- `sqlite` — SQLite
- `plsql` — PL/SQL (Oracle)
- `spark` — Apache Spark SQL
- `redshift` — Amazon Redshift
- `trino` — Trino / Presto
- `hive` — Apache Hive

## Input/output

**Input:** Any SQL string, in any format (compressed, multi-line, mixed casing).

**Output:** Formatted SQL with consistent indentation and keyword casing.

## Human surface

Live at: https://sqlchop.radicchio.page

The web interface accepts paste input and formats on button click or Cmd+Enter.

## Agent surface (planned)

An MCP tool `format_sql(query, dialect, indent_width, keyword_case)` → formatted SQL string is planned for the paid tier. Until then, agents can use the underlying `sql-formatter` npm package directly:

```js
import { format } from 'sql-formatter';
const result = format(rawSQL, { language: 'postgresql', tabWidth: 2, keywordCase: 'upper' });
```

## Pricing

Free tier: Unlimited formatting in the browser — no signup, no limit.
Paid tier (planned): Saved snippet library, team workspace, CI integration — $9/month.

## Privacy

All formatting is performed client-side using the `sql-formatter` JavaScript library. No SQL is transmitted to any server.

## Support

https://bitterdesk.com/s/sqlchop/
