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
