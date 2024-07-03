# Install Milvus Python SDK
### Requirements
- Python 3.7 or later is required.
```sh
# check version
python3 --version
```
- Google protobuf is installed. 
```sh
pip
pip3 --version 
pip3 install protobuf==3.20.0
```
- grpcio-tools is installed.
```sh
pip3 install grpcio-tools jupyterlab
```

### Create virtual env
```sh
sudo apt install python3-venv
python3 -m venv milvus_env
# to activate the env
source ~/milvus_env/bin/activate
# install
python3 -m pip install pymilvus==2.4.3
pip3 install pymilvus==2.4.3 grpcio-tools jupyterlab protobuf==3.20.0

# Verify installation
python3 -c "from pymilvus import Collection"

# to diactivate
deactivate
```

### Start jupyter-lab

```sh
jupyter-lab
```
- Create new notebook by click on python3 notebook icon
- rename: milvus_hello_world
- Importing few module

```py
from pymilvus import connections, utility
# this include username and password of milvus

# to make connection
connections.connect(
    host='localhost',
    port='19530'
)
# to verify connection
utility.list_collections()
```