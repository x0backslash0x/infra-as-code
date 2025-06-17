# Overzicht
Het verloop van deze play valt grotendeels op de delen in volgende stappen
* docker installeren
* SSL certifikaat aanmaken
* containers opzetten

# Depencencies
**ansible rollen**
* dockerinstall
* reboot
* certify
* vikunja

***ansible modules**
* acme_certificates
* ansible.builtin.file
* ansible.builtin.template
* ansible.builtin.copy
* ansible.builtin.package
* ansible.builtin.command
* ansible.builtin.shell
* ansible.builtin.service
* ansible.builtin.user
* ansible.builtin.reboot
* community.crypto.openssl_privatekey
* community.crypto.openssl_csr
* community.crypto.x509_certificate
* community.docker.docker_container
* community.docker.docker_network

# variables

| variable    | scope               | description                     |
|-------------|---------------------|---------------------------------|
| user        | playbook invocation | remote user                     |
| cn          | playbook invocation | common name for certificate     |
| uri_scheme  | playbook invocation | use HTTP or HTTPS for nginx     |
| project_dir | playbook            | absolute path for project files |

# Installatie Vikunja
## basic install 1
1 container

**commands**
```
mkdir -p $PWD/files $PWD/db
chown 1000 $PWD/files $PWD/db
docker run --rm --name vikunja -p 3456:3456 -v $PWD/files:/app/vikunja/files -v $PWD/db:/db vikunja/vikunja
```
**compose file**
compose bestand kopieren
```
mkdir -p $PWD/files $PWD/db
chown 1000 $PWD/files $PWD/db
docker compose up
```

## basic install 2
2 containers
* vikunja
* database

**commands**
```
mkdir -p $PWD/files $PWD/db
docker network create shared
docker run -d --network shared --name db -v $PWD/db:/var/lib/mysql -e MYSQL_RANDOM_ROOT_PASSWORD=true -e MYSQL_USER=dbuser -e MYSQL_PASSWORD=dbpass -e MYSQL_DATABASE=vikunja mariadb:10
docker run -d --network shared --name vikunja -p 3456:3456 -v $PWD/files:/app/vikunja/files -e VIKUNJA_SERVICE_PUBLICURL=127.0.0.1 -e VIKUNJA_DATABASE_HOST=db -e VIKUNJA_DATABASE_USER=dbuser -e VIKUNJA_DATABASE_PASSWORD=dbpass -e IKUNJA_DATABASE_TYPE=mysql -e VIKUNJA_DATABASE_DATABASE=vikunja -e VIKUNJA_SERVICE_JWTSECRET=secrettokenstr1ng vikunja/vikunja
```

## reverse-proxy install
3 containers
* vikunja
* database
* reverse proxy

# gebruik
requirements controleren
* op ansible controller
  * python modules
  * ansible collections
* op host
  * docker installatie

bestanden aanmaken

* ansible.cfg     basis ansible config
* hosts           host specificatie

playbook uitvoeren
```
ansible-playbook playbook.yml -e user=<username> -e cn=<common name> -e uri_scheme=<http|https> -K
```
