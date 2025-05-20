Role certify
=========

Generate an SSL certificate
* either self-signed, valid for 90 days
* or via Let's Encrypt

Requirements
------------

Docker must be installed.
The Let's Encrypt validation procedure relies on an nginx container for facilitating the `http-01` validation method.

Role Variables
--------------

* start_dir
<!-- * cert_basedir -->
<!-- * cert_commonname -->
<!-- * cert_privatekey -->
<!-- * cert_request -->
<!-- * cert_path -->


Dependencies
------------

collections:
* community.crypto
* community.docker

python modules
* cryptography >= 1.6

Example Playbook
----------------

- hosts: all
  roles:
    - role: certify
        vars:
          start_dir: <absolute path>
          <!-- cert_commonname: <common-name> -->

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
