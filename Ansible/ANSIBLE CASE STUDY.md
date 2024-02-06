# ANSIBLE CASE STUDY 
You are a Devops Engineer and the organization you are working on needs to set up two configuration 
management server groups. One for Apache another for Nginx. Being a Devops Engineer it is your task 
to deal with this configuration management issue. 
Let us see the tasks that you need to perform using Ansible. 
### 1. Create two Server Groups. One for Apache and another for Nginx. 
### 2. Push two html files with their server information. 

Make sure that you don’t forget to start the *services* once the installation is done. Also send post 
installation messages for both the server groups. 
Using *Ansible Roles* accomplish the above the tasks. 
Also, once the Apache server configuration is done you need to install *Java* on that server group using 
ansible role in a *playbook*.


Created an *inventory file* to define the target hosts and group them as apache and nginx:

```
[apache]
apache_node_1
apache_node_2

[nginx]
nginx_node_1
nginx_node_2
```

Created a role called ansible-apache to install Apache and push the HTML file with server information to the target hosts in the apache group
i defined the tasks for installing Apache and pushing the HTML file in ansible-apache/tasks/main.yml as follows:

```
---
- name: Install Apache
  become: true
  apt:
    name: apache2
    state: present

- name: Copy HTML file
  copy:
    src: files/apache.html
    dest: /var/www/html/index.html

- name: Start Apache service
  become: true
  service:
    name: apache2
    state: started

- name: Post installation message
  debug:
    msg: "Apache installation and configuration completed successfully."
```

Created another role called ansible-nginx to install Nginx and push the HTML file with server information to the target hosts in the nginx group
i defined the tasks for installing Nginx and pushing the HTML file in ansible-nginx/tasks/main.yml as follows:

```
---
- name: Install Nginx
  become: true
  apt:
    name: nginx
    state: present

- name: Copy HTML file
  copy:
    src: files/nginx.html
    dest: /var/www/html/index.html

- name: Start Nginx service
  become: true
  service:
    name: nginx
    state: started

- name: Post installation message
  debug:
    msg: "Nginx installation and configuration completed successfully."
```

Created a playbook called deployment.yml to deploy the roles on the target hosts based on the group
i defined the playbook as follows:

```
---
- name: Deploy roles
  hosts: all
  become: true
  roles:
    - { role: ansible-apache, when: "'apache' in group_names" }
    - { role: ansible-nginx, when: "'nginx' in group_names" }
```

Created another role called ansible-java to install Java on the target hosts in the apache group
i defined the tasks for installing Java in ansible-java/tasks/main.yml as follows:

```
---
- name: Install Java
  become: true
  apt:
    name: default-jdk
    state: present
```

Finally, i executed the playbook using the ansible-playbook command 

```bash
ansible-playbook -i <path-to-inventory-file> deployment.yml
```
