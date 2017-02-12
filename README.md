MariaDB
=========

MariaDB server optimized mainly for Drupal deployments.

Requirements
------------

None.

Role Variables
--------------

Configurable variables:

```
database_root_password: "root"
database_databases: [ 'db1', 'db2' ]
database_config_server:
  - { option: "character-set-server", value: utf8 , section: "mysqld" }
  - { option: "max_allowed_packet", value: 1024M , section: "mysqld" }
  - ...

database_users: []
  - { user: "myuser" , password: "s3cr3t" , host: "localhost" , priv: "myuser.*:ALL,GRANT" }
```

Dependencies
------------

None.

Example Playbook
----------------

```
- hosts: all
  user: root
  roles:
    - { role: "cristiroma.mariadb" }
```

License
-------

BSD

Author Information
------------------

This role was created and maintained by @cristiroma
