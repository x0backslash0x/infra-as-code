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

| variable                  | scope                        | description               |
|---------------------------|------------------------------|---------------------------|
| cert_commonname           | role invocation              |
| start_dir                 | role invocation              |
| cert_provider             | self                         | self-signed / letsencrypt |
| acme_directory_production | self                         |
| acme_directory_staging    | self                         |
| acme_account_key          | self                         |
| acme_challenge_dir        | self                         |
| cert_basedir              | self                         |
| cert_privatekey_path      | self                         |
| cert_privatekey_file      | self                         |
| cert_csr                  | self                         |
| cert_path                 | self                         |
| cert_file                 | self                         |
| cert_chain                | self                         |
| cert_fullchain            | self                         |
| http_challenge            | tasks/Letsencrypt validation |


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
          cert_commonname: <common-name>

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
