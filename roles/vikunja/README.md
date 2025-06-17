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

Role Variables
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
| docker_user           | role invocation        |
| db_user_name          | self                   |
| db_user_pass          | self                   |
| db_name               | self                   | 
| jwt_secret            | self                   |

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
      - role: vikunja
        vars:
          docker_user: "{{ user }}"

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
