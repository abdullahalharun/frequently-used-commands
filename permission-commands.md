### Laravel permission commands for lamp server

| Command | Description |
| ------- | ----------- |
| `sudo chgrp -R www-data storage bootstrap/cache` | Command One |
| `sudo chmod -R ug+rwx storage bootstrap/cache` | Command Two |

### wordpress permission commands for lamp server

| Command | Description |
| ------- | ----------- |
| `sudo chown -R www-data:www-data /var/www/path` | Command One |
| `sudo find . -type d -exec chmod 775 {} \;` | Command Two |
| `sudo find . -type f -exec chmod 664 {} \;` | Command Two |

### Rewrite mode enable commands for lamp server

| Command | Description |
| ------- | ----------- |
| `sudo a2enmod rewrite` | Enable Rewrite |
| `sudo systemctl restart apache2` | Restart Apache |

