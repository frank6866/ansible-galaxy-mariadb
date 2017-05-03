mariadb standalone
=====================

This role is used to deploy mariadb in standalone mode. This role support the following configuration:

* set and change root password for mariadb
* set max_connections for mariadb
* create databases
* create users and grant privilege on some database


Role Variables
--------------
No required vars, the optional var as follows:


The default password for root is change_me, if you want to set the **mariadb_root_password** variable:

```
mariadb_root_password: change_me
```

If you want to change the max connections of mariadb, set the following variables:

```
mariadb_open_files_limit: 2048
mariadb_max_connections: 1024
```

Please make sure **mariadb_open_files_limit** is large than **mariadb_max_connections**, otherwise the **mariadb_max_connections** not work.


If you want to create databases and users, follow the example blow:

```
mariadb_databases:
  - keystone
  - glance
  - nova_api
  - nova
  - neutron

mariadb_users:
  - name: keystone
    password: change_me
    host: "%"
    privilege: "keystone.*:ALL"
    state: present
```


Example Playbook
----------------

```
- hosts: mariadb
  become: true
  roles:
    - frank6866.mariadb
```

License
-------

MIT
