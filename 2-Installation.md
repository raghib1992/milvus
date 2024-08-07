# Install Milvus Standalone with Docker Compose

### Download the YAML file
```sh
wget https://github.com/milvus-io/milvus/releases/download/v2.4.4/milvus-standalone-docker-compose.yml -O docker-compose.yml
```

### Start Milvus
```
sudo docker compose up -d
```
### check if the containers are up and running.
```
sudo docker compose ps
```
# Install Milvus on kubernetes
### Helm
- Install Helm CLI.
- Create a K8s cluster.
- Install a StorageClass

```sh
kubectl get sc

NAME                 PROVISIONER                RECLAIMPOLICY   VOLUMEBINDINGMODE   ALLOWVOLUMEEXPANSION   AGE
standard (default)   k8s.io/minikube-hostpath   Delete          Immediate           false                  78d
```
-  add Milvus Helm repository
```sh
helm repo add milvus https://zilliztech.github.io/milvus-helm/
```
- fetch Milvus charts from the repository
```sh
helm repo update
```
- Deploy a Milvus cluster
```sh
helm install my-release milvus/milvus
```
# Install using Docker

- Install Milvus in Docker
- Milvus provides an installation script to install it as a docker container. The script is available in the Milvus repository. To install Milvus in Docker, just run

### Download the installation script
```sh
curl -sfL https://raw.githubusercontent.com/milvus-io/milvus/master/scripts/standalone_embed.sh

# Start the Docker container
bash standalone_embed.sh start
```
### After running the installation script:

- A docker container named milvus has been started at port 19530.
- An embed etcd is installed along with Milvus in the same container and serves at port 2379. Its configuration file is mapped to embedEtcd.yaml in the current folder.
- The Milvus data volume is mapped to volumes/milvus in the current folder.
- You can stop and delete this container as follows
```sh
# Stop Milvus
bash standalone_embed.sh stop

# Delete Milvus data
bash standalone_embed.sh stop
```

