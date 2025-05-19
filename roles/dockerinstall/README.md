Role dockerinstall
==================

Install docker from the official repo.
For now only installs on RHEL & Debian based distributions.

[Install Docker Engine on Debian](https://docs.docker.com/engine/install/debian/)
[Install Docker Engine on RHEL](https://docs.docker.com/engine/install/rhel/)

Modules
------------
List of modules used in the role

* ansible.builtin.command
* ansible.builtin.dnf

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

* docker_official_repo: url to the official docker repository for RHEL
* docker_dependencies: list of packages to install alongside docker
* user: user to add to the docker group

Dependencies
------------

* gathering_facts
* updateall role

Example Playbook
----------------
    - name: <play name>
      hosts: <hosts>
      gather_facts: True
      gather_subset:
        - "!all"
        - "os_family"
      become: yes
      roles:
         - { role: dockerinstall, user: <user> }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
