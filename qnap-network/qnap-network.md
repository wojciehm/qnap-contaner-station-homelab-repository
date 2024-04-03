# QNAP Network in Docker
In order to create a network with your desired configuration I use following code.


```
docker network create -d qnet --opt=iface=eth4 --ipam-driver=qnet --ipam-opt=iface=eth4 --subnet=192.168.0.0/16 --gateway=192.168.192.1 qnet-static
```
Let me break down what options do we have in network creation:
- Option **-d** - we need to specify qnet as a driver
- Option **-opt** - we can specify a


https://qnap-dev.github.io/container-station-api/qnet.html