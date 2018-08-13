
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
Example Apache Configuration for JWT Authentication
---------------------------------------------------
```apache
<VirtualHost *:443>
  ServerName example.com
  DocumentRoot "/var/www/nextcloud"

  <Directory "/var/www/nextcloud">
    AllowOverride All
    Options -Indexes +FollowSymLinks
    Require all granted
  </Directory>
  
AuthJWTSignatureAlgorithm HS256
AuthJWTSignatureSharedSecret Q0hBTkdFTUU=
AuthJWTIss IAM

<Location "/index.php/apps/user_saml/saml/login">
  AuthType jwt
  AuthName "private area"
  Require valid-user
</Location>

</VirtualHost>
```

License
-------

[GPLv3](license.md)

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
