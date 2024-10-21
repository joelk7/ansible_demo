## Ansible Playbook Command
to install ansible

```
pip install ansible

```

Check version
```
ansible --version

```



To run an Ansible playbook with a specific inventory file, use the following command:

```bash
ansible-playbook -i inventory.ini first-playbook.yaml
```


ansible-playbook: The Ansible command to execute playbooks.

-i inventory.ini: Specifies the inventory file (inventory.ini) that contains the list of hosts or groups where the tasks will be executed.

first-playbook.yaml: The actual playbook file containing tasks and roles to automate on the target hosts defined in the inventory file.



Create Role  named test
```
ansible-galaxy role init test
```


  test/
  ├── defaults/
  │   └── main.yml
  ├── files/
  ├── handlers/
  │   └── main.yml
  ├── meta/
  │   └── main.yml
  ├── tasks/
  │   └── main.yml
  ├── templates/
  ├── vars/
      └── main.yml
