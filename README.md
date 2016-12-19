mariadb
=======

Install mariadb.


Role Variables
--------------

```
# optional vars in default/main.yml
mariadb_bind_address: 0.0.0.0
mariadb_listen_port: 3307

# optional vars in vars/main.yml
mariadb_users:
  - name: frank6866
    host: "%"
    password: Change#me
    privilege: "*.*:ALL"
    state: present

# required vars
mariadb_root_password: Change@Me
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

