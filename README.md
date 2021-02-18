# kafka-installation

## kafka-commands

Open %KAFKA_HOME% folder (e.g., C:\kafka-version).

Use a different PowerShell as Administrator window for each process.  

We may minimize windows, but they must remain  open to keep the processes running.
  
Window 1 - Run Zookeeper Service  (keep window open)
```
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
Window 2 - Run Kafka Service (keep window open)
```
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
Window 3 (temporary) - Execute One-Time Commands - create, list, delete topics 
```
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic krish-msgs
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list
```
Window 4 - Run Kafka Producer (will provide a > prompt for writing messages)
```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic krish-msgs
```
Window 5 - Run Kafka Consumer (to show messages from the beginning)
```
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic krish-msgs --from-beginning
```
