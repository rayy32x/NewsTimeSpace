# NewsTimeSpace
# 新闻时空
项目描述：SpringCloud微服务项目，主要内容包括：实现单点登录，新闻的延迟发布与自动审核，远程调用实现微服务，app端新闻页面自动生成，新闻的异步上下架，新闻关键词检索，新闻的点赞评论等行为，热点新闻的实时与定时推荐等。
技术栈：SpringCloudAlibaba+Nacos+Feign+Gateway+MySQL+Redis+MongoDB+MyBatis-Plus+Kafka+Nginx
+JWT+Elasticsearch+Logstash+Kibana+xxl-job+Sentinel+Seata+MinIO+Freemarker
● 使用JWT作为Token实现单点登录，对密码进行MD5+盐加密，在Gateway网关中做Token有效性检查。
● 使用Redis的List结合SortedSet实现新闻的延迟发布。使用xxl-job定时拉取缓存中的任务执行，并定期同步缓存；
● 使用Tees4j的OCR接口对用户发布的新闻任务进行审核并消费，使用Feign远程调用app端接口新增新闻文章；
● 使用Elasticsearch创建索引，实现多条件全局检索，以及搜索结果高亮；使用Seata的AT模式解决分布式事务问题；
● 使用Freemarker模板引擎自动生成新闻html页面，并上传到MinIO对象存储服务器中供前端使用；
● 使用MongoDB文档数据库存储用户的搜索历史和评论，以支持用户的评论和搜索历史功能;
● 使用Kafka消息队列实现服务之间的异步通信，包括新闻上下架的通信，以及新闻发布时通知搜索服务创建ES索引等；
● 使用xxl-job定时根据用行为的不同权重计算新闻分值，将分值最高的30条数据作为热点数据存入Redis中优先展示；
● 使用Kafka-Stream对行为数据进行定时聚合，实现对新闻分值的实时计算，进而实现针对每个频道的实时新闻推荐。
● 使用Elasticsearch+Logstash+Kibana(ELK)实现可视化日志采集，使用Sentinel实现对服务的限流、降级、熔断。
