## Utilizing Ansible Galaxy for Web Server

### 1. Creating Ansible Role for Database Server Playbook:

**Code:**

```python
---
- name: Install Database Server
  hosts: database_server
  become: yes

  vars:  # Define variables here
	db_server_package: "mysql-server"  # Replace with the appropriate package name

  tasks:
	- name: Update package cache and install the database server package
  	apt:
    	name: "{{ db_server_package }}"
    	state: latest

#Ansible-playbook myplaybook.yml

#ansible-galaxy install geerlingguy.nginx

```
**Creating Database Server**

![Code Execution](https://i.imgur.com/aySQj0x.png)

![Code Execution](https://i.imgur.com/PTzJyf7.png)

![Code Execution](https://i.imgur.com/jmZDtrl.png)


### 2. Ansible Galaxy Role for Web Server Setup

**Code:**

```python
---
- name: Setup Nginx Web Server
  hosts: web_server  # Replace with your target hosts or group
  become: yes

  roles:
	- geerlingguy.nginx

ansible-playbook  your_playbook.yml

```
**Creating Database Server**

![Code Execution](https://i.imgur.com/mkGpzzz.png)

