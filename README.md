```bash
# .gitpod.dockerfile
FROM gitpod/workspace-mysql
```

```bash
mysql -e "show databases;"
mysql -e "CREATE DATABASE IF NOT EXISTS wordpress;"
mysql -e "CREATE USER wordpress@localhost IDENTIFIED BY 'wordpress';"
mysql -e "GRANT ALL PRIVILEGES ON *.* TO wordpress@localhost;"
mysql -e "FLUSH PRIVILEGES;"

mysql -e "SELECT user from mysql.user;"

mkdir ~/.php && echo 'cli_server.color = on' >> ~/.php/php-cli-server.ini
```