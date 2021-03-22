###启动zookeeper 管理kafka

bin/zookeeper-server-start.sh config/zookeeper.properties

###启动kafka服务

bin/kafka-server-start.sh config/server.properties

### 创建一个消息主体topic

bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 

###发送消息

bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test

###启动消费者

bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning

###使用kafka connect组件 导入数据/导出数据

####创建连接器

   1 创建测试文件（被导入）

​	echo -e "foo\nbar" > test.txt

   2 启动连接器进程（3个进程）

​       bin/connect-standalone.sh config/connect-standalone.properties config/connect-file-source.properties config/connect-file-sink.properties

第一个连接器进程connect-standalone.properties

kafka连接进程，内容：关于启动连接进程，broken ->connect->外部数据

第二个连接器进程connect-file-source.properties

连接器从哪个文件读取数据放入 kafka topic(配置文件决定connect-file-source.properties)

第三个连接器进程connect-file-sink.properties

连接器从kafka topic 读取信息放入到哪个文件(配置文件决定connect-file-sink.properties)

启动控制台查看文件topic connect-test 信息变化

####启动控制台查看主题消息变化

bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic connect-test --from-beginning

###使用kafka streams 去处理数据

 1 创建输入主题

bin/kafka-topics.sh --create \

​    --bootstrap-server localhost:9092 \

​    --replication-factor 1 \

​    --partitions 1 \

​    --topic streams-plaintext-input

Created topic "streams-plaintext-input".

2 创建输出主题

bin/kafka-topics.sh --create \

​    --bootstrap-server localhost:9092 \

​    --replication-factor 1 \

​    --partitions 1 \

​    --topic streams-wordcount-output \

​    --config cleanup.policy=compact

Created topic "streams-wordcount-output".

启动demo代码流计算处理

bin/kafka-run-class.sh org.apache.kafka.streams.examples.wordcount.WordCountDemo

控制台 对主题发送消息

bin/kafka-console-producer.sh --broker-list localhost:9092 --topic streams-plaintext-input

控制台查看主题信息

bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 \

​    --topic streams-wordcount-output \

​    --from-beginning \

​    --formatter kafka.tools.DefaultMessageFormatter \

​    --property print.key=true \

​    --property print.value=true \

​    --property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer \

​    --property value.deserializer=org.apache.kafka.common.serialization.LongDeserializer

 

 

 

 