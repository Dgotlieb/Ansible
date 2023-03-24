# Ansible
A simple Docker image for Ansible

### Prerequesits:
* Git
* Docker


### Initial setup:
1. Clone this repository:
``` bash
git clone https://github.com/Dgotlieb/Ansible.git
```  
2. In **keys** folder - replace the priavte key with your server key (e.g. EC2)  
3. In **hosts** file - Change the IP address to the IP address of the machine/s you want to control.   

4. Build the Docker image:  
``` bash
docker build -t ansible-controller .
```
5. Start container mounting files:  
``` bash
docker run -it -v $(pwd)/mnt:/opt/ansible ansible-controller /bin/bash
```
    
6. Restrict key permissions:
``` bash
chmod 400 /opt/ansible/private.pem
```

6. Validate you can ping your hosts using Ansible:
``` bash
ansible all -m ping
```

