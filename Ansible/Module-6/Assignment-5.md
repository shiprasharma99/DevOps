# Module-6: Ansible Assignment - 5 
You have been asked to: 
### 1. Create a new deployment of ansible cluster of 5 nodes 
### 2. Label 2 nodes as test and other 2 as prod 
### 3. Install java on test nodes 
### 4. Install mysql-server on prod nodes 
Use Anisble roles for the above, group the hosts under test and prod


Step 1: Create an inventory file to define the target hosts and group them as test and prod:

```markdown
[test]
test_node_1
test_node_2

[prod]
prod_node_1
prod_node_2
```

Step 2: Create a role called ansible-java to install Java on test nodes
i defined the tasks for installing Java in ansible-java/tasks/main.yml as follows:

```css
---
- name: Install Java
  become: true
  apt:
    name: default-jdk
    state: present

```
Step 3: Create another role called ansible-mysql to install MySQL on prod nodes
i defined the tasks for installing MySQL in ansible-mysql/tasks/main.yml as follows:

```css
---
- name: Install MySQL Server
  become: true
  apt:
    name: mysql-server
    state: present

```
Step 4: Create a playbook called deployment.yml to deploy the roles on the target hosts based on the group
i defined the playbook as follows:

```css
---
- name: Deploy roles
  hosts: all
  become: true
  roles:
    - { role: ansible-java, when: "'test' in group_names" }
    - { role: ansible-mysql, when: "'prod' in group_names" }

```
Finally, i executed the playbook using the ansible-playbook command as follows:

```bash
ansible-playbook -i <path-to-inventory-file> deployment.yml
```





