# ansible-basic-server-setup

Currently, this Ansible plays configure the followings:

| role | purpose|
|:-----|:-------|
| provision | role to (re)provision an operating system on a given server
| configure | role to (re)configure hostname, hosts file, firewalld, fail2ban, add first admin user, add EPEL, and update the service
| ovirt     | role to (re)deploy ovirt engine on RPM based distribution

## status

| provider | roles         | status  | missing feature |
|:---------|:--------------|:--------|:----------------|
| Hetzner  | provision     | 90% | last task is about checking installation status by waiting for port 22 to become alive but this is not working because of the way the provisioning is wokirng with a "rescue" mode
|          | configuration | 50% | the configuration is only working with RPM based distribution (with yum or dnf)
|          |               |     | still need to have server password to perform the confirmation however working in retrieving the created password during installation only based on the server IP
|          | ovirt         | 0%   | not yet started

## usage

| provider | requirements|
|:---------|:------------|
| Hetzner  | need to the set up a webservice account to access the remote configuration features from Hetzner: https://wiki.hetzner.de/index.php/Robot_Webservice.
|          | the roles are looking for the inventory group being used which for hetzner is [hetzner] and [hetzner:vars] to be modified with the required info.