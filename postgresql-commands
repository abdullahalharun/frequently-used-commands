# PostgreSQL Basic Commands

## Connect to PostgreSQL

Connect using a specific user and database:

```bash
psql -U <username> -d <database_name>
```

Connect as the `postgres` superuser:

```bash
psql -U postgres
```

## List Databases

Inside `psql`:

```sql
\l
```

## Create Database

```sql
CREATE DATABASE mydb;
```

## Drop Database

```sql
DROP DATABASE mydb;
```

## List Users / Roles

```sql
\du
```

## Create User

```sql
CREATE USER myuser WITH PASSWORD 'mypassword';
```

## Grant Privileges

```sql
GRANT ALL PRIVILEGES ON DATABASE mydb TO myuser;
```

## Connect to a Database

```sql
\c mydb
```

## List Tables

```sql
\dt
```

## Show Table Structure

```sql
\d table_name
```

## Insert Data

```sql
INSERT INTO table_name (column1, column2) VALUES ('value1', 'value2');
```

## Query Data

```sql
SELECT * FROM table_name;
```

## Update Data

```sql
UPDATE table_name SET column1 = 'newvalue' WHERE id = 1;
```

## Delete Data

```sql
DELETE FROM table_name WHERE id = 1;
```

## Exit from psql

```sql
\q
```
