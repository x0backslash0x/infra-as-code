Role certify
=========

Generate a self-signed certificate, valid for 90 days

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

* start_dir
* cert_basedir
* cert_commonname
* cert_privatekey
* cert_request
* cert_path


Dependencies
------------

collections:
* community.crypto

python modules
* cryptography >= 1.6

Example Playbook
----------------

- hosts: all
  roles:
    - role: certify
        vars:
          start_dir: <absolute path>
          cert_commonname: <common-name>

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
