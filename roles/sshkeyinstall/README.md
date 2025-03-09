Role Name
=========

Adds an ssh authorized key for a certain user.

Requirements
------------

ansible.posix

Role Variables
--------------

- username: for what user will the key be added
- ssh_key: public key to be added to authorized_keys

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------
    - hosts: <hosts>
      become: yes
      roles:
         - { role: sshkeyinstall, username: "<username>" ssh_key: "<ssh public key>" }
         #- { role: sshkeyinstall, username: "<username>" ssh_key: "{{ lookup('file', '<filename>') }}" }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
