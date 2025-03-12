## 1. Configure Ansible Inventory File

**Code:**

```python

#Ansible Inventory file content
[webservers]
web1 ansible_host=192.168.1.10 ansible_user=your_user ansible_ssh_private_key_file=~/.ssh/id_rsa

[databases]
db1 ansible_host=192.168.1.20 ansible_user=your_user ansible_ssh_private_key_file=~/.ssh/id_rsa

[loadbalancer]
lb1 ansible_host=192.168.1.30 ansible_user=your_user ansible_ssh_private_key_file=~/.ssh/id_rsa

[all:vars]
ansible_python_interpreter=/usr/bin/python3

#Type the following command to check the inventory file
ansible-inventory --list -y
```
**Configuration of Inventory File**

![Code Execution](https://i.imgur.com/h6q66oa.png)

## 2. Configure Ansible Inventory File

**Code:**

```python

ufw app list
ufw allow OpenSSH
ufw enable
ufw status

# Edit the "sshd_config" file from following aspects:
# 1. Comment the "PasswordAuthentication"
$ 2. Uncomment the "PubKeyAuthentication yes"

vim /etc/ssh/sshd_config

#Generate the ssh-key in master
ssh-keygen -t rsa

#copy this key into node authorized_keys.
cat /root/.ssh/id_rsa.pub

chmod 600 ~/.ssh/authorized_keys
```
**Configuration of Inventory File**

![Code Execution](https://i.imgur.com/jDESBc3.png)

![Code Execution](https://i.imgur.com/Ftd3WsG.png)


## 3. Successful set up of Server & Node

**Code:**

```python

ansible target-host -m ping 

```
**Server & Node are setup**

![Code Execution](https://i.imgur.com/tmsiT5W.png)

## 4. Installation of Apache2 in Node

**Code:**

```python

ansible server  -m apt -a "update_cache=yes" -b

ansible target_host -b -m apt -a "name=apache2 state=present"

ansible servers -b -m service -a "name=apache2 state=started"

ansible servers -b -m service -a "name=apache2 state=stopped"

```
**Installation of Apache2 in Node**

![Code Execution](https://i.imgur.com/2gC2v04.png)











