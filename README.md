# ansible_

ansible-playbook: The Ansible command to execute playbooks.
-i inventory.ini: Specifies the inventory file inventory.ini that contains the list of hosts or groups of hosts where the tasks will be executed.
first-playbook.yaml: The actual playbook file that contains tasks and roles to automate on the target hosts defined in the inventory file.

```
ansible-playbook -i inventory.ini  first-playbook.yaml
```
