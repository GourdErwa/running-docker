
## 安装启动

Create a data directory on a suitable volume on your host system, e.g. /Users/liwei/Development/data/docker/mysql.
```shell script
docker run --name mysql -p 3306:3306 -v /Users/liwei/Development/data/docker/mysql:/Users/liwei/Development/data/docker/mysql -e MYSQL_ROOT_PASSWORD=root -d mysql:8.0.20

## 登录 mysql
mysql -uroot -proot

```

## 文档
- [hub.docker.mysql](https://hub.docker.com/_/mysql/)
- [mysql/8.0/Dockerfile](https://github.com/docker-library/mysql/blob/bc6e37a2bed792b1c4fc6ab1ec3ce316e6a5f061/8.0/Dockerfile)
