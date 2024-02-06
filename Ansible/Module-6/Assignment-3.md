# Module-6: Ansible Assignment - 3 
You have been asked to: 
### 1. Create Ansible Role called “ansible-new”
### 2. Install apache2 on slave1 and nginx on slave2 
Above should be implemented using Ansible Roles


To create an Ansible role called ansible-new and install Apache on slave1 and Nginx on slave2, i followed the following steps:

Step 1: Create the Ansible Role
Create a new directory called ansible-new in your Ansible roles directory, which is located in ~/ansible/roles
Inside this directory, create a tasks subdirectory and a file called main.yml inside it
i added the following content to the main.yml file

```
---
- name: Install Apache on slave1
  hosts: slave1
  become: true
  tasks:
    - name: Install Apache
      apt:
        name: apache2
        state: present

- name: Install Nginx on slave2
  hosts: slave2
  become: true
  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present
```

This role contains two tasks that will install Apache on slave1 and Nginx on slave2 using the apt module.

Step 2: Use the Ansible Role
To use the ansible-new role in a playbook
create a new playbook file, named use_role.yml, 
added the following command:

```
---
- name: Use Ansible role
  hosts: all
  become: true
  roles:
    - ansible-new
```

This playbook will run the ansible-new role on all the target nodes.

Step 3: Run the playbook
To run the playbook and install Apache on slave1 and Nginx on slave2, 
i ran the following command:

```bash
ansible-playbook -i <inventory_file> use_role.yml
```
Where <inventory_file> is the file that contains the list of target nodes.

