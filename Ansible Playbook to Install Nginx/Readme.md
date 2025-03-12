## Nginx Installation in Node via Playbook

**Code:**

```python
---- 
name: Install Nginx on Ubuntu
  hosts: server
  become: yes

  tasks:
	- name: Update APT package cache
  	apt:
    	update_cache: yes

	- name: Install Nginx
  	apt:
    	name: nginx
    	state: latest

	- name: Start Nginx and enable it at boot
  	service:
    	name: nginx
    	state: started
    	enabled: yes

```
**Nginx Successfully Installed**

![Code Execution](https://i.imgur.com/6OjjvPe.png)




