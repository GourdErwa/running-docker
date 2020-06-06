
# docker 可视化 portainer

## 安装启动
[Portainer installation using Docker](https://www.portainer.io/installation/)

```shell script

$ docker volume create portainer_data

$ docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer


# http://localhost:9000/
# admin
# adminadmin
```