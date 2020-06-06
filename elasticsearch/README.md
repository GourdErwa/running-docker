
# ElasticSearch
[Install Elasticsearch with Docker](https://www.elastic.co/guide/en/elasticsearch/reference/7.7/docker.html#docker-cli-run-dev-mode)

## 安装启动
```shell script
## 拉取镜像
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.7.1

## 单节点启动
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.7.1

# http://localhost:9200

````