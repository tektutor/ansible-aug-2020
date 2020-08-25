
### Creating ubuntu containers (in case you already haven't created)

docker run -d --name ubuntu1 --hostname ubuntu1 -p 2001:22 -p 8001:80 tektutor/ansible-ubuntu

docker run -d --name ubuntu2 --hostname ubuntu2 -p 2002:22 -p 8002:80 tektutor/ansible-ubuntu


### Creating centos containers

docker run -d --name centos1 --hostname centos1 -p 2003:22 -p 8003:80 tektutor/ansible-centos

docker run -d --name centos2 --hostname centos2 -p 2004:22 -p 8004:80 tektutor/ansible-centos

### You can find the ip address of the ansible node as shown below

#### In case of docker container ansible nodes

ansible ubuntu1 -m shell -a "hostname -i"

ansible ubuntu2 -m shell -a "hostname -i"

#### In case of virtual machines or on-premise server or cloud based machines, you may try this

ansible ubuntu1  -m shell -a "ifconfig"

ansible ubuntu2  -m shell -a "ip addr show"

### You may need to execute the playbook as shown below

ansible-playbook install-nginx.yml

### You may now copy the default file from ubuntu container as shown below ( Assumption is centos1 container ip is 172.17.0.2 )
scp root@172.17.0.2:/etc/nginx/sites-available/default .

### You may now copy the default.conf file from centos container as shown below ( Assumption is centos1 container ip is 172.17.0.4 )
scp root@172.17.0.4:/etc/nginx/conf.d/default.conf .

### You may access the web page as shown below

### Access web page from ubuntu1 ansible node

curl http://172.17.0.2

### Access web page from ubuntu ansible node

curl http://172.17.0.3
