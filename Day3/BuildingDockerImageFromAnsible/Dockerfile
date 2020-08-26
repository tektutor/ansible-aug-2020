FROM ubuntu:16.04
LABEL author="Jeganathan Swaminathan <jegan@tektutor.org>"

RUN apt update && apt install -y openssh-server python3 sudo

RUN useradd -m -p devops -s /bin/bash devops 
RUN echo "devops:devops" | chpasswd

RUN mkdir -p /home/devops/.ssh
RUN chown -R devops:devops /home/devops
RUN chmod -R 755 /home/devops

COPY authorized_keys /home/devops/.ssh/authorized_keys
COPY sudoers /etc/sudoers

RUN mkdir -p /var/run/sshd

EXPOSE 80
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"] 
