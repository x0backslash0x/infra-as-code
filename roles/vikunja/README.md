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
the tasks for generating an SSL certificate assume `/etc/ssl/cert` and `/etc/ssl/private` exist

Role Variables
--------------

* db_user_name
* db_user_pass
* db_name
* jwt_secret
* network_name
* cert_basedir
* cert_cn
* cert_privatekey
* cert_request
* cert_path

Dependencies
------------

collections:
* community.docker
* community.crypto

python modules
* cryptography >= 1.6

images:
* vikunja/vikunja
* mariadb:10
* nginx:1.27

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
