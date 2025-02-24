2024 - 2025 Electronica-ICT, Cybersecurity & Cloud
OLOD Infrastructure As Code

# Labo 4
## Opdracht
Een basis bibliotheek maken met volgende rollen
* naam: Juiste naam zetten
* jackocreate: Een user acko aanmaakt en hem toegang geeft via een key tot alles
* Minimal install: Alle minimale pakketten die je nodig hebt :
    - EPEL
    - nc
    - mtr
    - git
* sshkey: Installatie van een standaard ssh-key op root voor toegang
* sshkeyupgrade: Upgrade-functie van die SSH-key ( nieuwe key installeren, oude wissen )
* Selinuxon / selinuxoff : Aan en afzetten van SELinux
* Firewall: Basis firewalling aanzetten:
    - Deny all wat niet nodig is;
    - Logging van alle dropped pakketten
* createuser: Aanmaken van een standaard user met een degelijk wachtwoord, key en sudo-rechten
* dockerinstall: nstallatie docker-ce met docker-compose, autostarten en user Jacko ook docker laat controleren
* mysqlnstall: Installatie veilige
* mysql met een database gezever, een user db met een random generated password dat wordt weergegeven en toegang heeft tot de db
* issue: Configuratie van een /etc/issue en /etc/issue.net met een angstaanjagende keepout boodschap en de naam van de host en de maker van de playbook erin
* updateall: Update-rol ( alle software naar laatste versie )
* backupconfig: Backup-rol schrijf een rol die een tar-backup maakt van de machine en de tar naar je pc kopieert
* reboot: Reboot
* down: Volledig afzetten van de VM
* verzin zelf nog twee rollen die je altijd kan gebruiken
