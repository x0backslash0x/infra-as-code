Role createuser
=========

Creates a user on the host.
Additionally grants the user sudo rights and generates an ssh-keypair for the user.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Modules
------------
List of modules used in the role

* ansible.builtin.user

Role Variables
--------------

- username: name of the user to be created
- userpass: sha-512 hashed password of the user to be createdµ
- ansible_facts.os_family: conditional check for setting group name

Dependencies
------------

- mkpasswd 

Example Playbook
----------------
    - hosts: managed-nodes
      gather_facts: True
      become: yes
      roles:
        - { role: createuser, username: "<username>", userpass: "<hash>" }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
