sudoers update role
=========

sudoers update ansible galaxy role.

Requirements
------------

None

Role Variables
--------------

* wheel_group_enabled  
if you need wheel administrator group, Then set True.  
wheel group has to execute sudo permission.

* sudoers  
add sudoers.d configurations.  
e.g.  
```yml
sudoers:
  - name: user_1
    line: "user_1 ALL=(ALL) NOPASSWD: ALL"
```

Dependencies
------------

None

Example Playbook
----------------

```yml
---
- hosts: all
  become: true
  roles:
    - role: galaxy-sudoers
      wheel_group_enabled: True
      sudoers:
        - { name: foo, line: "%hoge ALL=(ALL) NOPASSWD: ALL" }
        - { name: bar, line: "%fuga ALL=(ALL) NOPASSWD: ALL" }
```

License
-------

BSD

Author Information
------------------

[Daisuke Maeda](https://github.com/dmae3 "Daisuke Maeda")
