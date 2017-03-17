mariadb
=======

Install mariadb.


Role Variables
--------------
The variables are all optional, the default password is 'change_me' if you donot set it.

eg:

```
mariadb_root_password: change_me

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

# mariadb_open_files_limit should large than mariadb_max_connections
mariadb_open_files_limit: 2048
mariadb_max_connections: 1024
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

