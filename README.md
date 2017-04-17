kleinstuff.el-nodejs
=========

Ansible role to install and configure nodejs on a Enterprise Linux box.

Requirements
------------

You need access to the internet and epel repository installed (the role installs it for you)

Role Variables
--------------

All variables are setup on defaults/main.yml

### By default we install nodejs and npm
      ansible_el_nodejs__packages:
        - nodejs
        - npm

### Install pm2 process manager (default: true)
      ansible_el_nodejs__install_pm2: true

### Install other npm packages (default: none):
        ansible_el_nodejs__npm_packages:
          - package1
          - package2
          - ...packagen

### Create an user to run applications/pm2 (default: no)
        ansible_el_nodejs__pm2user: username

### If you need, you can add ssh keys to the created user above (default: no):
        ansible_el_nodejs__pm2user_public_keys_file: public_keys/linux_team.keys

Dependencies
------------

This role has no deps

Example Playbook
----------------

     - hosts: servers
       roles:
          - { role: kleinstuff.el-nodejs }

License
-------

BSD

Author Information
------------------

https://github.com/kleinstuff

