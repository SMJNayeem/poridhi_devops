# Creating Multi-Container Host Networking using VxLAN Overlay Networks

## For Instance 1:

### sudo apt update

### sudo apt install -y docker.io

### sudo apt install -y apt-utils

### sudo systemctl start docker

### sudo docker network create --subnet 172.18.0.0/16 vxlan-net

![Creating Subnet by Docker Network](/images/img-1-create-docker-network.png)

<p align="center">Fig: Creating Subnet by Docker Network</p>

### ip a

![Check the new Interface](/images/img-1-ip-a.png)

<p align="center">Fig: Check the new Interface</p>

### sudo docker run -d --net vxlan-net --ip 172.18.0.11 ubuntu sleep 3000

![Creating Docker Container and assigning Static IP](/images/img-1-create-docker-container.png)

<p align="center">Fig: Creating Docker Container and assigning Static IP</p>

### sudo docker ps

![Check Container List](/assets/images/img-1-docker-ps.png)

<p align="center">Fig: Check Container List</p>

### sudo docker exec -it 75 bash

### apt-get update

### apt-get install net-tools

### apt-get install iputils-ping

### exit

### sudo ip link add vxlan-demo type vxlan id 100 remote 172.31.81.94 dstport 4789 dev eth0

### sudo ip link set vxlan-demo up

### sudo ip link set vxlan-demo master br-26f55c2232fa

### sudo docker exec -it 75 bash



## For Instance 2:

### sudo apt update

### sudo apt install -y docker.io

### sudo apt install -y apt-utils

### sudo systemctl start docker

### sudo docker network create --subnet 172.18.0.0/16 vxlan-net

![Creating Subnet by Docker Network](/images/img-2-create-docker-network.png)

<p align="center">Fig: Creating Subnet by Docker Network</p>

### ip a

![Check the new Interface](/images/img-2-ip-a.png)

<p align="center">Fig: Check the new Interface</p>

### sudo docker run -d --net vxlan-net --ip 172.18.0.12 ubuntu sleep 3000

![Creating Docker Container and assigning Static IP](/images/img-2-create-docker-container.png)

<p align="center">Fig: Creating Docker Container and assigning Static IP</p>

### sudo docker ps

![Check Container List](/assets/images/img-2-docker-ps.png)

<p align="center">Fig: Check Container List</p>

### sudo docker exec -it e5 bash

### apt-get update

### apt-get install net-tools

### apt-get install iputils-ping

### exit

### sudo ip link add vxlan-demo type vxlan id 100 remote 172.31.85.228 dstport 4789 dev eth0

### sudo ip link set vxlan-demo up

### sudo ip link set vxlan-demo master br-0bbcf3408f28

### sudo docker exec -it e5 bash


## Connection Between Two Interfaces:


### ping 172.31.81.94

![Check if PING Works](/images/img-1-ping.png)

<p align="center">Fig: Check if PING Works</p>



### ping 172.31.81.94

![Check if PING Works](/images/img-2-ping.png)

<p align="center">Fig: Check if PING Works</p>