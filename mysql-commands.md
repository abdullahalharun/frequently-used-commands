## Frequently used mysql commands


### Lamp server create new database

| Command | Description |
| ------- | ----------- |
| `mysql -u root -p` | Login |
| `show databases;` | View all the databases |
| `CREATE DATABASE my_db DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;` | Create a new database for wordpress |
| `CREATE USER 'new_user'@'localhost' IDENTIFIED BY 'password';` | Create a new user |
| `GRANT ALL ON my_db.* TO 'new_user'@'localhost';` | Grant All privilleges for the user |
| `FLUSH PRIVILEGES;` | Reload for newly assigned premission |

### Update or select partial string in mysql database
> `UPDATE MyTable SET column = REPLACE(column, 'name ', '') WHERE id = something;`

### Merge table & create a new one on id
> `CREATE TABLE new_table AS (SELECT t1.id, t1.a, t1.b, t1.c, t2.x, t2.y, t2.z FROM t1 INNER JOIN  t2 ON t1.id = t2.id );`

### Export all databases at once
> `mysqldump -u root -p --all-databases > /var/www/alldb.sql`

### Export single database
> `mysqldump -u root -p db_name > /var/www/db_export_date.sql`

### Import all databases at once
> `mysql -u root -p < /var/www/alldb.sql`

### Import single database
> `mysql -u root -p db_name < /var/www/db_name.sql`

