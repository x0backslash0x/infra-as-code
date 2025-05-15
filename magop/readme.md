# basic install 1
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

# basic install 2
2 containers
* vikunja
* database
