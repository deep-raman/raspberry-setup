raspberry-setup
===============

This ansible role setup **RaspberryPi** as workstation. It installs the basic packages, that are very useful if you use it on daily basis.
It makes a life a bit easy so you don't have to spend a lots of time installing or configuring the basic things.


Role Variables
--------------

The role variables are defined in `defaults/main.yml`

- `packages`: list of packages that the role install by default.
- `user`: the user that you will be using to work
- `zsh`: to install zsh as default shell
- `powerlevel10k`: to install powerlevel10k
- `set_staticip`: to configure static ip
- `static_ip`: ip address configure
- `router_ip`: route ip to set as gateway
- `virtualenv`: to install virtualenv
- `virtualenvs_dir`: virtualenv home dir
- `virtualenvs_path`: to export the env variable virtualenv home dir
- `virtualenvwrapper_path`: virtualenvwrapper script path
- `log2ram`: to install log2ram utility, to write logs to ram to avoid excessive writing on the SD
- `size`: size of the log folder that will be reserved in the ram
- `ssh`: to enable ssh access to the pi, that by default is disabled

Example Playbook
-----------------
```
    - hosts: all
      become: yes
      
      roles:
        - raspberry-setup

```

For the direct one line command installation on localhost use :

`ansible-playbook --connection=local --inventory 127.0.0.1, raspberry-setup.yaml`

To run some specific task from the role use :

`ansible-playbook --connection=local --inventory 127.0.0.1, raspberry-setup.yaml --tags log2ram`

Dependencies
------------

`none`


Requirements
------------

`ansible 2.7.7`


Author Information
------------------

`Raman Deep`
`29th May 2020`
`deep.raman85@gmail.com`
