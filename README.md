shellbro.workstation
===========

[![Build Status](https://travis-ci.org/shellbro/ansible-role-workstation.svg?branch=master)](https://travis-ci.org/shellbro/ansible-role-workstation)

Ansible role for configuring workstation (CentOS 7).

Requirements
------------

None

Role Variables
--------------

* autostart_apps - configure autostart (by default true)
* autostart_user - configure autostart for this user (required when
autostart_apps is true)

Dependencies
------------

* shellbro.docker-engine-ce
* shellbro.emacs
* shellbro.epel
* shellbro.hardware-tools
* shellbro.npm
* shellbro.nux-dextop
* shellbro.pip
* shellbro.scl

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: shellbro.workstation
          autostart_apps: true
          autostart_user: shellbro

License
-------

BSD

Author Information
------------------

Jakub Gorczyca
