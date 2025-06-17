# open bugs
## BUG template
**title**</br>

**context**</br>

**description**</br>

**resolution**</br>


## BUG20250520-2
**title**</br>
extra dirs created

**context**</br>
file creation

**description**</br>
the directories `db` and `files` are also created at the user home directory


## BUG20250616-1
**title**</br>
playbook execution fails when variable is undefined

**context**</br>
playbook invocation

**description**</br>
![ansible error](./info/ansibe_missing-variable_uri_scheme.png)
The role *certify* fails to run when the variable *url_scheme* is not defined.
This variable is used to decide whether or not the role should run.


## BUG20250616-2
**title**</br>
host rebooted even when it's not needed

**context**</br>
role execution - dockerinstall

**description**</br>
The *dockerinstall* role contains a step that reboots the host.
If docker is already installed, there is no need to reboot the host.
Unnecessary reboots need to be avoided as much as possible.

**resolution**</br>
One solution for this is to run the role conditionally.
The condition should check whether the docker-ce package is installed on the host.


## BUG20250617-1
**title**</br>
Cannot issue cert for localhost

**context**</br>
Let's Encrypt certificate request

**description**</br>
![Let's Encrypt error](./info/letsencrypt_invalid-cn-localhost.png)
Let's Encrypt does not allow the use of *localhost* as Common Name.

So calling the playbook with *cn=localhost* summons the above error



# closed bugs
## BUG20250520-1
**title**</br>
cannot load certificate - no start line

**context**</br>
nginx container

**description**</br>
![container log](info/docker-rproxy_cannot-load-certificate-no-start-line.png)</br>
nginx cannot load the Let's Encrypt certificate


## BUG20250617-2
**title**</br>
undefined variable *docker_user* for vikunja role

**context**</br>
variable scope outside the role

**description**</br>
![undefined variable error](./info/ansibe_missing-variable_docker_user.png)
The vikunja role uses a variable *docker_user*
The variable is expected to be inherited through the playbook, from a previous role *dockerinstall*
The role *dockerinstall* does not set the variable *docker_user* explicitly. It is passed from the playbook.

**resolution**</br>
Pass the variable explicitly when calling the role in the playbook.
