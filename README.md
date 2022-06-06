# InterviewCake Bakery Schema for PostgreSQL

The [InterviewCake](https://www.interviewcake.com/) bakery schema for SQL questions is specific to MySQL. This repo provides a PostgreSQL conversion of the schema DDL and insert statements compatiblee with PosgreSQL.

The SQL files provided are:

- **bakery_schema_and_data_pg.sql** => DML INSERTS for the table data
- **bakery_schema_ddl.sql** => CRREATE TABLE statemnets compatible with PostgreSQL

## Background: How-to Convert the Inserts

You can simply convert the insert statements by prepending an `E'...'` to any MySQL string escapes using backslash:

```bash
# Inside a *nix like shell, Mac, Linux, etc
cat bakery_schema_and_data.sql | sed "s/,'/,E'/g" > bakery_schema_and_data_pg.sql
```
