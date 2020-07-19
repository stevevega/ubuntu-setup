# Ubuntu Setup

Ansible playbook to setup Ubuntu for personal usage.

# Getting started

To setup your environment after installing Ubuntu:

1. Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu)

```sh
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install --yes ansible
# to prevent: repository does not have a release file error.
sudo apt-add-repository --yes -r ppa:ansible/ansible
```

2. Install git

```sh
sudo apt install --yes git
```

3. Clone this repo

```sh
git clone https://github.com/stevevega/ubuntu-setup.git
```

4. Setup VirtualBox Guest Additions (when using VirtualBox)

```sh
sudo apt install virtualbox-guest-additions-iso
sudo mount -o loop /usr/share/virtualbox/VBoxGuestAdditions.iso /media/
sudo /media/VBoxLinuxAdditions.run
sudo shutdown -r now
```

# Usage

To run the default playbook:

```sh
ansible-playbook -i inventories/localhost -K ubuntu.yml
```

# VirtualBox settings

Recommended settings when using VirtualBox:

1. At least 2GB RAM.
2. At least 128MB for Video Memory.
3. At least 20GB of dynamic storage.
4. Devices -> Shared Clipboard -> Bidirectional.
5. Add code from host as shared folder.
