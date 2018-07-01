# Realtime IoT Data Source Simulator Traffic Data
Real Time IoT data Simulator in Scala lang to feed kafka


## Default Data Structure
    "device_id": 1090011, "ip": "123.231.120.54","city": "C olombo", "latitude": 6.927100, "longitude": 79.861200, "t emp": 31, "timestamp”:1522503549000



## Cloning the project
    https://github.com/OmalPerera/IoT-Data-Source-Simulator-Traffic-Data.git
    
## Configuring & Run the project

You should configure following libararies in order to run this project.
- JAVA
- Scala (v2.11.11 Recommended) [_scala-lang.org installation guide_](https://www.scala-lang.org/download/2.11.11.html)
- Apache Kafka (0.10.2.0 Recommended) [_installation Guide_](https://omalperera.github.io/general/bigdata/2017/11/10/Setting-Up-Apache-Kafka-localy.html)
- Maven [_installation Guide for Mac_](https://omalperera.github.io/howto/2017/12/21/Install-Maven-on-Mac-OSX.html)

<br>

Here onwards navigate to your downloaded **kafka directory** in terminal & execute following commands. Each command should be execute on seperater terminal tabs.

#### Starting Zookeeper Server
    sudo bin/zookeeper-server-start.sh config/zookeeper.properties
     
#### Starting Kafka Server
    sudo bin/kafka-server-start.sh config/server.properties
    
#### Creating a topic
    sudo bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test 
    
#### Running the consumer on console
    sudo bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic test
    
#### Run the `dataGenerator`
Now navigate to the directory where you cloned the project & execute following commands.
    
    mvn clean package
    java -jar dist/RDS-Simulator-1.0.jar
    
That's it! Now check the kafka Console Consumer


## Customizations


#### Changing the data Structure
You can add your own data structure & patterns. Code is direct forward

    val citiesInNewYork = List("Elmira", "Oneonta", "Peekskill", "Albany", "Yonkers")