# Ansible Commands

### You may execute the ping playbook as shown below

ansible-playbook -i inventory ping.yml

### As we have ansible.cfg file in the current directory,  you may also invoke conveniently as below

ansible-playbook ping.yml

### You may also try using the refactored hosts file

ansible -i hosts ping.yml

### You may also test the inventory file kept at Ansible Recommended Directory Structure

cd AnsibleRecommendedDirStructure

ansible -i hosts all -m ping
