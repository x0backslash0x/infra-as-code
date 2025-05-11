2024 - 2025 Electronica-ICT, Cybersecurity & Cloud
OLOD Infrastructure As Code

# Ansible modules
* copy ([ansible.builtin.copy](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/copy_module.html))
* template ([ansible.builtin.template](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/template_module.html))
* user/group ([ansible.builtin.user](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/user_module.html))
* packages ([ansible.builtin.package](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/package_module.html))
* service ([ansible.builtin.service](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/service_module.html))
* firewalls ([ansible.posix.firewalld](https://docs.ansible.com/ansible/latest/collections/ansible/posix/firewalld_module.html))
* iptables ([ansible.builtin.iptables](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/iptables_module.html))
* file ([ansible.builtin.file](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html))
* lineinfile ([ansible.builtin.lineinfile](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/lineinfile_module.html))
* (un)archive ([ansible.builtin.unarchive](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/unarchive_module.html))
* command ([ansible.builtin.command](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/command_module.html))
* git ([ansible.builtin.git](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/git_module.html))
* reboots ([ansible.builtin.reboot](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/reboot_module.html²))
* pip ([ansible.builtin.pip](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/pip_module.html))
* local gen ([community.general.locale_gen](https://docs.ansible.com/ansible/latest/collections/community/general/locale_gen_module.html))
* selinux ([ansible.posix.selinux](https://docs.ansible.com/ansible/latest/collections/ansible/posix/selinux_module.html))

# Labo 3
Neem de playbook van vorige week en breid je playbook uit met minstens 7 modules uit voorgaande lijst.

1. selinux
2. package voor installatie
3. file voor aanmaken bestand en bestandrechten

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

## Gebruikte modules
* ([ansible.builtin.hostname](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/hostname_module.htm))
* ansible.posix.selinux
* [ansible.builtin.reboot](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/user_module.html)
* [ansible.posix.authorized_key](https://docs.ansible.com/ansible/latest/collections/ansible/posix/authorized_key_module.html)

## Roles
Aangemaakte rollen
- createuser: Creates a user on the host
- naam: hostname aanpassen
- reboot: Reboots the host(s).
- selinux: Sets SELinux to disabled or permissive, depending on its current state.
- sshkeyinstall: Adds an ssh public key to the authorized_keys of the root user.
- down: Unconditionally shuts down the machine
- updateall: Updates all installed packages on the host(s)
- minimalinstall: Installs a minimal collection of essential packages
- dockerinstall: Install docker from the official repo.

# Labo 5: Ansible & Windows
## Opdracht
* Zet je windows machine klaar dat je hem op basis van WINRM kan configureren met ansible.
* Schrijf een basis playbook uit waarin je minstens 10 modules voor iets nuttigs gebruikt ( 2 van de modules moeten nieuw zijn, modules die we nog niet gezien hebben).

## Modules
Voor sommige windows modules is er ook een `ansible.windows` tegenhanger. maar die werd om de een of andere reden niet erkend door ansible
`ERROR! couldn't resolve module/action`

1. [ansible.windows.win_updates](https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_updates_module.html)
2. [ansible.windows.win_reboot](https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_reboot_module.html)
3. [ansible.windows.win_hostname](https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_hostname_module.html)
4. [community.windows.win_hosts](https://docs.ansible.com/ansible/latest/collections/community/windows/win_hosts_module.html)
5. [community.windows.win_firewall](https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_firewall_module.html)
6. [ansible.windows.win_service](https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_service_module.html)
7. [community.windows.win_security_policy](https://docs.ansible.com/ansible/latest/collections/community/windows/win_security_policy_module.html)
8. [ansible.windows.win_optional_feature](https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_optional_feature_module.html)
9. [ansible.windows.win_command](https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_command_module.html#ansible-collections-ansible-windows-win-command-module)
10. [community.windows.wim_timezone](https://docs.ansible.com/ansible/latest/collections/ansible/windows/win_timezone_module.html#ansible-collections-ansible-windows-win-timezone-module)

De playbook en hosts file maken gebruik van volgende variabelen
* hostname (file, hostname)
* host_ip bestand - ip van hosts
* passwd bestand - wachtwoord voor host
* ansible_controller

# Labo 6
## Opdracht
* Maak een overzichtje van alles wat er op je windows (Mac of Linux) PC draait.
* Maak een ansible procedure om zoveel mogelijk van deze software automatisch te installeren op je Windows 2019 vm.
* Creeëer indien nodig de nodige packages.

## Packages
* [7zip](https://community.chocolatey.org/packages/7zip#ansible)
* [dropboxç](https://community.chocolatey.org/packages/dropbox/220.4.4126)
* [greenshot](https://community.chocolatey.org/packages/greenshot)
* [irfanview](https://community.chocolatey.org/packages/IrfanView)
* [firefox](https://community.chocolatey.org/packages/Firefox)
* [okular](https://community.chocolatey.org/packages/okular)
* [python](https://community.chocolatey.org/packages/python/3.13.2)
* [notepad++](https://community.chocolatey.org/packages/notepadplusplus.install)
* [openssl](https://community.chocolatey.org/packages/OpenSSL.Light)
* [VLC media player](https://community.chocolatey.org/packages/vlc)
* [Java Runtime Environment (JRE)](https://community.chocolatey.org/packages/jre8)
* [Belgium e-ID Middleware](https://community.chocolatey.org/packages/eid-belgium)
* [Belgium e-ID Viewer](https://community.chocolatey.org/packages/eid-belgium-viewer)
* [Bruno](https://community.chocolatey.org/packages/bruno)
* [node.js](https://community.chocolatey.org/packages/nodejs)
* [OBS Studio](https://community.chocolatey.org/packages/obs-studio)
* [Toggl Track](https://community.chocolatey.org/packages/toggl)
* [Git](https://community.chocolatey.org/packages/git)
* [Discord](https://community.chocolatey.org/packages/discord)
* [Microsoft Visual Studio Code](https://community.chocolatey.org/packages/vscode)

# Labo 9

## Modules
* [community.vmware.vmware_local_user_manage](https://docs.ansible.com/ansible/latest/collections/community/vmware/vmware_local_user_manager_module.html#ansible-collections-community-vmware-vmware-local-user-manager-module)
* 