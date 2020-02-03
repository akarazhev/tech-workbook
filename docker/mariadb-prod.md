# MariaDB for the production use

Create working catalogues:

```bash
mkdir -p /opt/pmon/data
mkdir -p /opt/pmon/conf
mkdir -p /opt/pmon/log
```

Set appropriate permissions.
Create the config file: /opt/pmon/conf/config.cnf

```editorconfig
[mysqld]
log_error=/var/lib/mysql/logs/errorlog

slow_query_log=on
slow_query_log_file=/var/lib/mysql/logs/slowlog
```

Run the server:

```bash
docker run -d --restart=always --name pmon_mariadb -v /opt/pmon/data:/var/lib/mysql -v /opt/pmon/conf:/etc/mysql/conf.d -v /opt/pmon/log:/var/lib/mysql/logs -e MYSQL_ROOT_PASSWORD=secret -e MYSQL_DATABASE=pmon -e MYSQL_USER=sa -e MYSQL_PASSWORD=sa -p 127.0.0.1:3306:3306 mariadb:10.3
```

Connect via the client:

```bash
docker run -it --rm --link pmon_mariadb:mysql mariadb:10.3 mysql -hmysql -usa -psa 
```