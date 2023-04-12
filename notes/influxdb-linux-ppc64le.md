# How to Compile and Build InfluxDB for the ppc64le Platform

`InfluxDB` is a database specifically designed to handle large volumes of time-stamped data produced by various sources 
like sensors, applications, and infrastructure. In this article, we will cover how to compile and build InfluxDB for 
the ppc64le platform.

## Install GVM 

First, we need to install the Go Version Manager (GVM), which allows us to easily install and manage multiple versions 
of Go on the same machine. You can install GVM using the following command:

```bash
bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
```

## Select the appropriate Go version

Once GVM is installed, we need to select the appropriate Go version. In this case, we will use Go version 1.13. 
You can install and select the version of Go using the following commands:

```bash
gvm install go1.13
gvm use go1.13
go version
```

## Prepare the source directory

Next, we need to prepare the source directory where we will download and compile InfluxDB. 
You can create a new directory and set it as your GOPATH using the following commands:

```bash
mkdir $HOME/gocodez
export GOPATH=$HOME/gocodez
```

## Get the InfluxDB codes

Now that we have set up our environment, we can download the InfluxDB source code using the go get command:

```bash
go get github.com/influxdata/influxdb
cd $GOPATH/src/github.com/influxdata/influxdb
git checkout v1.8.9
```

## Build InfluxDB for ppc64le platform

Finally, we can build InfluxDB for the ppc64le platform using the following command:

```bash
go install -tags "ppc64le" -ldflags="-X main.version=1.8.9 -X main.branch=main -X main.commit=d9b56321d5796d7791138ed6a8f0a6ae6007a551" ./...
```
