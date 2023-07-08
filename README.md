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
2. In **mnt/keys** folder - replace the priavte key with your server key (e.g. EC2)  
3. In **mnt/hosts** file - Change the IP address to the IP address of the machine/s you want to control.   

4. Start container mounting files:  
Mac / Linux users
``` bash
docker run -it -v $(pwd)/mnt:/opt/ansible dgotlieb/ansible-controller:1.0.0 /bin/bash
```
Windows users (CMD)
``` bash
docker run -it -v %cd%/mnt:/opt/ansible dgotlieb/ansible-controller:1.0.0 /bin/bash
```
    
5. Restrict key permissions:
``` bash
chmod 400 keys/private.pem
```

6. Validate you can ping your hosts using Ansible:
``` bash
ansible all -m ping
```


### Local build (optional)  
if you wish to build the Docker image locally, you can run the below commands:  
1. Build the Docker image:  
``` bash
docker build -t ansible-controller .
```
2. Run the container using:  
Mac / Linux users  
``` bash
docker run -it -v $(pwd)/mnt:/opt/ansible ansible-controller /bin/bash
```
  
Windows users (CMD)  
``` bash
docker run -it -v %cd%/mnt:/opt/ansible ansible-controller /bin/bash
```
