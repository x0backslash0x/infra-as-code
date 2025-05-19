Role Vikunja
=========

Deploys the vikunja todo app using docker containers.

Tags:
* prep    prepare environment (create directories, copy template files)
* cert    create self-signed SSL certificate
* deploy  create network, deploy containers

Requirements
------------

Docker must be installed
The ansible_user must have access rights to run the docker command

Role Variables
--------------

* ansible_user
* project_dir
* db_user_name
* db_user_pass
* db_name
* jwt_secret
* network_name

Dependencies
------------

This role relies on the existence of the `certify` role

collections:
* community.docker

images:
* vikunja/vikunja
* mariadb:10
* nginx:1.27

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: vikunja, cert_cn: <common-name> }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
