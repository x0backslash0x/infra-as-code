Role updateall
=========

Updates all installed packages on the host(s).
Destinguishes between Debian, Red Hat (, Alpine) -based distributions.

Requirements
------------

* facts gathering needs to be enabled.
* community.general: not required by default as task has been disabled by commenting.

Modules
------------
List of modules used in the role

* ansible.builtin.apt
* ansible.builtin.dnf
* community.general.apk

Role Variables
--------------

* ansible_facts.os_family: obtained from ansible facts_gathering task

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------
    - name: <play name>
      hosts: <hosts>
      gather_facts: True
      become: yes
      roles:
         - updateall

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
