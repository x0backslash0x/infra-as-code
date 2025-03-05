Role selinux
=========

Sets SELinux to disabled or permissive, depending on its current state. Reboots host(s) for changes to take effect.

Requirements
------------

Only for distributions that use SELinux.

Modules
------------
List of modules used in the role

* ansible.posix.selinux

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

- reboot role

Example Playbook
----------------
    - name: <play name>
      hosts: <hosts>
      gather_facts: True
      become: yes
      roles:
         - selinux

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
