
# Ansible Guide

This guide explains how to install and use Ansible, create roles, and push them to Ansible Galaxy.

---

## 1. Install Ansible

To install Ansible using `pip`, run:

```bash
pip install ansible
```

## 2. Check Ansible Version

Once installed, verify the Ansible version by running:

```bash
ansible --version
```

---

## 3. Running an Ansible Playbook

To execute an Ansible playbook with a specific inventory file, use the following command:

```bash
ansible-playbook -i inventory.ini first-playbook.yaml
```

### Explanation:

- **`ansible-playbook`**: The command to run playbooks in Ansible.
- **`-i inventory.ini`**: Specifies the inventory file (`inventory.ini`) that contains the list of hosts or groups where the tasks will be executed.
- **`first-playbook.yaml`**: The actual playbook file containing tasks and roles to automate on the target hosts defined in the inventory file.

---

## 4. Creating an Ansible Role

To create a new role, run the following command:

```bash
ansible-galaxy role init test
```

This will generate the necessary folder structure for an Ansible role.

### Role Structure:

```
my_role/
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
├── tests/
│   ├── inventory
│   └── test.yml
└── vars/
    └── main.yml
```

---


# Ansible Playbook to Role Conversion Guide

This guide explains how to run an Ansible playbook and convert the playbook into a role.

---

## 1. Running the Playbook

To run an Ansible playbook with a specific inventory file, use the following command:

```bash
ansible-playbook -i inventory.ini first-playbook.yaml
```

### Example Playbook (`first-playbook.yaml`):

```yaml
---
- hosts: localhost
  remote_user: root
  roles:
    - test
```

---

## 2. Converting the Playbook to a Role

### Step 1: Create the Role

To convert the playbook into a role, create a new role using the following command:

```bash
ansible-galaxy role init test
```

### Step 2: Define Tasks in `main.yaml`

Once the role structure is created, place the tasks in `main.yaml` under the `test/tasks` directory.

#### Example Task Structure:

Place the following content in `test/tasks/main.yaml`:

```yaml
---
# Example task structure
- name: Ensure Nginx is installed
  apt:
    name: nginx
    state: present
```

---

## 3. Run the Playbook with the Role

Now that the role is set up, you can run the playbook again using:

```bash
ansible-playbook -i inventory.ini first-playbook.yaml
```

This will run the tasks defined in the `test` role.

---








## 5. Pushing Your Ansible Roles to Ansible Galaxy

### Step 1: Verify `ansible-galaxy` CLI

Ensure the `ansible-galaxy` CLI is installed and working:

```bash
ansible-galaxy --version
```

### Step 2: Push Your Role to GitHub

After creating your role, push it to your GitHub repository with the following commands:

```bash
cd <role-name>
git init
git remote add origin https://github.com/your_github_username/my_role.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

### Step 3: Import the Role to Ansible Galaxy

To upload your role to Ansible Galaxy, use the following command:

```bash
ansible-galaxy role import <your_github_username> <role-name>
```

---
