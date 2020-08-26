### First you need ensure your public key is copied under current directory as authorized_keys

### Switch to the below dir
cd ansible-aug-2020/Day3/SudoElevation

cp /root/.ssh/id_rsa.pub authorized_keys

### You need to build a new docker image with the Dockerfile

docker build -t tektutor/ansible-ubuntu-new .

### You may check if the newly built image is listed 

docker images

### In case you have other containers running you may clean up to avoid confusions

docker rm -f $(docker ps -aq)

### You may create a container out of the newly baked docker image

docker run -d --name ubuntu1 --hostname ubuntu1 -p 2001:22 -p 8001:80 tektutor/ansible-ubuntu-new

docker run -d --name ubuntu2 --hostname ubuntu2 -p 2002:22 -p 8002:80 tektutor/ansible-ubuntu-new

### You may now execute install-nginx playbook 

ansible-playbook install-nginx.yml
