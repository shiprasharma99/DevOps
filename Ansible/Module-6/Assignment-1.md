# Module-6: Ansible Assignment - 1 
You have been asked to: 
### 1. Setup Ansible cluster with 3 nodes 
### 2. On slave1 install java 
### 3. On slave 2 install mysql-server 
Do the above tasks using Ansible playbooks


To set up an Ansible cluster with 3 nodes and install Java on slave1 and MySQL server on slave2

Step 1: Install Ansible on your master node
i ran the following command on my master node:


```bash
sudo apt-get update
sudo apt-get install ansible
```
Step 2: Added the slave nodes to the Ansible inventory
for this i added the IP addresses of the my nodes to the inventory file
for this i created an inventory file named hosts.ini with the following content:

```
[cluster]
slave1 ansible_host=<slave1_ip_address>
slave2 ansible_host=<slave2_ip_address>

```
Step 3: Create a playbook to install Java on slave1
Create a new playbook file named install_java.yml with the following content:

```
- name: Install Java on slave1
  hosts: slave1
  become: true
  tasks:
    - name: Install Java
      apt:
        name: openjdk-8-jdk
        state: present
```

This playbook tells Ansible to install the openjdk-8-jdk package on the slave1 node using the apt module.

Step 4: Create a playbook to install MySQL server on slave2
Create a new playbook file named install_mysql.yml with the following content:

```
---
- name: Install MySQL server on slave2
  hosts: slave2
  become: true
  tasks:
    - name: Install MySQL server
      apt:
        name: mysql-server
        state: present
```

This playbook tells Ansible to install the mysql-server package on the slave2 node using the apt module.

Step 5: Run the playbooks
To run the playbooks and install the software on the target nodes
i ran the following command

```bash 
ansible-playbook -i hosts.ini install_java.yml
ansible-playbook -i hosts.ini install_mysql.yml
```
This will execute the playbooks on the respective nodes and install the required software.

