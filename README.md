# Ubuntu Setup

Ansible playbook to setup Ubuntu in a VirtualBox machine for personal usage.

# Getting started

To setup your environment after installing Ubuntu:

1. Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu)

```sh
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install --yes ansible
```

2. Install git

```sh
sudo apt install --yes git
```

3. Clone this repo

```sh
git clone https://github.com/stevevega/ubuntu-setup.git
```

4. Setup VirtualBox

```sh
ansible-playbook -i inventories/localhost -K virtualbox.yml
```

# Usage

To run the default playbook:

```sh
ansible-playbook -i inventories/localhost -K ubuntu.yml
```
