## Description

This Dockerfile will create a CentOS 7 image with Systemd enabled

## Build

```
docker build -t local/centos7-with-systemd .
```

## Run

```
docker run -d --name centos7 local/centos7-with-systemd
```