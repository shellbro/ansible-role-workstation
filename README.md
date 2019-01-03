shellbro.workstation
====================

[![Build Status](https://travis-ci.org/shellbro/ansible-role-workstation.svg?branch=master)](https://travis-ci.org/shellbro/ansible-role-workstation)

Ansible role for configuring workstation (CentOS 7).

Requirements
------------

None

Role Variables
--------------

* username - name of the user account
* rpm_url_chrome - URL to Google Chrome RPM (required)
* rpm_url_slack - URL to Slack RPM (required)
* rpm_url_skype - URL to Skype RPM (required)
* rpm_url_teamviewer - URL to TeamViewer RPM (required)
* rpm_url_custom - list of URLs to custom RPMs that will be installed (by
default empty list)
* config_url_bashrc - URL to .bashrc file (required)
* config_url_gitconfig - URL to .gitconfig file (required)
* config_url_toprc - URL to .toprc file (required)
* config_url_terminator - URL to Terminator config (required)

Dependencies' vars:

* nux_dextop_rpm_url - rpm_url var from shellbro.nux-dextop role

Dependencies
------------

Dependencies that are required for this role to work:

* shellbro.epel
* shellbro.npm
* shellbro.nux-dextop
* shellbro.pip
* shellbro.scl

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: shellbro.workstation
          username: shellbro
          rpm_url_chrome: https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
          rpm_url_slack: https://downloads.slack-edge.com/linux_releases/slack-3.3.3-0.1.fc21.x86_64.rpm
          rpm_url_skype: https://repo.skype.com/latest/skypeforlinux-64.rpm
          rpm_url_teamviewer: https://download.teamviewer.com/download/linux/teamviewer.x86_64.rpm
          custom_rpms:
            - https://releases.hashicorp.com/vagrant/2.2.2/vagrant_2.2.2_x86_64.rpm
          config_url_bashrc: https://raw.githubusercontent.com/shellbro/dotfiles/master/.bashrc
          config_url_gitconfig: https://raw.githubusercontent.com/shellbro/dotfiles/master/.gitconfig
          config_url_toprc: https://raw.githubusercontent.com/shellbro/dotfiles/master/.toprc
          config_url_terminator: https://raw.githubusercontent.com/shellbro/dotfiles/master/.config/terminator/config

          nux_dextop_rpm_url: http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm

License
-------

BSD

Author Information
------------------

Jakub Gorczyca
