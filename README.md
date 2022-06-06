# InterviewCake Bakery Schema for PostgreSQL

The [InterviewCake](https://www.interviewcake.com/) bakery schema for SQL questions is specific to MySQL. This repo provides a PostgreSQL conversion of the schema DDL and insert statements compatible with PostgreSQL.

The SQL files provided are:

- **bakery_schema_postgres.sql** => CREATE TABLE statemnets compatible with PostgreSQL
- **bakery_data_postgres.sql** => DML INSERTS for the table data

To unpack the gzipped SQL files:

```bash
# Unpacks and replaces gz file with sql one
$ gunzip bakery_schema_postgres.sql.gz
```

## Background: How-to Convert the Inserts

You can simply convert the insert statements by prepending an `E'...'` to any MySQL string escapes using backslash:

```bash
# Inside a *nix like shell, Mac, Linux, etc
# Note: bakery_schema_and_data.sql is the original InterviewCake MySQL file
cat bakery_schema_and_data.sql | sed "s/,'/,E'/g" > bakery_schema_and_data_pg.sql
```
