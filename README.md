blinkstick
=========

A Playbook to deploy BlinkStick zabbix integration (colour coded group overview).

![blinkstick overview](https://raw.githubusercontent.com/mikejonesey/blinkstick-zabbix/master/files/blinkstick-zabbix.png)

Requirements
------------

A BlinkStick: https://www.blinkstick.com/

Role Variables
--------------

Define if a blinkstick group is to be created (for running under non-root user):

- create_blinkstick_usergroup: yes

Define zabbix api login details (setup a readonly user with no access to frontend):

- zabbix_url: "https://127.0.0.1/zabbix"
- zabbix_username: "Admin"
- zabbix_password: "zabbix"

Dependencies
------------

no dependancies on other roles, but will source zabbix login from a "monitor" group, if you do have one...

Example Playbook
----------------

- hosts: blinkstick
  roles:

    - role: blinkstick
      vars:
        action: install
      tags: blinkstick-install

    - role: blinkstick
      vars:
        action: zabbix-script
      tags: blinkstick-zabbix

  tags: blinkstick

License
-------

GPLv2

Author Information
------------------

Mikejonesey
