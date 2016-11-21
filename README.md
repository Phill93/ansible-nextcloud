
[![Ansible Galaxy](https://img.shields.io/badge/Ansible%20Galaxy-Phill93.nextcloud-blue.svg)](https://galaxy.ansible.com/Phill93/nextcloud/)

Role Name
=========

This Role installs [Nextcloud](http://www.nextcloud.com).

Requirements
------------

A Debian compatible Linux with Apache and PHP 7.0

Role Variables
--------------

See [defaults/main.yml](defaults/main.yml)


Example Playbook
----------------
```yaml
- hosts: all
  become: true
  vars:
      nextcloud_database_type: "sqlite"
      nextcloud_database_name: "cloud"
      nextcloud_database_prefix: "oc_"
  roles:
    - role: nextcloud
```
License
-------

[GPLv3](license.md)

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
