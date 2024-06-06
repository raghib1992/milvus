# Install Milvus Standalone with Docker Compose

### Download the YAML file
```
wget https://github.com/milvus-io/milvus/releases/download/v2.0.2/milvus-standalone-docker-compose.yml -O docker-compose.yml
```

### Start Milvus
```
sudo docker-compose up -d
```
### check if the containers are up and running.
```
sudo docker-compose ps
```