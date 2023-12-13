## Frequently used linux command

#### Install zip & unzip support
> `sudo apt install zip unzip`

#### zip a folder
> `zip -r output.zip folder_name`

#### Move all files from a folder to another folder
> `mv  -v /source/path/* /destination/path/`

### Rewrite mode enable commands for lamp server

| Command | Description |
| ------- | ----------- |
| `sudo a2enmod rewrite` | Enable Rewrite |
| `sudo systemctl restart apache2` | Restart Apache |

### Copy file from remote server
If you are on the computer from which you want to send file to a remote computer:

`scp /file/to/send username@remote:/where/to/put`
Here the remote can be a FQDN or an IP address.

On the other hand if you are on the computer wanting to receive file from a remote computer:

`scp username@remote:/file/to/send /where/to/put`
scp can also send files between two remote hosts:

`scp username@remote_1:/file/to/send username@remote_2:/where/to/put`
