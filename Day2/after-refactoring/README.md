### You may execute the playbook as shown below

ansible-playbook install-nginx.yml

### You can find the ip address of the ansible node as shown below

#### In case of docker container ansible nodes

ansible ubuntu1 -m shell -a "hostname -i"

ansible ubuntu2 -m shell -a "hostname -i"

#### In case of virtual machines or on-premise server or cloud based machines, you may try this

ansible ubuntu1  -m shell -a "ifconfig"

ansible ubuntu2  -m shell -a "ip addr show"

### You may access the web page as shown below

### Access web page from ubuntu1 ansible node

curl http://172.17.0.2

### Access web page from ubuntu ansible node

curl http://172.17.0.3


### Creating centos containers

docker run -d --name centos1 --hostname centos1 -p 2003:22 -p 8003:80 tektutor/ansible-centos

docker run -d --name centos2 --hostname centos2 -p 2004:22 -p 8004:80 tektutor/ansible-centos
