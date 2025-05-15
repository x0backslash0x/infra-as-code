Role Vikunja
=========

Deploys the vikunja todo app using docker containers.

Requirements
------------

Docker must be installed
The ansible_user must have access rights to run the docker command

Role Variables
--------------

* db_user_name
* db_user_pass
* db_name
* jwt_secret
* network_name

Dependencies
------------

collections:
* community.docker

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: vikunja }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
