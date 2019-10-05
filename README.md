### Sample application using kafka

Two application kafka-multiple-consumer and kafka-multiple-producer. 

Producer application produces prices every 5 second and send value to kafka topic 'prices'.

Consumer application (PriceConverter) retrieve price from the topic and process and send to the stream 'my-data-stream'

Get prices using the http request  http://localhost:8080/prices/stream

### How to Run?

* generate jar file

```
mvn clean package -f kafka-multiple-consumer/pom.xml
mvn clean package -f kafka-multiple-producer/pom.xml
```

* build docker-compose.yaml

```
docker-compose up
```

* logs will show the message that price is generated

```
producer_1   | 2019-10-05 11:26:57,687 INFO  [io.sma.rea.mes.kaf.KafkaSink] (vert.x-eventloop-thread-0) Message org.eclipse.microprofile.reactive.messaging.Message$$Lambda$268/793159261@27dc4352 sent successfully to Kafka topic 'prices'
```

* After that Open http://localhost:8080/prices.html
