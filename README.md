# MySQL image with utf-8

## mysql:5.6.utf8

## mysql:5.6.utf8.xtrabak

### Dockerfile

```dockerfile
FROM hollychen503/mysql:5.6.utf8
# docker build -f Dockerfile-mysql_5.6.bak -t hollychen503/mysql:5.6.utf8.xtrabak  .

RUN apt update
RUN apt install curl -y

RUN curl https://www.percona.com/downloads/XtraBackup/Percona-XtraBackup-2.3.5/binary/debian/jessie/x86_64/percona-xtrabackup_2.3.5-1.jessie_amd64.deb -O

RUN dpkg -i percona-xtrabackup_2.3.5-1.jessie_amd64.deb ; exit 0


RUN apt --fix-broken install -y

RUN dpkg -i percona-xtrabackup_2.3.5-1.jessie_amd64.deb
```

### build

```bash
docker build -f Dockerfile-mysql_5.6.bak -t hollychen503/mysql:5.6.utf8.xtrabak  .
```

## mysql:5.7.35-utf8

### Dockerfile

```dockerfile
FROM mysql:5.7.35
COPY mysqld_charset.cnf /etc/mysql/conf.d/mysqld_charset.cnf
```

### build

```bash
docker build -t hollychen503/mysql:5.7.35-utf8 .
docker push hollychen503/mysql:5.7.35-utf8

docker tag hollychen503/mysql:5.7.35-utf8  lan.dhms.net:5000/hollychen503/mysql:5.7.35-utf8
docker push lan.dhms.net:5000/hollychen503/mysql:5.7.35-utf8
```

## xtrabackup(standalone)

### mysql 5.7: xtrabak2.4

### Dockerfile

```dockerfile
```

## build

```bash
docker build -t hollychen503/xtrabak:2.4.21 -f Dockerfile_xtrabak --progress=plain .
docker push hollychen503/xtrabak:2.4.21

docker tag hollychen503/xtrabak:2.4.21  hollychen503/xtrabak:2.4.21
docker push hollychen503/xtrabak:2.4.21

```
