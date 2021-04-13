# Kafka test notes

## Docker
Most of the config come from this this project. but I had to change the broker image in order to get it start and work with the ports correctly.  The one in the file kept crashing because things could not connect to the bootstrap port.

https://github.com/confluentinc/cp-all-in-one

The example to follow steps to run once services are up
https://docs.confluent.io/platform/current/quickstart/ce-docker-quickstart.html

### Zookeeper

	docker-compose up zookeeper
	docker logs zookeeper
### Broker
	docker-compose up broker
	docker ps  
	docker logs broker
See Kafkacat commands below to check on the broker

### schema registry

	docker-compose up schema-registry
https://docs.confluent.io/platform/current/schema-registry/schema_registry_onprem_tutorial.html#schema-registry-onprem-tutorial

### connect
	docker-compose up connect

https://docs.confluent.io/3.1.1/cp-docker-images/docs/tutorials/connect-avro-jdbc.html

### Control Center
	docker-compose up control-center

Control center URL: http://localhost:9021

## kafkacat

Install via brew
	brew install kafkacat

List topics
	kafkacat -b localhost:19092 -L

Producer 
On the command line - ctrl^d once done
	kafkacat -b localhost:19092 -P -t stevetest

From a file
	kafkacat -b localhost:9092 -t <my_topic> -T -P -l /tmp/msgs

Consumer 
	 kafkacat -b localhost:19092 -C -t stevetest
