## kakfa-based Fabric network

### Prerequisites and setup: 

* [Docker](https://www.docker.com/products/overview) - v1.12 or higher
* [Docker Compose](https://docs.docker.com/compose/overview/) - v1.8 or higher
* [Git client](https://git-scm.com/downloads) - needed for clone commands
* Download docker images

```
cd fabric-kafka-network

Once you have completed the above setup, you will be provisioned a local network with following configuration:
* 4 Kafka Brokers + 3 Zookeepers
* 3 Orderers
* 2 CA Orgs
* 4 peers (2 peers per Org)

启动网络
docker-compose up -d   
  
进入cli
docker exec -it cli bash 

创建通道
export CHANNEL_NAME=mychannel 
peer channel create -o orderer0.example.com:7050 -c $CHANNEL_NAME -f ./channel-artifacts/mychannel.tx 
    
其他的和solo排序一样


