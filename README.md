mariadb
=======

Install mariadb.


Role Variables
--------------
没有必须设置的变量,可选的可以设置的变量如下:

```
mariadb_open_files_limit: 2048
mariadb_max_connections: 1024

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

