## Taking Screenshot & Upload on S3

**Code:**

```python

#ansible-vault create sensitive_data.yml

b_password: my_secret_password
api_key: my_api_key


#ansible-vault edit sensitive_data.yml

---
- name: Use Encrypted Variables
  hosts: localhost  # You can specify the target hosts as needed
  gather_facts: no  # Disable gathering facts

 tasks:
	- name: Load Encrypted Variables
  	include_vars:
    	file: sensitive_data.yml
    	name: sensitive_data  # Define a variable name to access the encrypted data

	- name: Display Encrypted Variables
  	debug:
    	var: sensitive_data


#ansible-playbook my_playbook.yml --ask-vault-pass


```
**Result of Code:**

![Code Execution](https://i.imgur.com/dJhdcI1.png)
