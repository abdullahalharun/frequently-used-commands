# Frequenly Used Commands
Frequently used commands

### Lamp server

| Command | Description |
| ------- | ----------- |
| `mysql -u root -p` | Login |
| `show databases;` | View all the databases |
| `CREATE DATABASE my_db DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;` | Create a new database for wordpress |
| `CREATE USER 'new_user'@'localhost' IDENTIFIED BY 'password';` | Create a new user |
| `GRANT ALL ON my_db.* TO 'new_user'@'localhost';` | Grant All privilleges for the user |
| `FLUSH PRIVILEGES;` | Reload for newly assigned premission |

### Laravel permission for lamp server

| Command | Description |
| ------- | ----------- |
| `sudo chgrp -R www-data storage bootstrap/cache` | Command One |
| `sudo chmod -R ug+rwx storage bootstrap/cache` | Command Two |
