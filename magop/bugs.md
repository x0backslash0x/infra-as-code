# bugs
## BUG template
**name**</br>


**context**</br>


**description**</br>


## BUG20250520-1
**name**</br>
cannot load certificate - no start line

**context**</br>
nginx container

**description**</br>
![container log](info/docker-rproxy_cannot-load-certificate-no-start-line.png)</br>
nginx cannot load the Let's Encrypt certificate

## BUG20250520-2
**name**</br>
extra dirs created

**context**</br>
file creation

**description**</br>
the directories `db` and `files` are also created at the user home directory

## BUG20250616-1
**name**</br>
playbook execution fails when variable is undefined


**context**</br>
playbook invocation


**description**</br>
![ansible error](./info/ansibe_missing-variable_uri_scheme.png)
The role *certify* fails to run when the variable *url_scheme* is not defined.
This variable is used to decide whether or not the role should run.


# open bugs
* BUG20250520-2
* BUG20250616-1


# closed bugs
* BUG20250520-1