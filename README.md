# Flink-Kafka

After downloading confluent-kafka

# Start/Stop confluent
sudo ./confluent start #to start localhost:9021
sudo ./confluent stop #to stop it
sudo ./confluent destroy #to destory logs/data if something doesnt work last option)

### in new terminals for everycommand
#### Start a new topic: test
./bin/kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
#### Start producer
./bin/kafka-console-producer --broker-list localhost:9092 --topic test
#### Start consumer 
./bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic test --from-beginning

##### terminal where topic was created can be used for data-genration
./bin/ksql-datagen schema=./MySchema.json format=json key=rawid topic=test iterations=30 maxInterval=05
