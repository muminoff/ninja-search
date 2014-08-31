ninja-search
===

[shixiz.com](http://shixiz.com)

### require:

* [flask]()
* [elasticsearch]() or [elasticsearch-rtf]() (自带中文分词)
* [v2ex-scrapy (crawlers)]()

配置
----

elasticsearch-rtf / elasticsearch / bin / service / elasticsearch.conf

默认JAVA HEAP大小为2G，根据你的服务器环境，需要自行调整，一般设置为物理内存的50%.

    set.default.ES_HEAP_SIZE=2048

elasticsearch-rtf / config /elasticsearch.yml

    script.disable_dynamic: false


索引
--------

创建 index  

    curl -XPUT 'localhost:9200/v2'

mapping scheme  

    elasticsearch 下执行
    ./search/init.sh

    elasticsearch-rtf 下执行
    ./search/init_with_ik.sh

mongo index

    db.reply.createIndex({topic_id:1})

索引数据
    
    ./util/mongo2es.py


Run
----

    python index.py

