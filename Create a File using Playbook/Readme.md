## Taking RDC to EC2-Ubuntu:

### Creating a File Using Ansible Playbook

**Code:**

```python
---
- name: Create file in /tmp directory
  hosts: localhost
  tasks:
	- name: Create a file in /tmp directory
  	ansible.builtin.file:
    	path: /tmp/test_file.txt
    	state: touch
```
**Code Execution:**

![Code Execution](https://i.imgur.com/fmhYWy5.png)




