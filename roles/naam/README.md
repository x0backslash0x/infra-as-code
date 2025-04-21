Role Name
=========
naam

hostname aanpassen

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Modules
------------
List of modules used in the role

* ansible.builtin.hostname

Role Variables
--------------

* hostname

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------
    - name: <play name>
      hosts: <hosts>
      become: yes
      roles:
         - { role: naam, hostname: "ansible-host" }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
