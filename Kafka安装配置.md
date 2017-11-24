http://www.jianshu.com/p/64d25dcf8300
set CLASSPATH=,;
# 启动zookeeper:
.\bin\windows\zookeeper-server-start.bat config/zookeeper.properties
# 启动Kafka
.\bin\windows\kafka-server-start.bat config/server.properties
# 创建topic
.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
# 查看topic
.\bin\windows\kafka-topics.bat --list --zookeeper localhost:2181z
# 创建生产者
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic test