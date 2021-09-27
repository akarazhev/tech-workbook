# Compile and build InfluxDB for the ppc64le platform

`InfluxDB` empowers developers to build IoT, analytics and monitoring software. 
It is purpose-built to handle the massive volumes and countless sources of time-stamped data produced by sensors, 
applications and infrastructure.

## Install GVM 

```bash
bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
```

## Select the appropriate GO version

```bash
gvm install go1.13
go version
```

## Prepare the source directory

```bash
mkdir $HOME/gocodez
export GOPATH=$HOME/gocodez
```

## Get the InfluxDB codes

```bash
go get github.com/influxdata/influxdb
cd $GOPATH/src/github.com/influxdata/influxdb
git checkout v1.8.9
```

## Build the InfluxDB codes 

```bash
go install -ldflags="-X main.version=1.8.9 -X main.branch=main -X main.commit=d9b56321d5796d7791138ed6a8f0a6ae6007a551" ./...
```
