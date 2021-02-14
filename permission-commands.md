### Laravel permission commands for lamp server

| Command | Description |
| ------- | ----------- |
| `sudo chgrp -R www-data storage bootstrap/cache` | Command One |
| `sudo chmod -R ug+rwx storage bootstrap/cache` | Command Two |

### wordpress permission commands for lamp server

| Command | Description |
| ------- | ----------- |
| `sudo chown -R www-data:myusername /var/www/path` | Command One |
| `sudo find /path/to/your/wordpress/install/ -type d -exec chmod 775 {} \;` | Command Two |
| `sudo find /path/to/your/wordpress/install/ -type f -exec chmod 664 {} \;` | Command Two |

