# Ansible role : Init

Install and configure a lot of packages to initialize a linux environment.

## Requirements

This roles is self contained and install packages from debian backports if needed.

## Role Variables

From defaults/main.yml :

```yaml
init_users:
  - user_name: pandemonium
    user_group: ['cdrom', 'floppy', 'audio', 'dip', 'video', 'plugdev', 'netdev']
    user_home: /home/pandemonium
    user_password: $6$salt$IxDD3jeSOb5eB1CX5LBsqZFVkJdido3OUILO5Ifz5iwMuTS4XMS130MTSuDDl3aCI6WouIL9AjRbLCelDCy.g.  
```

From vars/main.yml :

```yaml
apt_packages:
  - apt-transport-https
  - build-essential
  - ca-certificates
  - cowsay
  - curl
  - dkms
  - dnsutils
  - fonts-powerline
  - gnupg2
  - htop
  - libfortune-perl
  - man
  - mlocate
  - module-assistant\
  - net-tools
  - nmap
  - powerline
  - python-dev
  - software-properties-common
  - sudo
  - tree
  - unzip
  - vim
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: servers
  roles:
    - { role: pandemonium1986.init }
```

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details

## Author Information

-   **Michael Maffait** - _Initial work_ - [Pandemonium1986](https://github.com/Pandemonium1986)
