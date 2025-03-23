Role rwin_hostname
=========

Changes the hostname.

Requirements
------------

* ansible.windows

Role Variables
--------------

* host_name

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: rwin_hostname, host_name: "{{ hostname }}" }
      vars:
        hostname: "{{ <hostname> }}"

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
