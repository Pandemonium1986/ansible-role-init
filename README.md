# Ansible role : Init

[![Ansible Role](https://img.shields.io/ansible/role/d/pandemonium1986/init?logo=Ansible&color=blue)](https://galaxy.ansible.com/ui/standalone/roles/pandemonium1986/init/)
[![Molecule](https://github.com/Pandemonium1986/ansible-role-init/actions/workflows/molecule.yml/badge.svg)](https://github.com/Pandemonium1986/ansible-role-init/actions/workflows/molecule.yml)
![GitHub release](https://img.shields.io/github/release/Pandemonium1986/ansible-role-init.svg?logo=github)
![Github license](https://img.shields.io/github/license/Pandemonium1986/ansible-role-init.svg?logo=github)

Install and configure a lot of packages to initialize a linux environment. Create groups and users.

## Requirements

This role is self contained. He installs packages for debian, ubuntu, opensuse, sles, centos if needed.

## Role Variables

From defaults/main.yml :

```yaml
init_groups:
  - group_name: pandama                      # Mandatory
    group_gid: 19860                         # Optionnal

init_users:
  - user_name: pandemonium                   # Mandatory
    user_comment: Pandemonium1986            # Mandatory
    user_groups: ["pandemonium", "pandama"]  # Optionnal
    user_home: /home/pandemonium             # Mandatory
    user_password: $6$salt$IxDD3jeSOb5eB1CX5LBsqZFVkJdido3OUILO5Ifz5iwMuTS4XMS130MTSuDDl3aCI6WouIL9AjRbLCelDCy.g. # Mandatory
    user_shell: "/bin/zsh"                   # Optionnal
    user_uid: "1000"                         # Optionnal
```

From vars/[distro|familly]-[os_familly]-[os_version].yml (depends of distribution):

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
  - man
  - mlocate
  - module-assistant
  - net-tools
  - nmap
  - powerline
  - remmina
  - remmina-plugin-rdp
  - remmina-plugin-vnc
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
  - curl
  - nmap

```

## Dependencies

None.

## Example Playbook

```yaml
---
- name: Init play
  hosts: pandama
  become: true
  become_method: sudo
  become_user: root
  tasks:
    - import_role:
        name: pandemonium1986.init
```

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details

## Author Information

- **Michael Maffait** - _Initial work_ - [Pandemonium1986](https://github.com/Pandemonium1986)
