# Ansible role : Init

![Ansible Role](https://img.shields.io/ansible/role/36274?logo=ansible)
[![Molecule](https://github.com/Pandemonium1986/ansible-role-init/actions/workflows/molecule.yml/badge.svg)](https://github.com/Pandemonium1986/ansible-role-init/actions/workflows/molecule.yml)
![GitHub release](https://img.shields.io/github/release/Pandemonium1986/ansible-role-init.svg?logo=github)
![Github license](https://img.shields.io/github/license/Pandemonium1986/ansible-role-init.svg?logo=github)
![Ansible Quality Score](https://img.shields.io/ansible/quality/36274?logo=ansible)

Install and configure a lot of packages to initialize a linux environment.

## Requirements

This role is self contained. He installs packages for debian, ubuntu, linux mint, centos if needed.

## Role Variables

From defaults/main.yml :

```yaml
init_users:
  - user_name: pandemonium
    user_group: ['cdrom', 'floppy', 'audio', 'dip', 'video', 'plugdev', 'netdev']
    user_home: /home/pandemonium
    user_password: $6$salt$IxDD3jeSOb5eB1CX5LBsqZFVkJdido3OUILO5Ifz5iwMuTS4XMS130MTSuDDl3aCI6WouIL9AjRbLCelDCy.g.  
```

From vars/main.yml (depends of distribution):

```yaml
---
_packages_ansible_bootstrap:
  - python3
  - python3-dev
  - sudo

_packages:
  - apt-transport-https
  - audacity
  - build-essential
  - ca-certificates
  - clamav
  - curl
  - dkms
  - dnsutils
  - fonts-powerline
  - gimp
  - git
  - gnupg2
  - htop
  - keepassxc
  - man
  - mlocate
  - module-assistant
  - net-tools
  - nmap
  - powerline
  - software-properties-common
  - tmux
  - tree
  - unzip
  - vim
  - zsh

_packages_os:
  - chromium
  - firefox-esr

_packages_backports:
  - remmina
  - remmina-plugin-rdp
  - remmina-plugin-vnc

```

## Dependencies

None.

## Example Playbook

```yaml
---
- name :         Init play
  hosts :        pandama
  become:        true
  become_method: sudo
  become_user:   root
  tasks:
    - import_role:
        name:    pandemonium1986.init

```

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details

## Author Information

- **Michael Maffait** - _Initial work_ - [Pandemonium1986](https://github.com/Pandemonium1986)
