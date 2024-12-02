## To switch to the PostgreSQL user account

## psql

- psql is a terminal-based front-end to PostgreSQL

```sh
psql -h localhost -d postgres -U postgres
```

# Common PostgreSQL Commands

This document lists frequently used PostgreSQL commands for managing databases, tables, and connections.

## General Commands

| Command            | Description                                                                                  |
| ------------------ | -------------------------------------------------------------------------------------------- |
| `\l`               | Lists all databases.                                                                         |
| `\q`               | Quits the `psql` command-line interface.                                                     |
| `\c database_name` | Connects to a specific database by replacing `database_name` with the desired database name. |
| `\conninfo`        | Displays information about the current database connection.                                  |
| `\password`        | Changes the password for the current user.                                                   |

## Schema and Table Commands

| Command          | Description                                                                        |
| ---------------- | ---------------------------------------------------------------------------------- |
| `\dt`            | Lists all tables in the current database.                                          |
| `\d table_name`  | Describes the structure of a table, including columns and their data types.        |
| `\d+ table_name` | Provides a detailed description of a table, including indexes and storage details. |
| `\dn`            | Lists all schemas in the current database.                                         |
| `\df`            | Lists all functions in the current database.                                       |
| `\di`            | Lists all indexes in the current database.                                         |
| `\dv`            | Lists all views in the current database.                                           |
| `\dm`            | Lists all materialized views.                                                      |

## Query Execution Commands

| Command                 | Description                                                                            |
| ----------------------- | -------------------------------------------------------------------------------------- |
| `EXPLAIN query`         | Displays the execution plan for a query.                                               |
| `EXPLAIN ANALYZE query` | Executes the query and provides the execution plan with actual performance statistics. |

## User and Role Management

| Command                                              | Description                                             |
| ---------------------------------------------------- | ------------------------------------------------------- |
| `CREATE USER username WITH PASSWORD 'password';`     | Creates a new database user.                            |
| `GRANT ALL PRIVILEGES ON database_name TO username;` | Grants all privileges on a database to a specific user. |
| `\du`                                                | Lists all roles and their attributes.                   |

## Database and Table Management

| Command                          | Description                                  |
| -------------------------------- | -------------------------------------------- |
| `CREATE DATABASE database_name;` | Creates a new database.                      |
| `DROP DATABASE database_name;`   | Deletes a database.                          |
| `CREATE TABLE table_name (...);` | Creates a new table.                         |
| `DROP TABLE table_name;`         | Deletes a table.                             |
| `ALTER TABLE table_name ...;`    | Modifies the structure of an existing table. |

## Miscellaneous Commands

| Command            | Description                                      |
| ------------------ | ------------------------------------------------ |
| `\timing`          | Toggles query execution time display on or off.  |
| `\x`               | Toggles expanded output mode for query results.  |
| `\i file_name.sql` | Executes SQL commands from a file.               |
| `\! command`       | Executes a shell command from the `psql` prompt. |

---
