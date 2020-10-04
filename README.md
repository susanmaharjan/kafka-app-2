# kafka-app-2
## Prerequisities
- OpenJDK
- Apache Zookeeper
- installed and working
- Apache Kafka
- installed and working
## Start Zookeeper
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

## Start Kafka
.\bin\windows\kafka-server-start.bat .\config\server.properties

## Create the Topic
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic bucketlist

## Compile and Build the Fat Jar File
mvn clean compile assembly:single

## Start Comsumer
java -cp target/kafka-app-2-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.susanmaharjan.Consumer bucketlist group1

## Start Producer
java -cp target/kafka-app-2-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.susanmaharjan.Producer bucketlist