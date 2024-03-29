# Module-6: Ansible Assignment - 4 
You have been asked to: 
### 1. Use the previous deployment of ansible cluster 
### 2. Configure the files folder in “ansible-new” role with index.html which should be replaced 
with the original index.html 
### 3. Configure the handlers folder in “ansible-new” role for restarting the nginx service
All of the above should only happen on the slave which has nginx installed


Step 1: Add new files to the ansible-new role
Inside the ansible-new role directory, create a new directory called files
Copy the original index.html file to this directory and replace it with a new index.html file 
create a new index.html file with the following content:

```
<!DOCTYPE html>
<html>
<head>
	<title>Welcome to my website</title>
</head>
<body>
	<h1>Hello World!</h1>
	<p>This is my website.</p>
</body>
</html>
```

Step 2: Configure the handlers folder
Inside the ansible-new role directory, create a new directory called handlers
Create a file called main.yml with the following content:

```
---
- name: Restart Nginx service
  systemd:
    name: nginx
    state: restarted

```
This handler will restart the Nginx service whenever it is notified by a task that modifies the Nginx configuration.

Step 3: Modify the ansible-new role tasks
Modify the main.yml file in the ansible-new role tasks directory to include the following tasks:

```
---
- name: Copy index.html file
  hosts: slave2
  become: true
  tasks:
    - name: Copy index.html
      copy:
        src: files/index.html
        dest: /var/www/html/index.html
      notify:
        - Restart Nginx service
```

This task will copy the index.html file from the files folder to the Nginx web root directory on slave2, 
and then notify the Restart Nginx service handler to restart the Nginx service.

Step 4: Run the playbook
To run the playbook and configure the files folder and handlers folder in the ansible-new role, 
i ran the following command:

```bash
ansible-playbook -i <inventory_file> use_role.yml
Where <inventory_file> 
```
is the file that contains the list of target nodes

