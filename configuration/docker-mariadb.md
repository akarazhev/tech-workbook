# MariaDB Usage

Create working catalogues:

```bash
mkdir -p /opt/project_name/data
mkdir -p /opt/project_name/conf
mkdir -p /opt/project_name/log
```

Set appropriate permissions.
Create the config file: /opt/project_name/conf/config.cnf

```editorconfig
[mysqld]
log_error=/var/lib/mysql/logs/errorlog

slow_query_log=on
slow_query_log_file=/var/lib/mysql/logs/slowlog
```

Run the server:

```bash
docker run -d --restart=always --name project_db_name \
-v /opt/project_name/data:/var/lib/mysql \
-v /opt/project_name/conf:/etc/mysql/conf.d \
-v /opt/project_name/log:/var/lib/mysql/logs \
-e MYSQL_ROOT_PASSWORD=secret -e MYSQL_DATABASE=db_name \
-e MYSQL_USER=sa -e MYSQL_PASSWORD=sa \
-p 127.0.0.1:3306:3306 mariadb:10.3
```

Connect via the client:

```bash
docker run -it --rm --link project_db_name:mysql mariadb:10.3 mysql -hmysql -usa -psa 
```

Make a dump:

```bash
docker run -it --rm --link project_db_name:mysql mariadb:10.3 mysqldump \
--all-databases -hmysql -usa -psa > /tmp/dump_name.sql
```

Upload the dump:

```bash
docker exec -i project_db_name sh -c 'exec mysql -usa -psa db_name' < /tmp/dump_name.sql
```