# Ansible role : Init

![](https://img.shields.io/github/release/Pandemonium1986/ansible-role-init.svg)
![](https://img.shields.io/github/repo-size/Pandemonium1986/ansible-role-init.svg)
![](https://img.shields.io/github/release-date/Pandemonium1986/ansible-role-init.svg)
![](https://img.shields.io/github/license/Pandemonium1986/ansible-role-init.svg)

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
_packages:
  - apt-transport-https
  - build-essential
  - ca-certificates
  - cowsay
  - curl
  - dkms
  - dnsutils
  - fonts-powerline
  - git
  - gitk
  - gnupg2
  - htop
  - libfortune-perl
  - man
  - mlocate
  - module-assistant
  - net-tools
  - nmap
  - powerline
  - python-dev
  - software-properties-common
  - sudo
  - tmux
  - tree
  - unzip
  - vim
  - zsh
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

-   **Michael Maffait** - _Initial work_ - [Pandemonium1986](https://github.com/Pandemonium1986)
