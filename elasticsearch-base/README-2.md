# 博文内容

- 博文标题：1.2 Elasticsearch 集群的管理
- 博文地址：<http://www.youmeek.com/elasticsearch-cluster/>


## 课程环境

- **CentOS 7.3 x64**
- JDK 版本：1.8（最低要求），主推：**JDK 1.8.0_121**
- Elasticsearch 版本：**5.2.0**
- 相关软件包百度云下载地址（密码：0yzd）：<http://pan.baidu.com/s/1qXQXZRm>
- **注意注意：** Elasticsearch 安装过程请移步到我 Github 上的这套 Linux 教程：<https://github.com/judasn/Linux-Tutorial/blob/master/ELK-Install-And-Settings.md>

------------------------

## Elasticsearch 介绍

- 当前（201705）最新版本为：5.4
- 官网：<https://www.elastic.co/>
- Github 地址：<https://github.com/elastic/elasticsearch>
- Elasticsearch 5.2 官网文档：<https://www.elastic.co/guide/en/elasticsearch/reference/5.2/index.html>

## Elasticsearch 集群简单操作

- 上一篇章我们已经安装了 Elasticsearch 和 Kibana，所以我们现在启动 Elasticsearch 和 Kibana 访问：<http://192.168.1.127:5601/app/kibana#/dev_tools/console?_g=()>，如下图：
- 需要注意的细节是：Kibana Dev Tools 上面可以写多条 DSL 语句，光标放在哪一条上面，那一条后面有一个播放号可以单独执行，所以没必要删掉旧的语句。

![Kibana Dev Tools](http://img.youmeek.com/2017/elasticsearch-cluster-1.jpg)

- 查询集群健康状况：`GET /_cat/health?v`
- 查询集群中有哪些索引：`GET /_cat/indices?v`
- 简单的索引操作：
	- 新增索引：`PUT /product_index?pretty`
	- 删除指定索引：`DELETE /product_index?pretty`
	- 删除所有索引：`DELETE /_all`
	- 查询索引配置信息：`GET /product_index/_settings`
	- 查询多个索引配置信息：`GET /product_index,order_index/_settings`
	- 查询所有索引配置信息：`GET /_all/_settings`

## Elasticsearch 集群较复杂操作

- 新增索引，并指定 private shard 和 replica shard 数量。

``` json
PUT /order_index
{
  "settings": {
    "index": {
      "number_of_shards": 5,
      "number_of_replicas": 1
    }
  }
}
```


``` json

```


``` json

```

## 其他资料辅助




