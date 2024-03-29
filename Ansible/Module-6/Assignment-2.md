# Module-6: Ansible Assignment - 2 
You have been asked to: 
### 1. Create a script which can add text “This text has been added by custom script” to /tmp.1.txt 
### 2. Run this script using Ansible on all the hosts


To create a script that adds text to /tmp.1.txt and run it using Ansible on all hosts, i followed the following steps

Step 1: Create the script
Create a new script file, text.sh and added the following script

#!/bin/bash
echo "This text has been added by custom script" >> /tmp.1.txt
This script will append the specified text to the end of the file /tmp.1.txt.

Step 2: Copy the script to the target nodes
To copy the script to the target nodes, you can use the copy module in Ansible. Create a new playbook file, named script.yml
and i added the following script

```
---
- name: Copy script to all hosts
  hosts: all
  tasks:
    - name: Copy script to target node
      copy:
        src: /path/to/add_text.sh
        dest: /tmp/add_text.sh
        mode: '0755'
```
This playbook will copy the add_text.sh script to the /tmp directory on all the target nodes and set its permission to 755 (read, write, execute for owner; read and execute for group and others).

Step 3: Run the script on the target nodes
To run the script on the target nodes, Create a new playbook file, named script.yml, with the following content:
```
---
- name: Run script on all hosts
  hosts: all
  tasks:
    - name: Run script on target node
      command: /tmp/add_text.sh
```
This playbook will execute the text.sh script on all the target nodes.

Step 4: Run the playbooks
To run the playbooks and execute the script on the target nodes, i ran the following commands:

```
ansible-playbook -i <inventory_file> copy_script.yml
ansible-playbook -i <inventory_file> run_script.yml

```
Where <inventory_file> is the file that contains the list of target nodes.

