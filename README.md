# apache-kafka-springBoot-demo

Apache Kafka is a distributed streaming platform, used to process real time data feeds with high throughput and low latency. Here we are doing basic demo program 
of producer-consumer with apache-kafka and spring-boot. The other test cases where such codes can be applied in real time are:
e.g: flights data, sensors data, stocks data, news data etc....

Kafka works based on Publisher and Subscriber model :
![](https://github.com/AadityaUoHyd/apache-kafka-springBoot-demo/blob/master/kafka-pic.jpg)

Kafka Terminology
-----------------
Zookeeper
Kafka Server
Kafka Topic
Message
Publisher
Subscriber

Kafka APIs
----------
Connector API
Publisher API
Subscriber API
Streams API


Spring Boot + Apache Kafka Application
=======================================

Step-1 : Download Zookeeper from below URL

   URL : http://mirrors.estointernet.in/apache/zookeeper/stable/

Step-2 : Download Apache Kafka from below URL

   URL : http://mirrors.estointernet.in/apache/kafka/

Step-3 : Set Path to ZOOKEEPER in Environment variables upto bin folder

Step-4 : Start Zookeeper server using below command from Kafka folder

    Command : zookeeper-server-start.bat zookeeper.properties

Note: Above command will available in kafka/bin/windows folder

Note: zookeeper.properties file will be available in kafka/config folder. You can copy zookeeper.properties and server.properties files from kafka/config folder to kafka/bin/windows folder.

Step-5: Start Kafka Server using below command from Kakfa folder

    Command : kafka-server-start.bat server.properties

Note: server.properties file will be available in config folder (Copied to windows folder)

Step-6 : Create Kakfa Topic using below command from kafka/bin/windows folder

Command : (use this for kafka newer version above 2.2+) #cmd > kafka-topics.bat --create --topic demo-sbms-topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1
          <br><br> (use this for kafka older version below 2.2) #cmd > kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic demo-sbms-topic
          

Step-7 : View created Topics using below command

      Command : kafka-topics.bat --bootstrap-server localhost:9092 --list

Step-8 : Create Spring Boot Project in IDE
===========================================

Step-9: Add below kafka related dependencies in pom.xml

		<dependency>
			<groupId>org.apache.kafka</groupId>
			<artifactId>kafka-streams</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.kafka</groupId>
			<artifactId>spring-kafka</artifactId>
		</dependency>
		<dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-databind</artifactId>
		</dependency>
		

Step-9: Create RestController, KafaProducer and KafaConsumer classes to publish and subsribe message


Step-10: Test application using PostMan.


Sample Data
-----------

[

  {
   "customerId":101,
   "customerName":"Aadi",
   "customerEmail":"aadi@outlook.com"
  },

  {
   "customerId":102,
   "customerName":"Shekhar",
   "customerEmail":"shekhar@gmail.com"
  },

  {
   "customerId":102,
   "customerName":"Santosh",
   "customerEmail":"santosh@hotmail.com"
  }

]
