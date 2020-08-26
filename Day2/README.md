# Configuring Docker Engine to support REST API

### You may check the current status docker.

sudo systemctl status docker

### From the output of above command, you can grab path of the docker service

sudo vim /usr/lib/systemd/system/docker.service

### Under [Servive]

### You need to modify the line as shown below by appending -H tcp://0.0.0.0:4243

ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock -H tcp://0.0.0.0:4243

### To apply the changes, you need restart docker service

sudo systemctl daemon-reload

sudo systemctl restart docker

### Just to double check, ensure the docker service still works after your configuration 

sudo systemctl status docker

### If you see the docker service is active, you have successfully enabled REST API in Docker Engine !
