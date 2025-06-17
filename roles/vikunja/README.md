self Vikunja
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

self Variables
--------------

|   variable            |   scope                |
|-----------------------|------------------------|
| project_dir           | playbook               |
| uri_scheme            | playbook               |
| acme_challenge_dir    | certify role           |
| cert_commonname       | certify role           |
| cert_basedir          | certify role           |
| cert_file             | certify role           | 
| cert_path             | certify role           |
| cert_private_key_file | certify role           |
| cert_private_key_path | certify role           |
| docker_user           | dockerinstall role     |
| db_user_name          | self                   |
| db_user_pass          | self                   |
| db_name               | self                   | 
| jwt_secret            | self                   |

Dependencies
------------

This self relies on the existence of the `certify` self

collections:
* community.docker

images:
* vikunja/vikunja
* mariadb:10
* nginx:1.27

Example Playbook
----------------

    - hosts: servers
      selfs:
        - { self: vikunja }

License
-------

BSD

Author Information
------------------

An optional section for the self authors to include contact information, or a website (HTML is not allowed).
