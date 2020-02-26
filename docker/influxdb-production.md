# InfluxDB for the production usage

Create working catalogues:

```bash
mkdir -p /opt/project_name/influxdb
```

Set appropriate permissions.

Run the server:

```bash
docker run -d --restart=always --name project_db_name \
-e INFLUXDB_DB=db_name \
-e INFLUXDB_ADMIN_USER=secret -e INFLUXDB_ADMIN_PASSWORD=secret \
-e INFLUXDB_HTTP_AUTH_ENABLED=true \
-v /opt/project_name/influxdb:/var/lib/influxdb \
-p 8086:8086 influxdb:1.7
```

Creating a DB named mydb:

```bash
curl -G http://localhost:8086/query --data-urlencode "q=CREATE DATABASE mydb"
```

Inserting into the DB:

```bash
curl -i -XPOST 'http://localhost:8086/write?db=mydb' --data-binary 'cpu_load_short,host=server01,region=us-west value=0.64 1434055562000000000'
```