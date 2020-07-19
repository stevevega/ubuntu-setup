# Ubuntu Setup

Ansible playbook to setup Ubuntu.

# Prerequisites

To prepare your environment:

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

# VirtualBox setup

Recommended settings when using VirtualBox:

1. At least 2GB RAM.
2. At least 128MB for Video Memory.
3. At least 20GB of dynamic storage.

## Setup VirtualBox Guest Additions

```sh
sudo apt install virtualbox-guest-additions-iso
sudo mount -o loop /usr/share/virtualbox/VBoxGuestAdditions.iso /media/
sudo /media/VBoxLinuxAdditions.run
sudo shutdown -r now
```

## Additional settings

Change host key:
Preferences -> Input -> Virtual Machine -> Host Key Combination: Right ⌘

Setup clipboard:
Devices -> Shared Clipboard -> Bidirectional.

Add code from host as shared folder
Devices -> Shared Folder -> Shared Folder Settings

## Setup Mac keyboard mapping

```sh
git clone https://github.com/rbreaves/kinto.git /tmp/kinto
cd /tmp/kinto
./setup.py
```

Answers for install prompts:

- 1: Kinto - xkeysnail (udev/x11) - Recommended
- 2: Mac Only & VMs on Macbooks - 3rd & 1st party Apple keyboards
- y: Do you want multi-language on Right Alt key?
- y: Would you like to give VS Code Sublime Text keymaps?
- y: Do you want to apply system level shortcuts?

# Usage

1. Clone the repo

```sh
git clone https://github.com/stevevega/ubuntu-setup.git
```

2. Run the Ansible playbook:

```sh
cd ubuntu-setup
ansible-playbook -i inventories/localhost -K ubuntu.yml
```
