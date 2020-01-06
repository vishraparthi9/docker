## Description

This image will install Nginx on top of CentOS 7 image. It will create a sample page with name index.html

## Build

```
docker build -t local/centos-nginx .
```

## Run

```
docker run -d -p 80:80 --name nginx local/centos-nginx
```