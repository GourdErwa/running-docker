
# Kibana
[Running Kibana on Docker](https://www.elastic.co/guide/en/kibana/current/docker.html)

## 
```shell script
## 拉取镜像
docker pull docker.elastic.co/kibana/kibana:7.7.1

## 单节点启动

docker run --link YOUR_ELASTICSEARCH_CONTAINER_NAME_OR_ID:elasticsearch -p 5601:5601 {docker-repo}:{version}

````