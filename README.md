# Ubuntu Setup

Ansible playbook to setup an Ubuntu machine for personal usage.

# Usage

Make sure to have [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu) installed:

```sh
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

Then run the following command:

```sh
ansible-playbook -i inventories/localhost -K ubuntu.yml
```
