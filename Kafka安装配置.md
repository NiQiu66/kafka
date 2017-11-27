http://www.jianshu.com/p/64d25dcf8300
set CLASSPATH=,;
# 启动zookeeper:
.\bin\windows\zookeeper-server-start.bat config/zookeeper.properties
# 启动Kafka
.\bin\windows\kafka-server-start.bat config/server.properties
# 创建topic
.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
# 查看topic列表
.\bin\windows\kafka-topics.bat --list --zookeeper localhost:2181
# 查看某一topic描述
.\bin\windows\kafka-topics.bat --describe --zookeeper localhost:2181 --topic my-replicated-topic
# 创建生产者
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic test
# 创建消费者
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test --from-beginning
# windows 杀进程
wmic process where "caption = 'java.exe' and commandline like '%server-1.properties%'" get processid
taskkill /pid 6016 /f




CMD工具:http://blog.xinshangshangxin.com/2015/02/22/ConEmu%E8%AE%BE%E7%BD%AE%E5%BD%93%E5%89%8D%E7%9B%AE%E5%BD%95%E6%89%93%E5%BC%80/